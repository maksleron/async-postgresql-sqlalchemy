На базе asyncio с использованием fastapi, postgresql и sqlalсhemy был реализован эндпоинт REST API с одной моделью, позволяющий создавать, менять и фильтровать данные.

Запуск: 
    uvicorn --port 8000 --host 127.0.0.1 main:app --reload

Примеры команд на curl для работы с эндпоинтами:

Добавление записи в БД:
    curl -X POST "http://localhost:8000/notes/" ^
    -H "accept: application/json" ^
    -H "Content-Type: application/json" ^
    -d "{\"text\":\"Get Groceries from the store\",\"completed\":false}"

Фильтрация данных из БД по id:
    curl -X GET "http://localhost:8000/notes/2/"

Обновление данных в БД по указанному id:
    curl -X PUT "http://localhost:8000/notes/2/" ^
    -H "accept: application/json" ^
    -H "Content-Type: application/json" ^
    -d "{\"text\":\"Plan a lavish dinner at Restaurant\",\"completed\":true}"