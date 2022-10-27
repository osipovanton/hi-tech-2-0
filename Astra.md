## Лабораторная работа 5


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


### Настройка шаблона для слонирования 

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

На сервере, подготовленном для развертывания контроллера домена, необходимо
выполнить в терминале команду

```
DEBIAN_FRONTEND=noninteractive apt-get install -q -y aldpro-mp
```

