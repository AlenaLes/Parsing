# Парсинг данных по продуктам на сайте.

## Краткое описание
Скрипт был написан в рамках реальной задачи для [АШАН](https://www.auchan.ru/).
Во время выполнения были выгружены артикула и наименования товаров с сайта для формирования актуальной базы по товарам на сайте и для сопоставления с имеющимися базами данных.

Задачи:
- Создать срипт для парсинга сайта;
- Выгрузить массив данных с артикулами и наименованиями товаров;
- Выгрузить существующую базу по товарам с помощью SQL;
- Объединение таблиц для добавления навигационных столбцов;
- Загрузка полученного результата в базу.

Проект выполнен с нуля и предназначен только для выгрузки определенных данных.

Результаты:
- Создан рабочий код для конкретной задачи;
- Финальные данные используются при проведении маркетинговых акций. Можно быстро получить данные по требуемым категориям.

Полный скрипт расположен в файле "Parsing_auchan.ipynb".

Стэк:

- Python
- SQL
- Parsing
- HTML

## Библиотеки для работы с Python, SQL и Запросами на сайт.

```
import requests
from bs4 import BeautifulSoup
import pandas as pd
import math
from tqdm import tqdm
import time
import os,  glob
import csv
from requests.packages.urllib3.exceptions import InsecureRequestWarning
requests.packages.urllib3.disable_warnings(InsecureRequestWarning)
import psycopg2
from sqlalchemy import create_engine
```

## Библиотеки для оформлени кода

```
import ipywidgets as wi
from ipywidgets import IntProgress
```

Полученные выгрузки не выкладываются в общий доступ из-за конфеденциальности. Также скрыты все доступы для подключения к базам.
_________________________________

## Процесс

Для подключения использовалась бибилотека BeautifulSoup. Все этапы получения данных раздеены на блоки, чтобы весь процесс был более отслеживаемым и наглядным.

В связи с тем, что процесс парсинга может занимать довольно длительное время на каждом этапе request-ов добавлен виджет с процентами загрузки данных, а также простой подсчет оставшегося времени получения выгрузки.
_________________________________

## Финальный результат

Итоговая таблица, загружаемая обрано в базы данных, выглядит следующим образом: 

![1](https://github.com/AlenaLes/Parsing/assets/100629361/66341ce8-a6f3-4a68-bc62-ac4d63b2e71e)

