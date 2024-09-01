# StaticJinjaDocker
Используется Docker для запуска [следующего проекта StaticJinjaPlus](https://github.com/MrDave/StaticJinjaPlus/tree/main)
## Требовании
1. ПО Docker (любая верция)
2. ПО Git (любая верция)
## Скачивание проекта 
* ### на основе Ubuntu
```shell
sudo docker pull elzig1999/static-jinja-plus:1.0u
```
Запуск
```shell
sudo docker run -it elzig1999/static-jinja-plus:1.0u
```
* ### на основе slim
```shell
sudo docker pull elzig1999/static-jinja-plus:1.0-slim
```
Запуск
```shell
sudo docker run -it elzig1999/static-jinja-plus:1.0-slim
```
## Запуск с параметрами 
Можно указывать путь к шаблонам при запуске проекта `srcpath`
<br>
Параметр:
*`TEMPLATE_FOLDER` - путь к  шаблонам
```shell
sudo docker run -e **TEMPLATE_FOLDER**=<ВАШ_ПУТЬ_К_ШАБЛОНАМ> <ОБРАЗ>
```
Где:
* Образ - ранее загруженый образ
# Самостоятельная сборка
Это инструкция для самостоятельной сборки
## Зависимости (Образы)
### Для установки на основе Ubuntu
* ubuntu:24.10
### Для установки на основе slim
* python:3.11-slim
## Файлы docker для сборки
Склонируете репозиторию в свою директорию
```shell
git clone https://github.com/ZiganshinIB/StaticJinjaDocker.git
cd StaticJinjaDocker
```
В репозитории есть уже готовые файлы для сборки
* `Dockerfile_ubuntu` - для сборки на Ubuntu
* `Dockerfile_slim` -  для сборки на slim
Выберите 1 из них и перименуйте в `Dockerfile`
## Сборка
Соберем образ. Для примера назову образ `static-jinja-plus`
```shell
sudo docker build --build-arg STATIC_JINJA_VERSION=<ВЕТКА> -t static-jinja-plus .
```
* `STATIC_JINJA_VERSION` - опцианальный параметр ветка в репозитории https://github.com/MrDave/StaticJinjaPlus.git
