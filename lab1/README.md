# Лабораторная работа 1

## **Цель работы**

Запустить приложение при помощи ansible, научиться писать плейбуки и пользоваться group vars

**Docker-образ:** https://hub.docker.com/repository/docker/timurbabs/django

Универсальный файл для вагранта: [Vagrantfile](https://drive.google.com/file/d/1Q5deuz9kcm9VeXDiX44iuHZZSp66VuAY/view?usp=share_link)

## **Ход работы**

1. Установить Ansible используя ([Гайд по установке](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html))
2. Установить Vagrant ([Гайд по установке](https://developer.hashicorp.com/vagrant/downloads))
3. Поднять Vagrant хост из ссылки при помощи файла Vagrantfile используя команду ***vagrant up** ([VagrantFile](https://drive.google.com/drive/u/0/folders/1Ev8N8LijxNR2npEwhoUFlxBuznf--ujP))
4. Написать inventory-файл для развернутых хостов
5. Написать плейбук для установки Docker
6. Клонировать репо ([Репозиторий](https://github.com/mdn/django-locallibrary-tutorial)) на ноды группы [app]
7. Запустить приложение на нодах группы [app] используя ansible

## Запуск

Для запуска требуется минимум один сервер на Ubuntu 20.02+ с установленным OpenSSH. IP серверов должен быть указан в inventory/hosts 

1. Плейбук docker.yaml устанавливает Docker на все ноды и запускается командой ansible-playbook -i inventory/hosts docker.yaml

2. Плейбук app.yaml устанавливает приложение на ноды app и запускается командой ansible-playbook -i inventory/hosts app.yaml