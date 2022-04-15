# Лабораторная работа №8
#### 
## Задачи:

* Создать отказоустойчевый кластер с помощью __consul__ и __patroni__


## Дано:
* Vagrantfile, который состоит из:
  + pg1, pg2 - сервера
  + dcs1, dcs2, dcs3 - диски
* Готовая роль consul.play
* inventory
* ansible.cfg
* postgresql.yml

## Шаги:

1. В почти готовом __Vagrantfile__ меняем путь к SSH ключу и добавляем еще один сервер __nfs__ 

2. Поднимаем машины 
````
vagrant up
````

3. Запускаем готовый __playbook__ для __consul__
````
ansible-playbook consul.play
````
4. Поскольку эта работа основана на 7-й лабораторной работе, нужно так же смонтировать диски, установить, настроить __patroni__  и __vip-manager__
5. Примонтировать папки по пути __pg_backup__
6. Настроить архивирование файлов с помощью утилиты __pg_probackup__
7. Все выполненые действия записываем в playbook.yml и запускаем его:
````
ansible-playbook playbook.yml
```` 
8. Следующей командой проверяем, поднялся ли адрес:
````
ip a
````



