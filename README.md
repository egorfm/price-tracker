<h1 align="center">🏷️ price-tracker</h1>

<p align="center">
  Telegram-бот для мониторинга цен на товары в интернет-магазинах и мгновенных уведомлений о скидках
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Telegram-aiogram%203-2CA5E0?logo=telegram&logoColor=white" alt="Telegram">
  <img src="https://img.shields.io/badge/Scheduler-APScheduler-blue" alt="Scheduler">
  <img src="https://img.shields.io/badge/Database-SQLite-003B57?logo=sqlite&logoColor=white" alt="SQLite">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
</p>

---

## ✨ Возможности

- 🔗 **Универсальный парсинг цен**: извлечение стоимости товаров через микроразметку `JSON-LD`, OpenGraph и мета-теги без жесткой привязки к конкретным маркетплейсам.
- ⏱️ **Фоновый мониторинг**: периодическая автоматическая проверка актуальных цен по расписанию (APScheduler).
- 📉 **Уведомления о снижении цены**: бот мгновенно отправляет сообщение, если цена отслеживаемого товара упала.
- 💬 **Удобные команды**:
  - `/track <url>` — поставить товар на отслеживание
  - `/list` — список всех ваших отслеживаемых товаров с текущими ценами
  - `/untrack <id>` — удалить товар из отслеживания
- 🗄️ **Локальное хранилище**: легкая встроенная база данных SQLite, не требующая настройки внешних серверов.

---

## 🛠 Стек технологий

- **Python 3.11+**
- **aiogram 3** — асинхронный фреймворк для Telegram Bot API
- **APScheduler** — планировщик периодических фоновых задач
- **BeautifulSoup4 & Requests** — парсинг веб-страниц и микроразметки
- **SQLite** — база данных товаров и истории цен
- **pytest** — модульное тестирование

---

## 🚀 Быстрый старт

### 1. Клонирование репозитория
```bash
git clone https://github.com/egorfm/price-tracker.git
cd price-tracker
```

### 2. Создание и активация виртуального окружения
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 3. Настройка токена
Скопируйте шаблон переменных окружения и укажите токен вашего бота от [@BotFather](https://t.me/BotFather):
```bash
cp .env.example .env
```
Заполните `.env`:
```ini
BOT_TOKEN=ваш_токен_бота
CHECK_INTERVAL_HOURS=6
```

### 4. Запуск бота
```bash
python -m bot.main
```

---

## 🧪 Тестирование

Запуск набора автоматических тестов:
```bash
pytest
```

---

## 📁 Структура проекта

```
price-tracker/
├── bot/
│   ├── main.py        # Точка входа и инициализация бота
│   ├── handlers.py    # Обработчики команд Telegram (/track, /list, /untrack)
│   ├── parser.py      # Парсинг цен через JSON-LD и meta-теги
│   ├── scheduler.py   # Фоновые периодические проверки
│   ├── db.py          # Работа с базой данных SQLite
│   └── config.py      # Загрузка конфигурации из .env
├── tests/             # Модульные тесты
├── requirements.txt   # Зависимости проекта
├── .env.example       # Пример конфигурации окружения
├── LICENSE            # Лицензия MIT
└── README.md
```

---

## 📄 Лицензия

Проект распространяется под лицензией [MIT](LICENSE).
