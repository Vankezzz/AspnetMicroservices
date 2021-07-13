Добавление Mongo DB в проект:
1. Удостовериться, что установлен докер (проверить командой `docker ps`)
2. Скачать образ Mongo DB https://hub.docker.com/_/mongo с помощью команды `docker pull mongo`
3. Запустить образ `docker run -d -p 27017:27017 --name shopping-mongo mongo`:
shopping-mongo - имя контейнера (обращаемся к нему при работе)
mongo - образ Mongo DB
Опракидываем на 27017 порт
4. Проверяем, запущен ли он `docker ps`

Вспомогательные команды:

Для докера
1. `docker logs -f shopping-mongo` - смотрим логи 
2. `docker exec -it shopping-mongo /bin/bash` - заходим внутрь и запускаем баш (терминал)
``
``

Баш
1. `ls`
``
``
``

Для работы с Mongo DB
1. `mongo` - входим в Mongo DB, вызывается из терминала
2. `show dbs` или `show collections` - показывает все базы данных или коллекции
3. `use CatalogDb` - создаем базу данных CatalogDb
4. `db.createCollection('Products')` - создаем коллекцию Products 
5. `db.Products.insertMany([{ 'Name':'Asus Laptop','Category':'Computers', 'Summary':'Summary', 'Description':'Description', 'ImageFile':'ImageFile', 'Price':54.93 }, { 'Name':'HP Laptop','Category':'Computers', 'Summary':'Summary', 'Description':'Description', 'ImageFile':'ImageFile', 'Price':88.93 } ])` - Добавление записей
6. `db.Products.find({}).pretty()` - просмотр всех записей из коллекции Products
7. `db.Products.remove({})` - удаление всех записей из коллекции Products

API документ 
![alt text](https://github.com/Vankezzz/AspnetMicroservices/blob/main/screenshots/catalog_api_doc.PNG "Описание работы сервиса")

Nuget:
1. MongoDB.Driver
2. Swashbuckle.AspNetCore
