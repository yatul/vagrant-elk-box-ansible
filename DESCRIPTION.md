# Тестовое задание по ELK стеку

Выполнено на основе [github.com/comperiosearch/vagrant-elk-box-ansible](https://github.com/comperiosearch/vagrant-elk-box-ansible)


## Изменения

Изменённые файлы:

1. *Vagrantfile* - установлено имя виртуальной машины, для удобства
2. *provisioning/group_vars/all/logstash.yml* - настройки для сбора
логов, чтобы в ES попадали системные логи (выбрал *syslog* и *dmesg*) и
информация о работе *sshd* (*auth.log*). В ES они попадают с разными
*document_type*: *system* и *auth* соотвественно.


## Запуск

Для запуска на машине должен быть установлен свежий *Vagrant*. Запуск
осуществляется с помощью команды `vagrant up`, после выполнения которой,
можно ходить по урлам:

- [http://localhost:5602/](http://localhost:5602/) -- Kibana
- [http://localhost:9201/_plugin/HQ](http://localhost:9201/_plugin/HQ) -- ElasticHQ
- [http://localhost:9201/_plugin/marvel](http://localhost:9201/_plugin/marvel) -- Marvel


## Проверка
   
Для проверки функциональности нужно:

1. Зайти в Kibana
2. Создать предлагаемый индекс *logstash-**
3. Отфильтровать поля по *_type*
