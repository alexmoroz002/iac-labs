# Лабораторная работа 4

## Цель работы

Поднять сервер OpenVPN использую роль Ansible, протестировать используя Molecule

## Ход работы

1. Написать Ansible Playbook поднимающий OpenVPN сервер
2. Через Molecule инициировать структуру для роли и вынести задачи поднятия сервера, с конфигурацией через переменные
3. При завершении работы плейбук должен разместить в playbook-dir артефактный ovpn-файл для подключения
4. Роль должна проходить стандартные тестами molecule test
5. Плейбук подключает роль через ansible-galaxy

## Запуск

Для запуска требуются компьютер-хост с установленным Ansible, Galaxy, Molecule и целевой сервер для VPN на Ubuntu 20.02+ с установленным OpenSSH. IP сервера должен быть указан в inventory/hosts 

Перед запуском необходимо скачать роль [openvpn](https://gitlab.com/ansible-roles-iac/openvpn), указаннуе в requirements.yaml, используя Ansible Galaxy - ansible-galaxy install -r requirements.yaml

Запуск плейбука осуществляется командой ansible-playbook -i inventory/hosts vpn.yaml

Конфигурация плейбука осуществляется через group_vars в папке с hosts. Конфигурационные параметры openvpn, а также значения по умолчанию можно посмотреть в gitlab по ссылке выше 