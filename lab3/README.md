# Лабораторная работа 3

## Цель работы

Поднять приложение на Django, используя Nginx для обработки статических файлов и прокси используя роли, научиться шаблонизации конфигураций.

**Django-приложение:** [репо](https://github.com/mdn/django-locallibrary-tutorial)

**Docker-образ:** [https://hub.docker.com/repository/docker/timurbabs/django](https://hub.docker.com/repository/docker/timurbabs/django)

## Ход работы

1. Поднять Vagrant-окружение при помощи файла Vagrantfile, используя команду **vagrant up**
2. Написать роль для установки nginx, запушить в репозиторий и добавить в requirements.yml
3. Подготовить в инвентори шаблон конфигурационного файла для Nginx и для default-сайта, с настройками для отдачи статических файлов
4. Учесть в шаблоне проксирование динамики в контейнер с Django
5. Написать плейбук установки через роли nginx на хосты группы web, и docker на хосты группы app
6. Запустить приложение на хостах группы app или подготовить docker-compose.yml для запуска приложения

## Запуск

Для запуска требуются два сервера на Ubuntu 20.02+ с установленным OpenSSH. IP серверов должен быть указан в inventory/hosts 

Перед запуском необходимо скачать роли [Nginx](https://gitlab.com/ansible-roles-iac/nginx) и [Docker](https://gitlab.com/ansible-roles-iac/docker), указанные в requirements.yaml, используя Ansible Galaxy - ansible-galaxy install -r requirements.yaml

Запуск плейбука осуществляется командой ansible-playbook -i inventory/hosts app.yaml