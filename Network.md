#Cloud services
##BASS

sudo -i
apt update 
hostnamectl set-hostname CloudServices
apt install -y nginx
apt install -y bind9


##Forwad

nano /etc/sysctl.conf

  net.ipv4.ip_forward=1

sysctl -p




#R1
### 192.168.255.153 - CloudServices
BASS

en
conf t
hostname R1
interface gigabitethernet 0/0	
no shutdown	
ip address dhcp
exit	
interface gigabitethernet 0/1	
no shutdown	
ip address 192.168.11.1 255.255.255.0	
exit
ip route 0.0.0.0 0.0.0.0 192.168.255.153	
do wr


NAT

interface Gi0/1
ip nat inside
!
interface Gi0/0
ip nat outside	
!
access-list 1 permit 192.168.11.0 0.0.0.255	
ip nat inside source list 1 interface Gi0/0 overload	



### 192.168.11.2   -   SRV1
### 192.168.255.82 -   R1 G0/0 

ip nat inside source static tcp 192.168.11.2 80 192.168.255.82 80


##DHCP
### 192.168.255.153 -  CloudServices

ip dhcp pool SRV1
network 192.168.11.0 255.255.255.0
default-router 192.168.255.153
dns-server 192.168.255.153







#SRV1
sudo -i

apt update 
hostnamectl set-hostname SRV1

apt install -y nginx

echo SRV1 > /var/www/html/index.html


systemctl reload nginx



##R2
### 192.168.255.153 - CloudServices
BASS

en
conf t
hostname R2
interface gigabitethernet 0/0	
no shutdown	
ip address dhcp
exit	
interface gigabitethernet 0/1	
no shutdown	
ip address 192.168.12.1 255.255.255.0	
exit
ip route 0.0.0.0 0.0.0.0 192.168.255.153	
do wr



NAT

interface Gi0/1
ip nat inside
!
interface Gi0/0
ip nat outside	
!
access-list 1 permit 192.168.12.0 0.0.0.255	
ip nat inside source list 1 interface Gi0/0 overload	



### 192.168.12.2   -   SRV2
### 192.168.255.2 -   R2 G0/0 

ip nat inside source static tcp 192.168.12.2 80 192.168.255.2 80


##DHCP
### 192.168.255.153 -  CloudServices

ip dhcp pool SRV2
network 192.168.12.0 255.255.255.0
default-router 192.168.255.153
dns-server 192.168.255.153


#SRV2

sudo -i

apt update 
hostnamectl set-hostname SRV2

apt install -y nginx

echo SRV2 > /var/www/html/index.html


systemctl reload nginx


#R3
### 192.168.255.153 - CloudServices
BASS

en
conf t
hostname R3
interface gigabitethernet 0/0	
no shutdown	
ip address dhcp
exit	
interface gigabitethernet 0/1	
no shutdown	
ip address 192.168.13.1 255.255.255.0	
exit
ip route 0.0.0.0 0.0.0.0 192.168.255.153	



NAT

interface Gi0/1
ip nat inside
!
interface Gi0/0
ip nat outside	
!
access-list 1 permit 192.168.13.0 0.0.0.255	
ip nat inside source list 1 interface Gi0/0 overload	



### 192.168.13.2   -   SRV3
### 192.168.255.209 -   R3 G0/0 

ip nat inside source static tcp 192.168.13.2 80 192.168.255.209 80


##DHCP
### 192.168.255.153 -  CloudServices

ip dhcp pool SRV3
network 192.168.13.0 255.255.255.0
default-router 192.168.255.153
dns-server 192.168.255.153



#SRV3

sudo -i

apt update 
hostnamectl set-hostname SRV3

apt install -y nginx

echo SRV3 > /var/www/html/index.html


systemctl reload nginx







#Cloud services


##DNS
mkdir /opt/dns
cp /etc/bind/db.local /opt/dns/demo.db
chown -R bind:bind /opt/dns

##SELINUX


nano /etc/apparmor.d/usr.sbin.named

/opt/dns/** rw,

systemctl restart apparmor.service


##ZONE
nano /etc/bind/named.conf.default-zones


### localhost  -  ht2022.wsr

zone "ht2022.wsr" {
   type master;
   file "/opt/dns/demo.db";
};


nano /opt/dns/demo.db

@ IN SOA ns.ht2022.wsr. root.localhost.(

### 192.168.255.153 -  CloudServices
### 192.168.255.82  -  R1
### 192.168.255.2  -  R2
### 192.168.255.209  -  R3

@     IN   NS    ns.ht2022.wsr.
@     IN   A     192.168.255.153  
ns    IN   A     192.168.255.153  
r1     IN   A     192.168.255.82
r2     IN   A     192.168.255.2
r3     IN   A     192.168.255.209


##Resolved 
systemctl disable systemd-resolved.service
systemctl stop systemd-resolved
rm /etc/dhcp/dhclient-enter-hooks.d/resolved

### оставть только nameserver 127.0.0.1

nano /etc/resolv.conf

nameserver 127.0.0.1







#CLI
##resolv
### 192.168.255.153 - CloudServices

vi /etc/resolv.conf 

nameserver 192.168.255.153


curl http://r1.ht2022.wsr
curl http://r2.ht2022.wsr
curl http://r3.ht2022.wsr




##Load Balancer

nano /ets/nginx/nginx.conf


upstream backend {
	server r1.ht2022.wsr fail_timeout=10;
	server r2.ht2022.wsr fail_timeout=10;
	server r3.ht2022.wsr fail_timeout=10;
}

server {
	listen 80 default_server;
	server_name ht2022.wsr;
	location / {
		proxy_pass http://backend ;
	}
}











