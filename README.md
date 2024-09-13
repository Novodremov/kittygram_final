![Workflow Status](https://github.com/nvdrmv/kittygram_final/actions/workflows/main.yml/badge.svg)

# **Kittygram**
Сервис для публикации фотографий котиков. Указывается имя, год рождения, цвет котика, также дополнительно можно публиковать его достижения. Можно просматривать записи чужих котиков.
## Использованные технологии:
Бэкенд проекта написан на Python, с использованием фреймворка Django, фронтэнд на JavaScript с использованием React.

## Настройка CI/CD

Деплой проекта на удалённый сервер настроен через CI/CD с помощью GitHub Actions по имеющемуся workflow, в котором реализованы:

* проверка кода бэкенда на соответствие PEP8;
* тестирование фронтенда и бэкенда;
* создание и загрузка образов на Docker Hub;
* выгрузка образов из Docker Hub на удалённый сервер и запуск проекта с помощью Docker Compose;
* направление сообщения в Telegram об успешном завершении деплоя.

Форкните репозиторий.
Сохраните следующие переменные с необходимыми значениями в секретах GitHub Actions своего репозитория:

```
DOCKER_USERNAME - логин в Docker Hub
DOCKER_PASSWORD - пароль для Docker Hub
HOST - ip-адрес удаленного сервера
SSH_KEY - закрытый SSH-ключ для доступа к удаленному серверу
SSH_PASSPHRASE - passphrase для доступа к удаленному серверу
USER - username для доступа к удаленному серверу
TELEGRAM_TO - ID своего телеграм-аккаунта
TELEGRAM_TOKEN - токен Telegram-бота
```

На удалённом сервере создайте корневую директорию проекта kittygram.

Создайте и заполните в корневой директории .env файл по примеру:
```
POSTGRES_DB=kittygram_db
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DB_PORT=5432
SERVER_IP={ip-адрес удаленного сервера}
SERVER_DOMAIN={доменное имя}
DEBUG=False
SECRET_KEY={секретный ключ Джанго-проекта}
SQLITE_BASE_CHOICE=False
```

Workflow находится в папке .github/workflows/


## Авторы:
Яндекс-Практикум и Алексей Лысов