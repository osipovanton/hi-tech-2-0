## Лабараторная работа 1


## Общие требования 




## Базовая конфигурация
|DC1             |DC2             |CLI1             |CLI2           |
| ------------- | ------------- | ------------- |    ------------- | 
|Windows Server 2022 GUI |Windows Server 2022 Core   |Windows 10|Ubuntu            |
|Administartor |Administartor   |Administartor|user           |
|Pa$$w0rd |Pa$$w0rd  |Pa$$w0rd|Pa$$w0rd          |

## Основные службы 
- Active directory
- DNS
- DHCP
- NTP
- SMB
- GPO

## на Виртуальной машине DC1

Базовая конфигурация

![image](https://user-images.githubusercontent.com/79700810/192774459-d9127b04-69eb-40d9-b012-2fdee7b6294f.png)



![image](https://user-images.githubusercontent.com/79700810/192774701-f0ba7741-9e39-47c4-915d-72e89015c24d.png)


![image](https://user-images.githubusercontent.com/79700810/192774857-a67dab66-ef8b-4141-9651-c876142f982a.png)


![image](https://user-images.githubusercontent.com/79700810/192775055-27c5f296-a342-4f58-b8e8-45c96b8097ec.png)


## на Виртуальной машине DC1

ADDS

![image](https://user-images.githubusercontent.com/79700810/192775765-f342c0a5-81a7-4d7a-a16f-a319a3efed7a.png)


![image](https://user-images.githubusercontent.com/79700810/192775831-ad2578e1-6378-4bd6-85b9-5c31090f1c67.png)


![image](https://user-images.githubusercontent.com/79700810/192775910-f860819e-d4e7-4772-97f3-98d0b95beb7b.png)


![image](https://user-images.githubusercontent.com/79700810/192776033-cc05120d-98da-4729-a6f1-6ca74e8fa781.png)


![image](https://user-images.githubusercontent.com/79700810/192776094-9152f917-977a-43a8-ace6-19fd090e64f8.png)


![image](https://user-images.githubusercontent.com/79700810/192776134-62f6411f-6f27-4daf-93db-e9f7395c0b73.png)



ADDS create forest


![image](https://user-images.githubusercontent.com/79700810/192776486-215c3a03-c985-4f37-99e4-cba223a8f3fc.png)

![image](https://user-images.githubusercontent.com/79700810/192776607-ba5868bc-05df-470d-955b-26b17c942df0.png)


![image](https://user-images.githubusercontent.com/79700810/192776797-c9b55ddd-60b0-4763-9a47-d2b3e34062a3.png)

![image](https://user-images.githubusercontent.com/79700810/192776849-b3380698-0868-45e3-abaa-e6b73737cb32.png)

![image](https://user-images.githubusercontent.com/79700810/192776922-4b37e86d-dfbe-4a3d-9769-70c942190520.png)

![image](https://user-images.githubusercontent.com/79700810/192777178-1f55c715-dadd-476e-a789-ccd9226d4d8a.png)


![image](https://user-images.githubusercontent.com/79700810/192778332-b550cca1-8cff-4f29-b65f-11ae950d7492.png)


DNS

![image](https://user-images.githubusercontent.com/79700810/192778412-cbd6bff2-39b3-43d9-9151-a0c73038f75d.png)


Обратная зона 

![image](https://user-images.githubusercontent.com/79700810/192778527-c86bb60b-3517-434c-a3c4-1295f359fb03.png)


![image](https://user-images.githubusercontent.com/79700810/192778636-316123cd-7ac5-4934-96c9-43379c69cf48.png)

![image](https://user-images.githubusercontent.com/79700810/192778697-ee273ce5-38ea-4701-93b4-34923decd2ee.png)


![image](https://user-images.githubusercontent.com/79700810/192778761-9929631e-794c-4006-bd4c-28d153bc041b.png)

![image](https://user-images.githubusercontent.com/79700810/192778805-f26778e1-9047-4183-a3f5-51b7ea8cdf84.png)


![image](https://user-images.githubusercontent.com/79700810/192778869-f20aa2be-fd58-4321-952b-151c67817e17.png)


добавление записи 

![image](https://user-images.githubusercontent.com/79700810/192779005-06d919b5-4860-4e32-ab01-7c159ba78242.png)



Эмуляция доступа в Интернет


![image](https://user-images.githubusercontent.com/79700810/192779162-4cd3cd27-ea39-4803-8b78-45f8e9e26ce3.png)


Создаем новую Primary zone. Не забываем убрать галку о хранении в Active Directory

![image](https://user-images.githubusercontent.com/79700810/192779230-70b06f70-32dc-4ee3-8dc2-bbe280acf1f9.png)


Пишем имя зоны из значения ActiveDNSProbeHost – msftncsi.com (без хоста dns)

![image](https://user-images.githubusercontent.com/79700810/192779324-c092356d-6547-4886-ac66-85dcfc4df1e0.png)


![image](https://user-images.githubusercontent.com/79700810/192779366-0d9c57f0-9681-47ad-9d89-4d5a4a3a64bf.png)


![image](https://user-images.githubusercontent.com/79700810/192779431-29dfe089-e26f-48a4-9659-0273564a4df6.png)


Внутри зона создаем А запись

![image](https://user-images.githubusercontent.com/79700810/192780098-f9ff222c-2a5f-4fbc-b3ff-35fac9e85205.png)


Создаем новую Primary zone. Не забываем убрать галку о хранении в Active Directory

![image](https://user-images.githubusercontent.com/79700810/192779230-70b06f70-32dc-4ee3-8dc2-bbe280acf1f9.png)


Пишем имя зоны из значения ActiveDNSProbeHost – msftncsi.com (без хоста dns)

![image](https://user-images.githubusercontent.com/79700810/192779324-c092356d-6547-4886-ac66-85dcfc4df1e0.png)




