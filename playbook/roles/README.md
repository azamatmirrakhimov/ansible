# Шаг 1: Создание структуры роли
Сначала создадим структуру роли с помощью команды Ansible:

~~~
ansible-galaxy init vsftpd_role
~~~
# Шаг 2: Определение задач установки и запуска vsftpd
Отредактируем файлы в директории нашей роли.
2.1 Отредактируйте vsftpd_role/tasks/main.yml
~~
---
# tasks file for vsftpd_role

- name: Install vsftpd package
  apt:
    name: vsftpd
    state: present

- name: Start vsftpd service and enable it on boot
  service:
    name: vsftpd
    state: started
    enabled: yes
~~~
