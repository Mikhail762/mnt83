# Домашнее задание к занятию "08.03 Использование Yandex Cloud"  

Данный плейбук производит установку и базовую настройку системы сбора, парсинга, хранения и визуализации логов с помощью Elasticsearch, Kibana и Filebeat.  
Структура плейбука:  
```
├── inventory
│   └── prod
│       ├── group_vars
│       │   └── all.yml
│       └── hosts.yml
└── playbooks
    ├── site.yml
    └── templates
        ├── elasticsearch.yml.j2
        ├── filebeat.yml.j2
        └── kibana.yml.j2
```


Установка Elasticsearch и Kibana производится на отдельные машины, Filebeat - на машину, с которой нужно собирать логи.  
Требуемая ОС - Centos 7.  
**Для корректной работы необходимо подставить соответствующие IP-адреса в файл invenory/prod/hosts.yml**  

