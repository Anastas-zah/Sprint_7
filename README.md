# Тема "API тестирование" курс ЯндексПрактикум | Sprint_7
Для тестирования был выбран сервис [ЯндексСамокат](https://qa-scooter.praktikum-services.ru/) | [API ЯндексСамокат](https://qa-scooter.praktikum-services.ru/docs/)
> Почасова/посуточная аренда самокатов. С возможностью доставки самоката до метро.

В связи с грядущим релизом был создан чек лист по функционалу:

#### [Создание курьера](tests/test_create_courier.py)
- Успешное создание курьера
- Нельзя создать двух одинаковых курьеров
- Для создания курьера требуется передать все обязательные поля
- При успешном создании запрос возвращает правильный код ответа 
- Если нет одного из обязательных полей, возращает ошибку

#### [Логин курьера](tests/test_login_courier.py)
- Курьер может авторизоваться
- Успешный завпрос возвращает id
- Для авторизации требуется передать все обязательные поля
- Возврат ошибки при авторизации с некорректными данными: 
  - Некорректный логин
  - Некорректный пароль
  - Нет какого либо обязательного поля
  - Несуществующий курьер

#### [Создание заказа](tests/test_create_order.py)
- При создании заказа можно указать: 
  - Можно указать один из цветов - BLACK or GREY
  - Можно указать оба цвета
  - Можно не указывать цвета 
  - Тело ответа содержит track

#### [Список заказов](tests/test_list_orders.py)
- При запросе к ручке "Список заказов" возвращается список всех заказов

---
Перед работой с репозиторием требуется установить зависимости 
``` shell
pip3 install -r requirements.txt
```
Запустить все тесты из директории tests
```shell
pytest tests --alluredir=allure_results
```
Посмотреть отчет в веб версии пройденного прогона
```shell
allure serve allure_results
```