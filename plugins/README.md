# FormComposer v5.1 - Плагины

## Быстрый старт

1. Открой `w_composer_51.html`
2. В секции **Presets** перетащи элемент на холст
3. Кликни на элемент — он работает!

## Пресеты (встроенные)

| Пресет | Поведение |
|--------|-----------|
| 📁 File Menu | Клик раскрывает меню с действиями |
| 🔗 Nav Menu | Навигационное меню с ссылками |
| 📋 Accordion | Раскрывающиеся секции |
| 📑 Tabs | Переключатель вкладок |
| 🎚️ Slider | Слайдер с отображением значения |
| 📊 Progress | Прогресс-бар |

## Импорт своих плагинов (.fcomp)

### Формат файла

```json
{
  "name": "My Plugin",
  "behavior": "toggle|accordion|tabs|range|interactive|none",
  "html": "<button>Click me</button>",
  "popup": "<div class='plugin-popup'>...</div>",
  "ai": "Description for AI agent.",
  "w": 100,
  "ht": 35
}
```

### Поля

- **name** — название плагина
- **behavior** — тип поведения
  - `toggle` — клик раскрывает popup-меню
  - `accordion` — раскрытие/сворачивание
  - `tabs` — переключение вкладок
  - `range` — интерактивный слайдер
  - `interactive` — произвольное поведение
  - `none` — статичный элемент
- **html** — основной HTML элемента
- **popup** — опциональное popup-меню (для toggle)
- **ai** — описание для ИИ-агента
- **w, ht** — размеры по умолчанию

### Пример: Кнопка с меню

```json
{
  "name": "Settings",
  "behavior": "toggle",
  "html": "<button class=\"plugin-toggle-btn\">⚙️ Settings</button>",
  "popup": "<div class=\"plugin-popup\"><div class=\"plugin-popup-item\">Option 1</div><div class=\"plugin-popup-item\">Option 2</div></div>",
  "ai": "Settings dropdown with configuration options.",
  "w": 90,
  "ht": 35
}
```

## Экспорт

При сохранении проекта (SAVE) получаешь:
- HTML-файл с визуальным прототипом
- `data-ai` — описание поведения для LLM
- `data-behavior` — тип поведения

LLM использует эти атрибуты для "оживления" прототипа.
