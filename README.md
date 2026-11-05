# LightHouse Role

Роль для установки веб-интерфейса LightHouse (для ClickHouse) под управлением Nginx.

## Переменные роли (Variables)

Изменяемые параметры по умолчанию (`defaults/main.yml`):
* `lighthouse_dir` — Директория, куда будет склонирован интерфейс (`/var/www/lighthouse`).
* `lighthouse_force_update` — Принудительное обновление репозитория при каждом запуске (`false`).

Внутренние переменные (`vars/main.yml`):
* `lighthouse_vcs_url` — Ссылка на официальный Git-репозиторий LightHouse.
* `lighthouse_vcs_version` — Целевая ветка репозитория (`master`).

## Шаблоны (Templates)
Роль использует шаблон конфигурации веб-сервера:
* `lighthouse.conf.j2` — Конфигурационный файл Nginx (Virtual Host) для раздачи интерфейса LightHouse.

## Теги (Tags)
Вы можете запускать части роли отдельно с помощью тегов:
* `nginx` — Всё, что связано с установкой и настройкой веб-сервера.
* `lighthouse` — Скачивание и настройка прав для самого интерфейса.

## Пример использования (Example Playbook)

```
yaml
- hosts: lighthouse
  become: true
  roles:
    - lighthouse-role
```
