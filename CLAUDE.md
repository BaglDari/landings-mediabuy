# landings-mediabuy

Проект для создания лендингов под медиабай. Claude сам верстает.
Не связан с ai-landing-agent.

## Структура

```
landings-mediabuy/
├── templates/
│   └── base.html         — базовый шаблон (токены в {{CAPS}})
├── assets/
│   ├── fonts/            — кастомные шрифты (.woff2)
│   ├── icons/            — SVG-иконки
│   └── images/           — shared картинки
├── input/                — бриф от байера (референсы, текст, лого)
├── output/               — готовые лендинги (папка = slug)
└── src/                  — wip, черновики
```

## Стек

Чистый HTML/CSS/JS — никаких сборщиков. Лендинг = один файл index.html + assets.

- Шрифты: Google Fonts CDN или локальный .woff2 в assets/fonts/
- Иконки: Feather Icons CDN (data-feather="name") или SVG inline
- Изображения: Unsplash/Pexels или от байера → assets/images/
- Анимации: CSS transitions/keyframes, без тяжёлых библиотек

## Как создавать лендинг

1. Взять бриф из input/ (продукт, язык, CTA, ссылка, референс)
2. Скопировать templates/base.html → output/[slug]/index.html
3. Заменить все {{TOKENS}} на реальный контент
4. Подобрать цвета/шрифты под бренд
5. Проверить адаптивность (mobile-first)
6. UTM-трекинг уже вшит в базовый шаблон

## Целевые рынки (SEA)

TH / VN / MY / ID / PH / PK / BD — финтех/трейдинг/крипто.
Язык контента по брифу, часто EN или местный.

## Дизайн-ориентиры

Референсы байеров: elev8_id стиль (clean, dark accents, red CTA, mobile-first).
Инспирация: supahero.io, dark.design, headers.club

## Установленные инструменты

- **Figma MCP** — читать Figma-файлы байера прямо из Claude Code
  Требует: Figma API token в настройках MCP
- **Feather Icons** — cdn.jsdelivr.net (в шаблоне)
- **Google Fonts** — fonts.googleapis.com (в шаблоне)
