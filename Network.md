# Лабораторная работа 3

Задание:

1. Вы заказали инстансы (SRV1,SRV2,SRV3) и облачные маршрутизаторы Cisco у облачного сервиса

Инстансы находятся в регионах (region1, region2, region3). Так же вам нужно настроить DNS имя для приложения (ht2022.wsr.), которое, ссылается на Load Balancer.

![image](https://user-images.githubusercontent.com/79700810/195075466-278cb40f-5af2-4365-87a9-32069aea3c4f.png)

2. Вашей задачей является - настроить VPN между R1,R2,R3.
3. На SRV1,SRV2,SRV3 создайте одностраничный сайт.
4. На LoadBalancer настройте nginx, так что бы при обращении клиента к mycorp.ru открывался работающий инстанс. Приорететы - SRV1, затем SRV2, затем SRV3.


| Region 1              | Region 2              | Region 3              | Cloud services |
| -------------         | -------------         | -------------         | -------------  |
|R1 - DHCP provider     |R1 - DHCP provider     |R1 - DHCP provider     |Load Balancer   |
|r1.ht2022.wsr          |r2.ht2022.wsr          |r3.ht2022.wsr          |DNS           |
|GW - IP Cloud services |GW - IP Cloud services |GW - IP Cloud services |Application DNS - ht2022.wsr|

## Базовая Конфигурация Cloud services
### Обновление и установка пакетов

```
sudo -i
apt update 
apt install -y nginx
apt install -y bind9
```

### Имя
```
hostnamectl set-hostname CloudServices
```

### Настройка пропускания трафика
```
nano /etc/sysctl.conf
```

net.ipv4.ip_forward=1

![image](https://user-images.githubusercontent.com/79700810/195077066-d3156a00-bae3-4875-af8f-9a3e02458126.png)

  
```
sysctl -p
```

## Базовая Конфигурация R1, R2, R3

### ip address 192.168.255.153 - CloudServices

| R1              | R2             |R3             | 
| -------------         | -------------         | -------------         |
|en      |en      |en      |
|conf t|conf t|conf t|
|hostname R1      |hostname R2      |hostname R3      |
|interface gigabitethernet 0/0      |interface gigabitethernet 0/0      |interface gigabitethernet 0/0      |
|no shutdown      |no shutdown      |no shutdown      |
|ip address dhcp      |ip address dhcp      |ip address dhcp      |
|exit      |exit     |exit      |
|interface gigabitethernet 0/1      |interface gigabitethernet 0/1    |interface gigabitethernet 0/1      |
|no shutdown      |no shutdown      |no shutdown      |
|ip address 192.168.11.1 255.255.255.0      |ip address 192.168.12.1 255.255.255.0     |ip address 192.168.13.1 255.255.255.0      |
|exit      |exit     |exit      |
|ip route 0.0.0.0 0.0.0.0 192.168.255.153 |ip route 0.0.0.0 0.0.0.0 192.168.255.153      |ip route 0.0.0.0 0.0.0.0 192.168.255.153      |



## Настройка DHCP
### ip address 192.168.255.153 - CloudServices

| R1              | R2             |R3             | 
| -------------         | -------------         | -------------         |
|ip dhcp pool SRV1    |ip dhcp pool SRV2     |ip dhcp pool SRV3  |
|network 192.168.11.0 255.255.255.0    |network 192.168.12.0 255.255.255.0     |network 192.168.13.0 255.255.255.0  |
|default-router 192.168.255.153    |default-router 192.168.255.153     |default-router 192.168.255.153  |
|dns-server 192.168.255.153    |dns-server 192.168.255.153     |dns-server 192.168.255.153  |


## Настройка NAT R1, R2, R3

### ip address 192.168.11.2   -   SRV1
### ip address 192.168.12.2   -   SRV2
### ip address 192.168.13.2   -   SRV3
### ip address 192.168.255.82 -   R1 G0/0 
### ip address 192.168.255.2 -   R2 G0/0 
### ip address 192.168.255.209 -   R3 G0/0 

| R1              | R2             |R3             | 
| -------------         | -------------         | -------------         |
|interface Gi0/1    |interface Gi0/1     |interface Gi0/1  |
|ip nat inside    |ip nat inside     |ip nat inside  |
|!    |!     |!  |
|interface Gi0/0    |interface Gi0/0     |interface Gi0/0  |
|ip nat outside    |ip nat outside     |ip nat outside  |
|!    |!     |!  |
|access-list 1 permit 192.168.11.0 0.0.0.255    |access-list 1 permit 192.168.12.0 0.0.0.255     |access-list 1 permit 192.168.13.0 0.0.0.255  |
|ip nat inside source list 1 interface Gi0/0 overload    |ip nat inside source list 1 interface Gi0/0 overload     |ip nat inside source list 1 interface Gi0/0 overload |
|!    |!     |!  |
|ip nat inside source static tcp 192.168.11.2 80 10.10.11.1 80    |ip nat inside source static tcp 192.168.12.2 80 192.168.255.2 80     | ip nat inside source static tcp 192.168.13.2 80 192.168.255.209 80  |



## Базовая Конфигурация SRV1, SRV2, SRV3

| SRV1              | SRV2             |SRV3             | 
| -------------         | -------------         | -------------         |
| sudo -i           | sudo -i             |sudo -i           | 
| apt update            | apt update             |apt update           | 
| apt install -y nginx            | apt install -y nginx             |apt install -y nginx          | 
| echo SRV1 > /var/www/html/index.html           | echo SRV2 > /var/www/html/index.html             |echo SRV3 > /var/www/html/index.html           | 
| systemctl reload nginx            | systemctl reload nginx             |systemctl reload nginx           | 














