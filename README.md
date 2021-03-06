# test-task-for-reiffeisen
POST /api/socks/income
Регистрирует приход носков на склад.

Параметры запроса передаются в теле запроса в виде JSON-объекта со следующими атрибутами:

color — цвет носков, строка (например, black, red, yellow);
cottonPart — процентное содержание хлопка в составе носков, целое число от 0 до 100 (например, 30, 18, 42);
quantity — количество пар носков, целое число больше 0.

POST /api/socks/outcome
Регистрирует отпуск носков со склада. Здесь параметры и результаты аналогичные, но общее количество носков указанного цвета и состава не увеличивается, а уменьшается.

GET /api/socks
Возвращает общее количество носков на складе, соответствующих переданным в параметрах критериям запроса.

Параметры запроса передаются в URL:

color — цвет носков, строка;
operation — оператор сравнения значения количества хлопка в составе носков, одно значение из: moreThan, lessThan, equal;
cottonPart — значение процента хлопка в составе носков из сравнения.

Сервис размещен на Heroku: https://socks-service.herokuapp.com/
