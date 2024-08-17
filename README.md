# Работа с маракетлейсами OZON и YANDEX MARKET
## OZON
### seller.py
Для работы с данным скриптом вам понадобится `SELLER_TOKEN` и `CLIENT_ID `.
- SELLER_TOKEN - API-ключ Ozon Seller.
- CLIENT_ID - ID клиента.

Данный файл позволяет вам взаимодествовать с площадкой OZON, автоматически обновлять информацию о товарах.

В первую очередь код получает список товаров, которые представлены на OZON вместе с их артикулами. Далее он скачивает остатки часов `Casio` с сайта [timeworld](https://timeworld.ru/) и обновляет данные об остатках в ранее полученном списке от OZON. 

Затем он обновляет цены на основе скаченного файла с остатками. 

Также код учитывает возможные ошибки и избегает их.

Весь код работает автоматически. Он синхронизирует работу с OZON, обновляет цены и остатки товаров.
## YANDEX MARKET
### market.py
Для запуска этого скрипта вам понадобится: `MARKET_TOKEN`, `FBS_ID, DBS_ID`, `WAREHOUSE_FBS_ID`, `WAREHOUSE_DBS_ID`. 
- MARKET_TOKEN — API-ключ продавца Яндекс Маркета.
- FBS_ID - ID продавца, который работает по FBS.
- DBS_ID — ID продавца, который работает по DBS.
- WAREHOUSE_FBS_ID - ID склада товаров продавца, который работает по FBS.
- WAREHOUSE_DBS_ID — ID склада товаров продавца, который работает по DBS. 
  
Данный файл позволяет вам взаимодествовать с площадкой YANDEX MARKET, автоматически обновлять информацию о товарах. Также код написан для двух схем доставик по DBS и FBS. 
>FBS (Fulfillment by Seller — исполнение продавцом). Схема работы, когда поставщик продает товар со своего склада: получает заказ, обрабатывает его, упаковывает и везет до склада маркетплейса, а откуда он уже едет к покупателю.
>DBS (Delivery by Seller — доставка продавцом). При такой форме работы маркетплейс выступает только как витрина. Все остальное поставщик делает самостоятельно: от хранения и упаковки до доставки заказа клиенту в руки.

Цена формируется из файла формата xls, который заранее скачен с сайта [timeworld](https://timeworld.ru/).

Первым делом код скачивает файл с остатками часов `Casio` с сайта [timeworld](https://timeworld.ru/). Далее он получает список оставшихся товаров и их артикулами на площадке YANDEX MARKET. 

Скрипт может отслеживать товары на складке с помощью SKU кода.
>SKU (англ. Stock keeping unit) — это код, состоящий из цифр и букв, который присваивают товарам для отслеживания остатков на складе, подсчета продаж по группам и категориям товаров и для определения оптимального момента для следующих закупок.

Затем он сверяет информацию с ранее скаченным файлом и обновляет данные о товарах: остатки товара и цену.
