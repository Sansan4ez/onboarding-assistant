# AI Onboarding Assistant

Документация по ИИ-инструментам и технологиям для разработчиков.

## 🚀 Быстрый старт

### Требования
- Hugo Extended (версия 0.146.0 или выше)
- Git

### Установка Hugo

#### macOS (с Homebrew)
```bash
brew install hugo
```

#### Ubuntu/Debian
```bash
sudo apt-get install hugo
```

#### Windows (с Chocolatey)
```bash
choco install hugo-extended
```

### Сборка сайта

1. Клонируйте репозиторий:
```bash
git clone https://github.com/Sansan4ez/onboarding-assistant.git
cd onboarding-assistant
```

2. Установите тему:
```bash
git submodule add https://github.com/alex-shpak/hugo-book.git themes/hugo-book
```

3. Запустите локальный сервер:
```bash
hugo server -D
```

4. Откройте http://localhost:1313 в браузере

### Сборка для продакшена

```bash
hugo --minify
```

Собранные файлы будут в папке `docs/`.

## 📁 Структура проекта

```
onboarding-assistant/
├── content/           # Контент сайта
│   ├── index.md      # Главная страница
│   └── menu/         # Меню для темы
├── themes/            # Темы Hugo
│   └── hugo-book/    # Тема документации
├── hugo.toml         # Конфигурация Hugo
└── docs/             # Собранный сайт (генерируется)
```

## 🔧 Конфигурация

Основные настройки в `hugo.toml`:
- `baseURL` - базовый URL для GitHub Pages
- `theme` - используемая тема (hugo-book)
- `publishDir` - папка для собранных файлов

## 📚 Тематические разделы

- 🤖 **ИИ и машинное обучение** - LLM, AI-агенты, RAG
- 🔍 **Поисковые технологии** - векторный, полнотекстовый, гибридный поиск
- 🛠️ **Инструменты разработки** - Cursor AI, Dify.ai, UV
- 📚 **Системы управления контентом** - Git, GitHub Pages, Markdown
- 🗄️ **Базы данных и бэкенд** - Supabase
- 🏗️ **Архитектура и алгоритмы** - DDD, архитектура ассистентов
- 🛠️ **Утилиты и инструменты** - Pandoc, настройки, скрипты

## 🚀 Развертывание

Сайт автоматически развертывается на GitHub Pages из папки `docs/`.

## 📝 Добавление нового контента

1. Создайте новый `.md` файл в папке `content/`
2. Добавьте front matter с заголовком и датой
3. Обновите меню в `content/menu/index.md`
4. Обновите главное оглавление в `content/index.md`

## 🤝 Вклад в проект

1. Форкните репозиторий
2. Создайте ветку для новой функции
3. Внесите изменения
4. Создайте Pull Request

## 📄 Лицензия

MIT License
