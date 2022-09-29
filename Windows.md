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
- RAID1

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


![image](https://user-images.githubusercontent.com/79700810/192785825-e17e6927-85c0-4973-af2c-742f2685cf5a.png)


![image](https://user-images.githubusercontent.com/79700810/192785918-dab19276-6464-44f6-988d-1cdf5a72c5be.png)


![image](https://user-images.githubusercontent.com/79700810/192786056-3e02e383-d3e5-4925-a20f-a2da5d232014.png)



![image](https://user-images.githubusercontent.com/79700810/192786208-22961e4c-c1d6-4c08-88c4-2ff25d5c0564.png)


![image](https://user-images.githubusercontent.com/79700810/192786462-83a49c96-6416-4b02-ba6c-21b7c7e792b0.png)


![image](https://user-images.githubusercontent.com/79700810/192786547-9467b470-cf07-4874-a94e-5f12d3effc9b.png)


![image](https://user-images.githubusercontent.com/79700810/192787155-3aae47e6-20cf-4730-b5ec-07c531dd30a7.png)


на DC1

![image](https://user-images.githubusercontent.com/79700810/192787330-88324207-4687-49db-8057-1ef9a5557122.png)


![image](https://user-images.githubusercontent.com/79700810/192787435-50062df9-c8d6-449a-850d-def4f33352c5.png)



ADDS RODS

![image](https://user-images.githubusercontent.com/79700810/192787592-0762e19a-2e7e-4d45-bfbd-8ede2996cd29.png)


![image](https://user-images.githubusercontent.com/79700810/192787663-246b3bb1-b3d9-4955-9870-00a0586cd004.png)


![image](https://user-images.githubusercontent.com/79700810/192787730-626f58b2-7bc8-4920-838c-3b281cf2c7a9.png)


![image](https://user-images.githubusercontent.com/79700810/192787825-0abd64ab-e90a-4d29-8d1f-9ec3e197a056.png)

![image](https://user-images.githubusercontent.com/79700810/192787899-834671d9-dedf-4e16-a88c-195c686f8078.png)


![image](https://user-images.githubusercontent.com/79700810/192787946-f853b60d-699a-4ef1-a06d-eda1b9f3190e.png)




![image](https://user-images.githubusercontent.com/79700810/192788139-c3f524a1-c656-4045-9a99-dbce31d82ccd.png)




![image](https://user-images.githubusercontent.com/79700810/192788324-68b432b6-3497-4343-98ff-48b5e5f47b15.png)

![image](https://user-images.githubusercontent.com/79700810/192788470-4e58d086-b22c-4647-8892-772d1c9eab01.png)

![image](https://user-images.githubusercontent.com/79700810/192788534-0c4f314a-bf52-42a2-b5a7-de34d44a3931.png)


![image](https://user-images.githubusercontent.com/79700810/192788627-2485793e-c9f9-491d-b653-d255889e0c13.png)


![image](https://user-images.githubusercontent.com/79700810/192788695-c67ea5d7-ea7d-42d7-ae3f-b4b160f8c334.png)




DHCP Over

![image](https://user-images.githubusercontent.com/79700810/192985784-bd2a6d9f-a90f-4895-b8af-3ef44ea9d60e.png)


![image](https://user-images.githubusercontent.com/79700810/192985959-62b0fb50-8ec5-4c7f-a02b-de02a39e4e5e.png)

![image](https://user-images.githubusercontent.com/79700810/192986220-95d2a2a8-4d59-4716-8452-0344fca0c660.png)


![image](https://user-images.githubusercontent.com/79700810/192986321-e7c9672e-0f62-4d4c-a27f-e38f8bb9e946.png)


![image](https://user-images.githubusercontent.com/79700810/192986585-2ec699fa-31ad-4a55-b19f-5af90dccfd68.png)


![image](https://user-images.githubusercontent.com/79700810/192986648-fd5255ed-8ab3-4e42-9227-e3d0a33adaff.png)



![image](https://user-images.githubusercontent.com/79700810/192986744-643b6be7-5262-47b1-91c7-b03371718cd2.png)



![image](https://user-images.githubusercontent.com/79700810/192987009-0360e5b9-4c0a-43c3-adc5-1b3f3bf396ec.png)



![image](https://user-images.githubusercontent.com/79700810/192987195-8e15aab7-b5fd-45c0-81a9-64657e221ed4.png)


![image](https://user-images.githubusercontent.com/79700810/192987297-9ed2d226-2618-4fab-842b-fa4bb3056a06.png)


![image](https://user-images.githubusercontent.com/79700810/192987368-3ebf9c75-6b08-4c5e-a650-7d33a5db9032.png)


![image](https://user-images.githubusercontent.com/79700810/192987499-97476fc5-b451-4d49-bff6-29f40051c319.png)


![image](https://user-images.githubusercontent.com/79700810/192987583-3c886f63-a67a-43cc-89eb-4e8723c0e6a7.png)

![image](https://user-images.githubusercontent.com/79700810/192987654-a1575969-6d82-48f8-9f05-0a9fcbc94f4f.png)


RAID1

![image](https://user-images.githubusercontent.com/79700810/192977608-312914fd-6cf7-455c-a2c8-3661e7812656.png)


![image](https://user-images.githubusercontent.com/79700810/192977721-18275b79-7c3b-4e5e-b7be-7a9221fba850.png)


![image](https://user-images.githubusercontent.com/79700810/192977874-cd49c81a-3b45-4e97-a9eb-7a0a9fdec078.png)


![image](https://user-images.githubusercontent.com/79700810/192977950-2a6f8794-39df-40d5-949a-5c07e90e574e.png)


![image](https://user-images.githubusercontent.com/79700810/192978114-6c11af07-91a3-4687-8819-102b23550a49.png)



![image](https://user-images.githubusercontent.com/79700810/192978189-3f02ffa5-8ee4-46bb-acfa-4237562469a1.png)



![image](https://user-images.githubusercontent.com/79700810/192978243-f019f4e1-1241-4fbb-9f79-c4a7f6c4b661.png)


![image](https://user-images.githubusercontent.com/79700810/192978355-e2cbfafa-d67b-4e79-92fc-ad01d0801ec8.png)


![image](https://user-images.githubusercontent.com/79700810/192978420-0b08922d-132d-4e8f-8e4c-739039b25133.png)


![image](https://user-images.githubusercontent.com/79700810/192978514-3e315e99-950d-4ed3-8360-ce914350d699.png)


![image](https://user-images.githubusercontent.com/79700810/192978579-665bf99e-7877-40de-926c-c6b839a4c9dd.png)


![image](https://user-images.githubusercontent.com/79700810/192978652-7642a36a-a009-4ab3-a1f8-6511f3274604.png)



![image](https://user-images.githubusercontent.com/79700810/192978720-785aa9ba-588a-47fe-a52d-03685620d81a.png)


![image](https://user-images.githubusercontent.com/79700810/192978781-8ac363f3-fe49-41c6-8c69-3b5d87c68884.png)


![image](https://user-images.githubusercontent.com/79700810/192978829-59b3284e-a260-4fc3-956d-3e8f7bbb8569.png)



format 

![image](https://user-images.githubusercontent.com/79700810/192979075-65a1b290-0078-425e-b3e2-10edee807508.png)


![image](https://user-images.githubusercontent.com/79700810/192979179-8b3c7aaa-abd3-4f36-8391-14bf48b247b1.png)


![image](https://user-images.githubusercontent.com/79700810/192979239-732dfc88-7eca-4a22-9432-07c6715508f6.png)


![image](https://user-images.githubusercontent.com/79700810/192979303-9eafbbdb-8d15-4086-9417-70b7ac15588e.png)


![image](https://user-images.githubusercontent.com/79700810/192979478-e1113b36-4b88-40ef-bd91-3bed0839fba1.png)


![image](https://user-images.githubusercontent.com/79700810/192979656-521bb0e2-7928-49c1-8edd-ca4c1cbe6b38.png)





ADDS USERS and GROUP

![image](https://user-images.githubusercontent.com/79700810/192981603-d3dbaa7a-0dc0-4024-9395-6953db528d1e.png)


![image](https://user-images.githubusercontent.com/79700810/192981856-209bdfaa-eb04-40b6-bc44-2b90b0736455.png)



![image](https://user-images.githubusercontent.com/79700810/192981961-237a8726-0747-44a7-91e5-52f67b760cfd.png)


по аналогии

![image](https://user-images.githubusercontent.com/79700810/192982592-c7d71817-c3c3-4e57-9cbf-f566aad04645.png)



![image](https://user-images.githubusercontent.com/79700810/192982755-81d79fde-bfe5-4e3f-94c8-5f43070031fc.png)

![image](https://user-images.githubusercontent.com/79700810/192984292-50a876d5-6df7-4814-8610-8fe21c1feb38.png)


![image](https://user-images.githubusercontent.com/79700810/192984664-683e872b-f727-4fc0-8886-662912cedca0.png)



SMB

![image](https://user-images.githubusercontent.com/79700810/192979894-691daefe-6459-43e0-8580-50fc32ae4661.png)


![image](https://user-images.githubusercontent.com/79700810/192980021-3f2f4610-4ff1-4f0a-a3e2-e4923b5abfed.png)


![image](https://user-images.githubusercontent.com/79700810/192980307-5dbbeac3-ede8-4d1b-b75a-a8be88f50c69.png)



![image](https://user-images.githubusercontent.com/79700810/192980494-652cc995-1f06-422c-9d78-3f14365ed4dc.png)


![image](https://user-images.githubusercontent.com/79700810/192980594-3cf15eb8-6c14-4831-a224-a2b7aa30f31c.png)



![image](https://user-images.githubusercontent.com/79700810/192980965-353287fa-889d-406a-be49-7174a6b7be95.png)

![image](https://user-images.githubusercontent.com/79700810/192981336-68a36e26-7983-4ef2-a84d-7c02d519ad53.png)



![image](https://user-images.githubusercontent.com/79700810/192984859-9c6ebb00-88aa-4d93-9513-03100ce34cb3.png)


![image](https://user-images.githubusercontent.com/79700810/192984960-563040af-7ffc-446f-b846-fc60084e9bb8.png)


![image](https://user-images.githubusercontent.com/79700810/192985139-ef17deeb-6cdd-43aa-b47f-548dc3a14bbb.png)


![image](https://user-images.githubusercontent.com/79700810/192985260-805d1a17-966c-46a5-aa33-e126090f0e11.png)



![image](https://user-images.githubusercontent.com/79700810/192985337-da6c3b5e-fd2e-4754-b42d-014b431d2290.png)


![image](https://user-images.githubusercontent.com/79700810/192985418-14fc2b35-189b-4ea2-926b-d0a420092e57.png)



GPO

![image](https://user-images.githubusercontent.com/79700810/192988740-a4e36cb6-05e5-4133-9943-491844b12c44.png)


![image](https://user-images.githubusercontent.com/79700810/192989727-e920704a-e665-4d10-906c-c3273ea13673.png)






