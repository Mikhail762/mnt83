# Домашнее задание к занятию "08.03 Использование Yandex Cloud"  

Данный плейбук производит установку и базовую настройку системы сбора, парсинга, хранения и визуализации логов с помощью  
Elasticsearch, Kibana и Filebeat.  
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

В inventory объявлены 3 группы хостов - elasticsearch, kibana, filebeat.
Установка Elasticsearch и Kibana производится на отдельные хосты, Filebeat - на хосты, с которых нужно собирать логи.  
Требуемая ОС - Centos 7.  
**Для корректной работы необходимо подставить IP-адреса соответствующих хостов в файл invenory/prod/hosts.yml**    

Собственно плейбук site.yml содержит plays c заданиями скачивания репозиториев, распаковки и конфигурирования при помощи  
шаблонов в директории playbooks/templates. Используется параметр `elk_stack_version` для указания конкретных версий ПО.  
Тэги не используются (all по умолчанию).  

Для запуска вылоните: `ansible-playbook -i inventory/prod/hosts.yml playbooks/site.yml`

