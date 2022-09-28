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


Пишем имя зоны из значения ActiveWebProbeHost – msftconnecttest.com (без хоста www)


![image](https://user-images.githubusercontent.com/79700810/192780392-f965b69f-fcb0-4806-a439-6dbeb1b1d6a7.png)


![image](https://user-images.githubusercontent.com/79700810/192780429-39a84bda-1a3f-40ab-9d4b-56710ee3ac18.png)


![image](https://user-images.githubusercontent.com/79700810/192780482-76f0282d-2069-4438-b34f-bb78a8c49b17.png)


Внутри зона создаем А запись


![image](https://user-images.githubusercontent.com/79700810/192781030-0fe5d4a2-0cf2-4265-bea4-a22cdead1101.png)


IIS

![image](https://user-images.githubusercontent.com/79700810/192781173-9b3f46a3-03eb-44b7-962f-161178be2df9.png)

Устанавливаем IIS сервер на DC1 в стандартной комплектации

![image](https://user-images.githubusercontent.com/79700810/192781263-752f8958-afbf-4d37-9a63-aef25feeb87b.png)


![image](https://user-images.githubusercontent.com/79700810/192781336-03589cc1-2274-42be-beb9-33540c1a2a23.png)



![image](https://user-images.githubusercontent.com/79700810/192781434-c000cc18-49ef-45e2-827a-d228678ca51d.png)



![image](https://user-images.githubusercontent.com/79700810/192781491-75122f77-f463-41ba-b2fa-5a6fed01e30a.png)


создаем файл из ActiveWebProbePath – connecttest.txt (аккуратнее с
расширениями файлов)



![image](https://user-images.githubusercontent.com/79700810/192781847-a616ab5d-b333-4426-bb68-3ccc0b8aaffc.png)


![image](https://user-images.githubusercontent.com/79700810/192781916-adb6f2f7-4f79-42ab-978c-d03125461481.png)


Внутри файла пишем из ActiveWebProbeContent – Microsoft Connect Test

![image](https://user-images.githubusercontent.com/79700810/192782086-4cb216b5-2e88-47c7-97cb-18f33675f4ef.png)


создаем сайт 

![image](https://user-images.githubusercontent.com/79700810/192782253-5d8025ed-dd45-4c89-97d5-9b4cf2c0dd85.png)

![image](https://user-images.githubusercontent.com/79700810/192782361-f4188c43-33d1-4b63-b1de-122f439e6b6e.png)



А также прописать в Bindings имя Host name – www.msftconnecttest.com

![image](https://user-images.githubusercontent.com/79700810/192782508-73cb776a-edba-48f2-9dfc-d995e5ae9878.png)

проверяем настройки адаптера 


![image](https://user-images.githubusercontent.com/79700810/192782940-1e4493b7-ccad-4347-bd15-0918f46e49bb.png)


![image](https://user-images.githubusercontent.com/79700810/192783161-4e1a2e7e-d05a-4b38-a6e1-9e0ec313cfac.png)


![image](https://user-images.githubusercontent.com/79700810/192783261-c9268283-b671-4bd8-820a-a7798d14697f.png)



![image](https://user-images.githubusercontent.com/79700810/192783379-8cc8135e-c077-4087-99f8-b906cb571d76.png)


DHCP



![image](https://user-images.githubusercontent.com/79700810/192783508-0b535943-f943-42a6-bfd2-ad57e39f51cf.png)


![image](https://user-images.githubusercontent.com/79700810/192783601-a6073585-c921-4896-a0d7-be8b28c77bcc.png)


![image](https://user-images.githubusercontent.com/79700810/192783659-7835a5cb-2820-4eeb-ae94-e260c0eb7f69.png)


![image](https://user-images.githubusercontent.com/79700810/192783721-9539a12b-88d9-4166-8972-962ca17df1c3.png)




![image](https://user-images.githubusercontent.com/79700810/192783861-a15e8f11-b037-4c99-9cad-152984df3f91.png)


![image](https://user-images.githubusercontent.com/79700810/192783928-6b9726d4-fba4-4c48-ad59-d878719096c0.png)


![image](https://user-images.githubusercontent.com/79700810/192783997-08222646-d16f-47cc-abaa-50a7c62e5941.png)


![image](https://user-images.githubusercontent.com/79700810/192784137-75fa9d9e-6639-4b74-821c-6103d661c2a3.png)


![image](https://user-images.githubusercontent.com/79700810/192784244-c4cff5bc-e3c4-4a07-9e25-b5d8c540a52f.png)


![image](https://user-images.githubusercontent.com/79700810/192784365-a5546f50-34da-4bec-b992-dcc600df07c8.png)


![image](https://user-images.githubusercontent.com/79700810/192784499-9fc2ac26-c56e-47f7-8971-250b4fc7fb56.png)


![image](https://user-images.githubusercontent.com/79700810/192784560-45788f65-d989-4349-9007-22b6cd1b7c37.png)


![image](https://user-images.githubusercontent.com/79700810/192784635-a4081595-3e72-4ed1-b7b8-30acfca47518.png)

![image](https://user-images.githubusercontent.com/79700810/192784712-60fd9032-0250-414d-ac50-93d462c934eb.png)


![image](https://user-images.githubusercontent.com/79700810/192784840-e22144bc-561d-43e4-a5d5-1572908e4b54.png)



![image](https://user-images.githubusercontent.com/79700810/192784899-b5251a97-caf2-4b08-8de2-cc623bd002b4.png)

![image](https://user-images.githubusercontent.com/79700810/192784949-fadd772c-ae8a-47e4-aa77-0d46a27afbbf.png)


![image](https://user-images.githubusercontent.com/79700810/192785002-e5ec2235-e698-41b9-88e0-d647063b116b.png)



## на Виртуальной машине DC2




