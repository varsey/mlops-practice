## Homework #3
Публичная точка доступа к моему бакету
* **s3://varsey-backet** (я знаю что правильно bucket :)

Создание кластера и перенос в него данных из бакета (pdf со скриншотами):
* https://disk.yandex.ru/d/4nCDKDiQLnOHSQ
На мастерноде запускаю jupyter notebook командой
* jupyter notebook --no-browser --port 8888 -ip=*
Подключаюсь с локального компа к удаленной тачке с jupyter notebook с пробрасыванием портов:
* На локальной тачке запускаю команду для подлючкения к удаленному jupyter notebook с pyspark:
http://localhost:8889/tree `ssh -L 8889:localhost:8888 ubuntu@rc1a-dataproc-m-xxx.mdb.yandexcloud.net`


Токен для подключения взять из консоли мастерноды

Создаем ноутбук со следующим [содержанием](https://github.com/varsey/mlops-practice/blob/main/notebooks/hw-3.ipynb)

* Схема для файла: 
```
`schema = StructType([
    StructField("transaction_id", IntegerType(), True),
    StructField("tx_datetime", StringType(), True),
    StructField("customer_id", IntegerType(), True),
    StructField("terminal_id", IntegerType(), True),
    StructField("tx_amount", DoubleType(), True),
    StructField("tx_time_seconds", IntegerType(), True),
    StructField("tx_time_days", IntegerType(), True),
    StructField("tx_fraud", IntegerType(), True),
    StructField("tx_fraud_scenario", IntegerType(), True)
])
```
* Загружаем файлы
```
data = (
    spark.read.format('csv')
    .options(header='true', inferSchema='true', sep=',')
    .load(['20*.txt'], schema=schema)
)
```
* Проверка на полноту - ищем пропущенные значения, находим в колонке terminal_id меньше одного процента NaN
* Проверка на валидность - ищем строки с датой не по формату - таких нет
* Проверка на консистентность - ищем строки с подозрением на разные единицы измерения. Не нашел
