# python_web_hw8_mongodb
Домашнее задание #8

Первая часть

Исходные данные
У нас есть json файл с авторами и их свойствами: дата и место рождения, краткое описание биографии- `authors.json`.
Также мы имеем следующий json файл с цитатами от этих авторов- `qoutes.json`.

Порядок выполнения
1. Создайте облачную базу данных Atlas MongoDB
2. С помощью ODM Mongoengine создайте модели для хранения данных из этих файлов в коллекциях authors и quotes.
3. При хранении цитат (quotes), поле автора в документе должно быть не строковым значением, а Reference fields полем, где хранится ObjectID из коллекции authors.
4. Напишите скрипты для загрузки json файлов в облачную базу данных.
5. Реализуйте скрипт для поиска цитат по тегу, по имени автора или набору тегов.
Скрипт выполняется в бесконечном цикле и через обычный оператор input принимает команды в следующем формате команда:значение.
Пример:
name:Steve Martin — найти и вернуть список всех цитат автора Steve Martin;
tag:life — найти и вернуть список цитат для тега life;
tags:life,live — найти и вернуть список цитат, где есть теги life или live (примечание: без пробелов между тегами life,live);
exit — закончить выполнение скрипта;
6. Вывод результатов поиска только в формате utf-8;

Дополнительное задание

Подумайте и реализуйте для команд name:Steve Martin и tag:life возможность сокращенной записи значений для поиска, как name:st и tag:li соответственно;
---Выполните кеширование результата выполнения команд name: и tag: с помощью Redis, чтобы при повторном запросе результат поиска брался не из MongoDB базы данных, а из кеша;

ПОДСКАЗКА
Для команд name:st и tag:li используйте регулярные выражения в String queries
