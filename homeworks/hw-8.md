# Домашнее задание

## Обновление моделей

_Цель:_
В этом ДЗ вы будете оборачивать ML-модели в REST-интерфейс и запускать в k8s.

Выполненое задание в документе со скриншотами - [тут](https://disk.yandex.ru/i/hP51wde4hFf9fQ)

Описание/Пошаговая инструкция выполнения домашнего задания:
1. Напишите на python REST API для вашей модели.
При выполнении задания за основу брал форк учебного репо курса - [ссылка](https://github.com/varsey/otus-ml-skel/settings/secrets/actions)
В проектной работе поменяю на своей репо
2. Настройте на github actions CI/CD с тестами, сборкой docker и его публикацией в registry.
Переиспользовал gitflow файл из учебного репо (урок 9), изменил креды для docker hub на свои
3. Создайте k8s манифест для запуска вашего сервиса.
Переиспользовал из проекта
4. Создайте в YC k8s кластер из 3-х узлов.
Развернул согласно инструкции в уроке 39 - подробнее см. pdf со скринами
5. Запустите ваш сервис в k8s и проведите тестирование через публичный API.
Сделал порт-форвард с кластера и дернул предсказание по api - подробнее см. pdf со скринами
