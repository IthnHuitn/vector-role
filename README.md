# Vector Role

Роль Ansible для установки и настройки Vector — сборщика логов с отправкой в ClickHouse.

## Требования

- Ansible 2.9+
- ClickHouse должен быть установлен и доступен по сети
- Архитектура x86_64

## Переменные

### defaults/main.yml

| Переменная | Значение по умолчанию | Описание |
|------------|------------------------|----------|
| `vector_version` | `0.39.0` | Версия Vector |
| `vector_install_dir` | `/opt/vector` | Директория установки |
| `vector_config_dir` | `/etc/vector` | Директория конфигурации |
| `vector_data_dir` | `/var/lib/vector` | Директория данных |

### Обязательные переменные (из playbook)

| Переменная | Описание |
|------------|----------|
| `clickhouse_host` | IP-адрес или хост ClickHouse |

## Использование

```yaml
- hosts: vector
  become: true
  roles:
    - role: vector-role
      vars:
        clickhouse_host: "IP-adress" # ваш IP адрес хоста
```

## Теги

```text
Тег	        | Описание
directories	| Создание директорий
download	| Скачивание дистрибутива
install	   | Установка Vector
config	   | Настройка конфигурации
service	   | Запуск и включение сервиса
```

## Установка

```bash
ansible-galaxy install git+https://github.com/IthnHuitn/vector-role.git
```

## Автор

## `IthnHuitn`