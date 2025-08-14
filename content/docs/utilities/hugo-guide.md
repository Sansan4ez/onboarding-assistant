---
title: "Hugo - Статический генератор сайтов"
date: 2024-12-19
draft: false
weight: 2
---

# Hugo - Статический генератор сайтов

Hugo — быстрый статический генератор сайтов, написанный на Go. Идеально подходит для создания документации, блогов и лендингов.

## 🚀 Установка

### macOS (с Homebrew)
```bash
brew install hugo
```

### Ubuntu/Debian
```bash
sudo apt-get install hugo
```

### Windows (с Chocolatey)
```bash
choco install hugo-extended
```

### Проверка версии
```bash
hugo version
```

## 📁 Структура проекта Hugo

```
my-site/
├── archetypes/          # Шаблоны для нового контента
├── content/             # Контент сайта (Markdown файлы)
├── data/               # Файлы данных (JSON, YAML, TOML)
├── layouts/            # HTML шаблоны
├── static/             # Статические файлы (CSS, JS, изображения)
├── themes/             # Темы
├── hugo.toml           # Конфигурация сайта
└── public/             # Собранный сайт (генерируется)
```

## ⚡ Основные команды

### Разработка
```bash
# Создание нового сайта
hugo new site my-site

# Запуск dev сервера
hugo server

# Запуск с черновиками
hugo server -D

# Запуск с минификацией
hugo server --minify

# Запуск на конкретном порту
hugo server --port 3000
```

### Создание контента
```bash
# Создание новой страницы
hugo new content/posts/my-post.md

# Создание страницы в разделе
hugo new content/docs/guide.md
```

### Сборка
```bash
# Сборка для продакшена
hugo

# Сборка с минификацией
hugo --minify

# Сборка черновиков
hugo -D

# Очистка кеша
hugo --gc
```

### Проверка
```bash
# Проверка конфигурации
hugo check

# Подробный вывод при сборке
hugo --verbose

# Показать метрики сборки
hugo --templateMetrics
```

## 📄 Front Matter

Каждый Markdown файл начинается с метаданных:

```yaml
---
title: "Заголовок страницы"
date: 2024-12-19
draft: false
weight: 10
description: "Описание страницы"
tags: ["tag1", "tag2"]
categories: ["category1"]
---

# Содержимое страницы
```

### Основные параметры
- `title` - заголовок страницы
- `date` - дата создания
- `draft` - черновик (true/false)
- `weight` - порядок сортировки
- `description` - описание для SEO
- `tags` - теги
- `categories` - категории

## 🎨 Работа с темами

### Установка темы
```bash
# Как git submodule (рекомендуется)
git submodule add https://github.com/theme/repo.git themes/theme-name

# Или клонирование
git clone https://github.com/theme/repo.git themes/theme-name
```

### Настройка в hugo.toml
```toml
theme = "theme-name"
```

### Переопределение шаблонов
Создайте файл в `layouts/` с тем же путем, что и в теме для переопределения.

## 🔧 Конфигурация hugo.toml

```toml
baseURL = 'https://example.com'
languageCode = 'ru-ru'
title = 'Мой сайт'
theme = 'my-theme'

# Папка для сборки для публикации на GitHub
publishDir = "docs"

# Параметры темы
[params]
  author = "Автор"
  description = "Описание сайта"

# Настройки Markdown
[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true  # Разрешает HTML в Markdown

# Меню
[menu]
  [[menu.main]]
    name = "Главная"
    url = "/"
    weight = 1
```

## 🔗 Внутренние ссылки

### Shortcode relref (рекомендуется)
```
[Ссылка на страницу](релативная_ссылка_с_relref)
[Ссылка на раздел](релативная_ссылка_на_раздел)
```

Пример синтаксиса: двойные фигурные скобки с углами, relref, путь в кавычках

### Относительные ссылки
```markdown
[Страница](/page/)
[Раздел](/section/)
```

## 📋 Shortcodes

Hugo поддерживает встроенные shortcodes:

### Встроенные
- **youtube** - встраивание видео YouTube
- **tweet** - встраивание твитов
- **ref** - ссылка на страницу
- **relref** - относительная ссылка

Синтаксис: двойные фигурные скобки с углами, имя shortcode, параметры

### Пользовательские
Создайте файл в `layouts/shortcodes/myshortcode.html`:
```html
<div class="custom">
  {{ .Inner }}
</div>
```

Использование: оберните контент в парный shortcode с именем myshortcode

## 🚀 Деплой

### GitHub Pages
1. Настройте `baseURL` в hugo.toml
2. Установите `publishDir = "docs"`
3. Соберите сайт: `hugo --minify`
4. Настройте GitHub Pages на папку `docs/`

### Netlify
1. Подключите репозиторий
2. Команда сборки: `hugo --minify`
3. Папка публикации: `public`

### Vercel
1. Импортируйте проект
2. Framework: Hugo
3. Автоматическая сборка при push

## ⚠️ Частые ошибки

### Битые ссылки
- ❌ `[ссылка](page.md)` - не добавляйте .md
- ✅ Используйте relref shortcode для внутренних ссылок

### Проблемы с темой
- Проверьте правильность имени темы в конфиге
- Убедитесь, что тема установлена в `themes/`

### Черновики не показываются
- Используйте флаг `-D` при разработке
- Проверьте `draft: false` в front matter

## 📚 Полезные ресурсы

- [Официальная документация Hugo](https://gohugo.io/documentation/)
- [Темы Hugo](https://themes.gohugo.io/)
- [Hugo Shortcodes](https://gohugo.io/content-management/shortcodes/)
- [Syntax Highlighting](https://gohugo.io/content-management/syntax-highlighting/)

## 🔍 Отладка

```bash
# Проверка конфигурации
hugo check

# Детальная информация о сборке
hugo --verbose

# Показать переменные окружения
hugo env

# Список всех команд
hugo help
```