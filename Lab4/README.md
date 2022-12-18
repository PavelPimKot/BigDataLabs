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

Представим теперь, что одному из клиентов нужна информация о другом клиенте (к качестве клиентов могут выступать узлы кластера). Этот сценарий эмулируется получением информации командой get.
Выберем консоль grue и обратимся к информации узла bleen.

![](images/get_bleen_from_grue.png)

Теперь эмулируем аварийное отключение любого клиента. Нажмем сочетание клавиш Ctrl + D в одной из консолей, создавшей эфимерный узел.
Проверим, что соответствующий узел пропал из mygroup. Изменение списка дочерних узлов может произойти не сразу — от 2 до 20 tickTime, значение которого можно посмотреть в zoo.cfg.

![](images/only_grue_left.png)

В заключении удалим узел /mygroup.

![](images/delete_my_group.png)

### Animal task
![](images/monkey_run.png)
![](images/tiger_running.png)

### Philosophers
```
Philosopher 0 is going to eat
Philosopher 4 is going to eat
Philosopher 1 is going to eat
Philosopher 2 is going to eat
Philosopher 3 is going to eat
Philosopher 2 picked up the left fork
Philosopher 2 picked up the right fork
Philosopher 5 picked up the left fork
Philosopher 5 picked up the right fork
Philosopher 4 picked up the left fork
Philosopher 5 put the right fork
Philosopher 5 put the loft fork and finished eating
Philosopher 4 picked up the right fork
Philosopher 5 is thinking
Philosopher 1 picked up the left fork
Philosopher 2 put the right fork
Philosopher 2 put the loft fork and finished eating
Philosopher 1 picked up the right fork
Philosopher 3 picked up the left fork
Philosopher 2 is thinking
Philosopher 4 put the right fork
Philosopher 1 put the right fork
Philosopher 1 put the loft fork and finished eating
Philosopher 4 put the loft fork and finished eating
Philosopher 3 picked up the right fork
Philosopher 1 is thinking
Philosopher 4 is thinking
Philosopher 4 is going to eat
Philosopher 5 picked up the left fork
Philosopher 5 picked up the right fork
Philosopher 1 is going to eat
Philosopher 2 picked up the left fork
Philosopher 5 put the right fork
Philosopher 5 put the loft fork and finished eating
Philosopher 1 picked up the left fork
Philosopher 5 is thinking
Philosopher 3 is going to eat
Philosopher 3 put the right fork
Philosopher 3 put the loft fork and finished eating
Philosopher 2 picked up the right fork
Philosopher 3 is thinking
Philosopher 4 picked up the left fork
Philosopher 4 picked up the right fork
Philosopher 2 put the right fork
Philosopher 2 put the loft fork and finished eating
Philosopher 1 picked up the right fork
Philosopher 2 is thinking
Philosopher 2 is going to eat
Philosopher 3 picked up the left fork
Philosopher 1 put the right fork
Philosopher 1 put the loft fork and finished eating
Philosopher 1 is thinking
Philosopher 4 put the right fork
Philosopher 4 put the loft fork and finished eating
Philosopher 3 picked up the right fork
Philosopher 4 is thinking
Philosopher 3 put the right fork
Philosopher 3 put the loft fork and finished eating
Philosopher 3 is thinking