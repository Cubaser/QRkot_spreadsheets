# QRkot

## Описание
QRkot — это платформа, созданная для привлечения пожертвований на различные нужды, связанные с заботой о кошках. Это может быть медицинская помощь, покупка корма, создание безопасных мест для проживания и многое другое. Основная цель проекта — поддержка кошачьей популяции через финансирование целевых инициатив.


## Как это работает?

Целевые проекты
Фонд может одновременно поддерживать несколько инициатив. Каждый проект имеет:

- Уникальное название и описание.
- Целевую сумму для сбора средств.

Как только проект достигает своей финансовой цели, он закрывается, а пожертвования начинают поступать в следующий по очереди открытый проект.

## Пожертвования

Любой зарегистрированный пользователь может внести вклад в фонд. Пожертвования не привязаны к конкретному проекту, что позволяет автоматически распределять средства на первый нуждающийся проект. Если на момент пожертвования нет активных проектов, средства будут ждать открытия нового. Избыточные суммы переходят на следующую инициативу, чтобы исключить потерю ресурсов.


## Пользователи и права

Доступ к проектам

- Гости: могут просматривать список всех проектов.
- Администраторы: имеют право добавлять новые проекты, редактировать существующие (в рамках текущих вложений) и удалять проекты, если в них ещё не было внесено средств.

Доступ к пожертвованиям

- Пользователи: видят свои пожертвования, включая такие данные, как ID, комментарий, сумма и дата создания.
- Администраторы: имеют доступ к полной информации о всех пожертвованиях.
  
Важно: редактировать или удалять пожертвования не может никто, чтобы сохранить прозрачность и достоверность данных.

## Работа с GoogleAPI

- Администраторы: имеют доступ к созданию Google таблицы. В таблице будет сформирована информация о закрытых проектах, по количеству времени, которое понадобилось на сбор средств, — от меньшего к большему.

## Как начать работу с проектом?

Клонируйте репозиторий:
```bash
git clone git@github.com:Cubaser/cat_charity_fund.git
```

### 2. Установка виртуального окружения и зависимостей
Активируйте виртуальное окружение и установите необходимые библиотеки:
```bash
cd cat_charity_fund/
python3 -m venv venv
source venv/bin/activate # для Linux
source venv/scripts/activate # для Windows
pip install -r requirements.txt
```

### 3. Настройка переменных окружения
Создайте в корне проекта файл `.env` со следующим содержимым:
```env
APP_TITLE=Кошачий благотворительный фонд
DATABASE_URL=sqlite+aiosqlite:///./fastapi.db
SECRET_KEY=<ваш_секретный_ключ>

Данные для работы Google API
EMAIL=
TYPE=
PROJECT_ID=
PRIVATE_KEY_ID="
PRIVATE_KEY=
CLIENT_EMAIL=
CLIENT_ID=
AUTH_URI=
TOKEN_URI=
AUTH_PROVIDER_X509_CERT_URL=
CLIENT_X509_CERT_URL=
```

Примените миграции базы данных:
```bash
alembic upgrade head
```

Запустите сервер:
```bash
uvicorn app.main:app
```

Проект станет доступен по адресу: [Кошачий благотворительный фонд](http://127.0.0.1:8000).

### Основные технологии:
- **Python**
- **Fastapi**
- **SQLAlchemy**
- **GoogleAPI**

### Документация
Документация к API доступна по следующим адресам:

- [Swagger UI](http://127.0.0.1:8000/docs) — документация API.
- [Redoc](http://127.0.0.1:8000/redoc) — альтернативная документация API.

---

## Автор
Иванов Виктор
[cubaser@mail.ru](mailto:cubaser@mail.ru)

