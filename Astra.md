## Лабораторная работа 5


![DEMO2022azure-Страница 7 (2)](https://user-images.githubusercontent.com/79700810/198517174-0e3d27f0-14d1-4455-89c1-7aa44340cfe3.jpg)



### Установка

Установка дистрибутива с помощью графического интерфейса

![image](https://user-images.githubusercontent.com/79700810/198209430-93f31ecd-43b8-4150-9e90-51a60ad8ad96.png)

![image](https://user-images.githubusercontent.com/79700810/198209583-eecca7ac-87d0-4401-8252-bd9a328dda2e.png)

![image](https://user-images.githubusercontent.com/79700810/198209601-059622ae-2424-496f-b269-7fb52a11f5ca.png)

![image](https://user-images.githubusercontent.com/79700810/198209614-7eab206c-1315-4546-9d6e-6ec1e2908735.png)

![image](https://user-images.githubusercontent.com/79700810/198209625-78651d65-3915-43c9-8378-12120a551976.png)

![image](https://user-images.githubusercontent.com/79700810/198209633-bc5c2f09-0174-4637-a162-8e8ac354a312.png)

![image](https://user-images.githubusercontent.com/79700810/198209645-2755f671-953a-44a1-a2b3-ddce5e219bce.png)

![image](https://user-images.githubusercontent.com/79700810/198209661-627ffc0a-aa1d-47b3-a19d-9c0da3791543.png)

![image](https://user-images.githubusercontent.com/79700810/198209669-52fe4a29-2ee3-4569-9a40-325743910c56.png)

![image](https://user-images.githubusercontent.com/79700810/198209688-1b4d4796-69c4-453d-94b2-fc872f613507.png)

![image](https://user-images.githubusercontent.com/79700810/198209735-3f7d74ad-c19e-4c7e-96a5-748aa04b0db6.png)

![image](https://user-images.githubusercontent.com/79700810/198209751-a2678aac-6cb9-47b1-8539-6664f5639612.png)

![image](https://user-images.githubusercontent.com/79700810/198209763-ff433b02-9cd6-4bdb-a094-20fdf4d70674.png)

![image](https://user-images.githubusercontent.com/79700810/198209782-36802a6c-a812-493c-8218-6dba1dace321.png)

![image](https://user-images.githubusercontent.com/79700810/198209793-a9f74cb2-ede8-4968-bf2f-66f59fa3b093.png)


![image](https://user-images.githubusercontent.com/79700810/198209812-062dc9c3-924f-4038-9e9c-af643d465040.png)


![image](https://user-images.githubusercontent.com/79700810/198209830-41ac1661-6a29-4539-bb49-79d3ae8e805e.png)

![image](https://user-images.githubusercontent.com/79700810/198209859-d568a358-2194-45df-a2be-c8430dfebb31.png)

![image](https://user-images.githubusercontent.com/79700810/198209869-4588de0a-e1df-4a82-a197-0ebed7f5a839.png)

![image](https://user-images.githubusercontent.com/79700810/198209891-d26b22c8-3a1c-4945-b52b-3d927fe42b0f.png)


### Настройка шаблона для клонирования 

![image](https://user-images.githubusercontent.com/79700810/198210357-08abe0c4-9b9e-4af1-a546-ee5426e564a8.png)

![image](https://user-images.githubusercontent.com/79700810/198210549-754cf55c-a378-4ad4-ac49-c69ce1cb92ca.png)

Убедиться, что файл /etc/apt/sources.list содержит следующие строки,
при необходимости — добавить, если имеются другие записи, то закомментировать их или удалить

```
nano /etc/apt/sources.list
```

```
deb http://download.astralinux.ru/astra/frozen/1.7_x86-64/1.7.1/repository-base 1.7_x86-64 main non-free contrib

deb http://download.astralinux.ru/astra/frozen/1.7_x86-64/1.7.1/repository-extended 1.7_x86-64 main contrib non-free
```

![image](https://user-images.githubusercontent.com/79700810/198210691-b91d3586-963f-4f4b-b48b-00bcb59a7780.png)

подключить репозиторий aldpro, выполнив в терминале команды

```
echo -e "deb https://download.astralinux.ru/aldpro/stable/repository-main/ 1.0.0 main" | sudo tee /etc/apt/sources.list.d/aldpro.list

echo -e "deb https://download.astralinux.ru/aldpro/stable/repository-extended/ generic main" | sudo tee -a /etc/apt/sources.list.d/aldpro.list
```

![image](https://user-images.githubusercontent.com/79700810/198211039-745b7244-1159-4838-a977-9d308a84344c.png)


добавить конфигурационный файл /etc/apt/preferences.d/aldpro настроек приоритета apt со следующим содержимым:

```
nano /etc/apt/preferences.d/aldpro
```

```
Package: *
Pin: release n=generic
Pin-Priority: 900
```

![image](https://user-images.githubusercontent.com/79700810/198211110-9fa548fb-38a2-4614-a383-fe141de33ba6.png)


обновить пакеты, выполнив в терминале команду

```
apt update
apt upgrade
```


```
apt install -y open-vm-tools
```


![image](https://user-images.githubusercontent.com/79700810/198218196-a81bf25a-ec29-44e9-ad58-6b42be1e9ce4.png)

На сервере, подготовленном для развертывания контроллера домена, необходимо
выполнить в терминале команду

```
DEBIAN_FRONTEND=noninteractive apt-get install -q -y aldpro-mp
```


### Создание виртуальный машины DC1 из шаблона 

![image](https://user-images.githubusercontent.com/79700810/198517553-86aea054-cd50-4613-96f4-34986e6ab5fa.png)


![image](https://user-images.githubusercontent.com/79700810/198517829-ce1d18b6-e7f2-4c51-9677-f74f08b62817.png)

![image](https://user-images.githubusercontent.com/79700810/198517944-fe0302b2-cb18-4ac3-aff0-9837d4be45d5.png)

![image](https://user-images.githubusercontent.com/79700810/198517986-2807697a-9082-4d21-a8b9-0c98df9a7378.png)

![image](https://user-images.githubusercontent.com/79700810/198518104-4314a8d6-df4d-4218-96a1-867c96e0fee1.png)

Добавляем второй интерфейс

![image](https://user-images.githubusercontent.com/79700810/198518159-cb543bf8-84bd-4862-859e-4705d8a9bc67.png)


!!!!!!!!!!!!!!!!!!!!
### DC1
!!!!!!!!!!!!!!!!!!!!
```
nano /etc/hostname
```

```
dc1.domain.test
```

![image](https://user-images.githubusercontent.com/79700810/198520511-77ce0590-9ee4-4fd4-a14e-6a6dd000a0e8.png)


```
nano /etc/hosts
```

```
127.0.0.1 localhost.localdomain localhost
172.30.10.10 dc1.domain.test dc1
127.0.1.1 dc1
```


![image](https://user-images.githubusercontent.com/79700810/198520541-60d40950-91fd-4b56-9d94-c48a332df2ab.png)


```
nano /etc/resolv.conf

```

```
search domain.test
nameserver 127.0.0.1
```

![image](https://user-images.githubusercontent.com/79700810/198520640-079c92c9-4ca3-4d6f-8386-897578f5c777.png)


```
systemctl stop network-manager
systemctl disable network-manager
```

```
nano  /etc/network/interfaces
```

```
auto eth1
iface eth1 inet static
address 172.30.10.10
netmask 255.255.255.0
dns-nameservers 127.0.0.1
dns-search domain.test


auto eth0
iface eth0 inet static
address 172.30.66.24
netmask 255.255.255.0
gateway 172.30.66.1
```

![image](https://user-images.githubusercontent.com/79700810/198520716-97af4b73-d2d6-4b18-b914-7f875bb661ab.png)


```
systemctl restart networking
```
```
sudo /opt/rbta/aldpro/mp/bin/aldpro-server-install.sh -d domain.test -n dc1 -p Passw0rd --ip 172.30.10.10 --no-reboot
```

```
reboot
```

```
iptables -t nat -A POSTROUTING -o eth0  -j MASQUERADE
```

```
nano /etc/sysctl.conf
```

```
net.ipv4.ip_forward=1
```

![image](https://user-images.githubusercontent.com/79700810/198520843-0c64a584-e20e-4922-8724-99406e0241fa.png)

```
sysctl -p
```

![image](https://user-images.githubusercontent.com/79700810/198518839-010cb036-16ed-4c78-918e-ec72a68eb827.png)


!!!!!!!!!!!!!!!!!!!!
### DC2
!!!!!!!!!!!!!!!!!!!!

```
nano /etc/hostname
```

```
dc2.domain.test
```

```
nano /etc/hosts
```

```
127.0.0.1 localhost
127.0.1.1 dc2
```

```
nano /etc/resolv.conf
```

```
search domain.test
nameserver 172.30.10.10
```

```
systemctl stop network-manager
systemctl disable network-manager
```

```
nano  /etc/network/interfaces
```

```
auto eth0
iface eth0 inet static
address 172.30.10.11
netmask 255.255.255.0
gateway 172.30.10.10
dns-nameservers 172.30.10.10
dns-search domain.test
```

```
systemctl restart networking
```

```
sudo /opt/rbta/aldpro/client/bin/aldpro-client-installer -c domain.test -u admin -p Passw0rd -d dc2 -i -f
```

```
reboot
```


После перезагрузки на DC1

![image](https://user-images.githubusercontent.com/79700810/198519150-7e5dc3b1-1812-48da-9810-2bc72aaafc6e.png)


Настройка дополнительного контроллера домена

![image](https://user-images.githubusercontent.com/79700810/198523686-5050e83d-e889-413c-9350-ce44c8f647a5.png)

![image](https://user-images.githubusercontent.com/79700810/198523818-d8b2f20a-d27e-4dd9-af53-6a9bd719df26.png)

Выберете сервер и нажмите сохранить

![image](https://user-images.githubusercontent.com/79700810/198523974-ca9a8024-b629-47d7-9bcc-eac0c6953fd9.png)



!!!!!!!!!!!!!!!!!!!!
### AUDIT
!!!!!!!!!!!!!!!!!!!!

```
nano /etc/hostname
```

```
audit.domain.test
```

```
nano /etc/hosts
```

```
127.0.0.1 localhost
127.0.1.1 audit
```

```
nano /etc/resolv.conf
```

```
search domain.test
nameserver 172.30.10.10
```

```
systemctl stop network-manager
systemctl disable network-manager
```

```
nano  /etc/network/interfaces
```

```
auto eth0
iface eth0 inet static
address 172.30.10.12
netmask 255.255.255.0
gateway 172.30.10.10
dns-nameservers 172.30.10.10
dns-search domain.test
```

```
systemctl restart networking
```

```
sudo /opt/rbta/aldpro/client/bin/aldpro-client-installer -c domain.test -u admin -p Passw0rd -d mon -i -f
```

```
reboot
```

!!!!!!!!!!!!!!!!!!!!
### MON
!!!!!!!!!!!!!!!!!!!!

```
nano /etc/hostname
```

```
mon.domain.test
```

```
nano /etc/hosts
```

```
127.0.0.1 localhost
127.0.1.1 mon
```

```
nano /etc/resolv.conf
```

```
search domain.test
nameserver 172.30.10.10
```

```
systemctl stop network-manager
systemctl disable network-manager
```

```
nano  /etc/network/interfaces
```

```
auto eth0
iface eth0 inet static
address 172.30.10.13
netmask 255.255.255.0
gateway 172.30.10.10
dns-nameservers 172.30.10.10
dns-search domain.test
```

```
systemctl restart networking
```

```
sudo /opt/rbta/aldpro/client/bin/aldpro-client-installer -c domain.test -u admin -p Passw0rd -d mon -i -f
```

```
reboot
```


!!!!!!!!!!!!!!!!!!!!
### SMB
!!!!!!!!!!!!!!!!!!!!

```
nano /etc/hostname
```

```
smb.domain.test
```

```
nano /etc/hosts
```

```
127.0.0.1 localhost
127.0.1.1 smb
```

```
nano /etc/resolv.conf
```

```
search domain.test
nameserver 172.30.10.10
```

```
systemctl stop network-manager
systemctl disable network-manager
```

```
nano  /etc/network/interfaces
```

```
auto eth0
iface eth0 inet static
address 172.30.10.14
netmask 255.255.255.0
gateway 172.30.10.10
dns-nameservers 172.30.10.10
dns-search domain.test
```

```
systemctl restart networking
```

```
sudo /opt/rbta/aldpro/client/bin/aldpro-client-installer -c domain.test -u admin -p Passw0rd -d smb -i -f
```

```
reboot
```


!!!!!!!!!!!!!!!!!!!!
### DHCP
!!!!!!!!!!!!!!!!!!!!

```
nano /etc/hostname
```

```
dhcp.domain.test
```

```
nano /etc/hosts
```

```
127.0.0.1 localhost
127.0.1.1 dhcp
```

```
nano /etc/resolv.conf
```

```
search domain.test
nameserver 172.30.10.10
```

```
systemctl stop network-manager
systemctl disable network-manager
```

```
nano  /etc/network/interfaces
```

```
auto eth0
iface eth0 inet static
address 172.30.10.15
netmask 255.255.255.0
gateway 172.30.10.10
dns-nameservers 172.30.10.10
dns-search domain.test
```

```
systemctl restart networking
```

```
sudo /opt/rbta/aldpro/client/bin/aldpro-client-installer -c domain.test -u admin -p Passw0rd -d smb -i -f
```

```
reboot
```

!!!!!!!!!!!!!!!!!!!!
### REPO
!!!!!!!!!!!!!!!!!!!!

```
nano /etc/hostname
```

```
repo.domain.test
```

```
nano /etc/hosts
```

```
127.0.0.1 localhost
127.0.1.1 repo
```

```
nano /etc/resolv.conf
```

```
search domain.test
nameserver 172.30.10.10
```

```
systemctl stop network-manager
systemctl disable network-manager
```

```
nano  /etc/network/interfaces
```

```
auto eth0
iface eth0 inet static
address 172.30.10.16
netmask 255.255.255.0
gateway 172.30.10.10
dns-nameservers 172.30.10.10
dns-search domain.test
```

```
systemctl restart networking
```

```
sudo /opt/rbta/aldpro/client/bin/aldpro-client-installer -c domain.test -u admin -p Passw0rd -d repo -i -f
```

```
reboot
```

