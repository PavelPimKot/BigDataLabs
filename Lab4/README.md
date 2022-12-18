# Лабораторная 4.
# Zookeeper

# 1) Установка и запуск
Устанавливаем Zookeeper, запускаем сервер  через zkServer.cmd

Запускаем ZooKeeper CLI с помощью zkCli. Используем help для просмотра доступных команд.

![](images/zookeeper_help_command.png)

# 2) Добавление узлов znode, считывание и запись данных в znode из CLI, управление конфигурациями

Для вывода списка корневых узлов - ls / - получаем один узел
Для вывода списка дочерних узлов - ls /zookeeper:

![](images/zookeeper_ls_command.png)

Создадим в корне узел /mynode с данными "first_version" и проверим, что в корне появился новый узел.

![](images/mynode.png)

Изменим данные узла на "second_version":

![](images/mynode_start.png)

Создадим два нумерованных узла в качестве дочерних mynode:

![](images/children_mynode.png)

Пример. Принадлежность клиентов к группе
Внутри CLI сессии, создадим узел mygroup. Откроем две новых CLI консоли и в каждой создайте по дочернему узлу в mygroup и проверим, что grue и bleen являются членами группы mygroup:

![](images/create_mygroup.png)
![](images/bleen.png)
![](images/grue.png)
![](images/grue_bleen.png)