Добавление Redis в проект:
1. Удостовериться, что установлен докер (проверить командой `docker ps`)
2. Скачать образ Redis https://hub.docker.com/_/redis с помощью команды `docker pull redis`
3. Запустить образ `docker run -d -p 6379:6379 --name aspnetrun-redis redis`:
aspnetrun-redis - имя контейнера (обращаемся к нему при работе)
redis - образ Redis
Опракидываем на 6379 порт
4. Проверяем, запущен ли он `docker ps`



Для работы с Redis
1. `redis-cli` - входим в redis, вызывается из терминала (предварительно войти в контейнер `docker exec -it aspnetrun-redis /bin/bash`)
2. `set key value` - мы создаем пару ключ-значение (key:value); для получения этого значения исполняем `get key`
3. Настройка строки поключения в appsettings.json
```

API документ 
![alt text](https://github.com/Vankezzz/AspnetMicroservices/blob/main/screenshots/basket_api_doc.PNG "Описание работы сервиса")

Nuget:
```
<ItemGroup>
    <PackageReference Include="Microsoft.Extensions.Caching.StackExchangeRedis" Version="5.0.1" />
    <PackageReference Include="Newtonsoft.Json" Version="13.0.1" />
    <PackageReference Include="Swashbuckle.AspNetCore" Version="5.6.3" />
 </ItemGroup>
```

Использованные паттерны:
1. N-layer архитектура
2. CRUD / Repository паттерны для работы с базой данных