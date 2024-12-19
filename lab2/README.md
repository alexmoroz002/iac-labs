# Лабораторная работа 2

## **Цель работы**

Научиться пользоваться Ansible Galaxy и писать роли

## **Ход работы**

1. Инициировать структуру роли “**Docker**” через Ansible-Galaxy
2. Вынести из предыдущего плейбука задачи установки Docker в отдельную роль
3. Параметризовать роль через переменные
4. Создать в gitlab группу для репозиториев с ролями, запушить роль “**Docker**” в репозиторий
5. Создать файл requirements.yml для установки роли Docker из репозитория
6. Запустить приложение на нодах группы [app] используя ansible-playbook с ролью “**Docker**”

## Запуск

Для запуска требуется минимум один сервер на Ubuntu 20.02+ с установленным OpenSSH. IP серверов должен быть указан в inventory/hosts 

Перед запуском необходимо скачать роль [Docker](https://gitlab.com/ansible-roles-iac/docker), указанную в requirements.yaml, используя Ansible Galaxy - ansible-galaxy install -r requirements.yaml

1. Плейбук docker.yaml устанавливает роль Docker на все ноды и запускается командой ansible-playbook -i inventory/hosts docker.yaml

2. Плейбук app.yaml устанавливает приложение на ноды app и запускается командой ansible-playbook -i inventory/hosts app.yaml