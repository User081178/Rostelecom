Дипломный проект: реальный кейс компании «Ростелеком Информационные Технологии»

Автоматизированное тестирование страницы https://b2c.passport.rt.ru сайта "Ростелеком"

Чек-лист/Тест-кейсы/Баг-репорты:

https://drive.google.com/drive/folders/1iRojAwDoAM8N0Of431DK6J0S8t1c5B3H?usp=sharing

Автоматизированные тесты.

Для тестирования сайта были использованы:

 - анализ граничных значений;
 - разбиение на классы эквивалентности;
 - тестирование состояний и переходов.

Используемые при тестировании библиотеки PyCharm:

requests
python-dotenv
pytest
selenium
faker

Запуск тестов через команду в консоли:

pytest -v --driver Chrome --driver-path ./chromedriver.exe


//ВАЖНО//:

Для страниц восстановления пароля в позитивных и негативных тестах необходимо вводить символы с картинки "капчи" в поле для ввода, задержка по времени для ввода настроена автоматически. 

Для проверки авторизации по почте и паролю, так же потребуется ввод "капчи" вручную.

Для генерации временного адреса электронной почты использовался сайт www.1secmail.com

Проект содержит две папки pages и tests, а так же файлы conftest.py и pytest.ini.

conftest.py - фикстура для работы с браузером.

pytest.ini - маркеры для параметризации.



Папка /pages:

registration_email.py - GET-запросы к виртуальному почтовому ящику для получения валидного email и кода для регистрации на сайте и восстановления пароля;

config.py - исходные статические данные;

auth.py - функции-обертки для локаторов, распределенные по классам в зависимости от тематики тестов;

base.py - функции для применения к локаторам явных ожиданий, получения главной страницы сайта и пути текущей страницы;

locators.py - XPath- и CSS-локаторы web-элементов сайта;

settings.py - данные, используемые в процессе теста.



Папка /tests:

test_registr_positive - позитивные тесты страницы регистрации;

test_auth_page_positive - позитивные тесты страницы авторизации;

test_new_password_positive - позитивные тесты страницы восстановления пароля;

test_registr_positive - позитивные тесты страницы регистрации;

test_auth_page_negative - негативные тесты страницы авторизации;

test_new_password_negative - негативные тесты страницы восстановления пароля.
