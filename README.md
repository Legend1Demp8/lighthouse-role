# Ansible Role: Lighthouse
Простая Ansible-роль для установки и настройки легковесного веб-интерфейса Lighthouse для ClickHouse на Ubuntu 24.

## Требования
* Веб-сервер (Nginx или Apache) на целевом хосте для раздачи статики.

## Переменные роли
Вы можете настроить версию или путь установки (необязательно):
* `lighthouse_version`: "master" — ветка или тег Lighthouse для загрузки.
* `lighthouse_install_dir`: "/var/www/lighthouse" — директория для размещения файлов.

## Пример Playbook
```yaml
- hosts: webservers
  roles:
    - role: clickhouse 
```

## Лицензия
BSD
