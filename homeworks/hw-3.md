## Homework #3
Публичная точка доступа к моему бакету
* **s3://varsey-backet** (я знаю что правильно bucket :)

Создание кластера и перенос в него данных из бакета (pdf со скриншотами):
* https://disk.yandex.ru/d/4nCDKDiQLnOHSQ
На мастерноде запускаю jupyter notebook командой
* jupyter notebook --no-browser --port 8888 -ip=*
Подключаюсь с локального компа к удаленной тачке с jupyter notebook с пробрасыванием портов:
* ssh -L 8889:localhost:8888 ubuntu@rc1a-dataproc-m-g0qze60v8hlzfvcr.mdb.yandexcloud.net
На локальной тачке запускаю команду для подлючкения к удаленному jupyter notebook с pyspark
* http://localhost:8889/tree
Токен для подключения взять из консоли мастерноды
