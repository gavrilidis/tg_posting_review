# tg_posting_review

```markdown
# Обзоры мест КИПР - Улучшаем проект и код

Этот проект автоматизирует публикацию обзоров заведений на Кипре с использованием данных из Google Sheets, API Google Maps, OpenAI и Telegram. Код написан для работы в Google Apps Script.

## Функциональность

- **Извлечение данных:** Считывание информации из Google Sheets (ссылки на заведения, статус публикации).
- **Обогащение данных:** Получение Place ID и подробной информации о месте через Geocoding API и Places API.
- **Генерация контента:** Создание поста с помощью OpenAI (с учетом отзывов и описания заведения).
- **Публикация:** Отправка сгенерированного поста в Telegram и обновление статуса в таблице.

## Установка и настройка

1. **Клонирование репозитория:**

   Если вы планируете работать локально, выполните:
   ```bash
   git clone <URL_репозитория>
   ```

2. **Создание нового проекта в Google Apps Script:**

   - Перейдите на [Google Apps Script](https://script.google.com/) и создайте новый проект.
   - Скопируйте содержимое из репозитория (ваш код) в редактор кода.

3. **Настройка конфиденциальных данных:**

   Чтобы не публиковать секретные ключи в открытом репозитории, используйте Скриптовые свойства:
   
   - В редакторе Google Apps Script выберите **Файл → Свойства проекта → Скриптовые свойства**.
   - Добавьте следующие ключи и их значения:
     - `SHEET_ID` – ID вашего Google Sheet (только ID из ссылки).
     - `MAPS_API_KEY` – API-ключ для Google Maps.
     - `OPENAI_API_KEY` – API-ключ OpenAI.
     - `TELEGRAM_BOT_TOKEN` – токен вашего Telegram-бота.
     - `TELEGRAM_CHAT_ID` – идентификатор чата или канала Telegram.

   В коде вместо жёстко заданных констант используйте получение значений:
   ```js
   const SHEET_ID = PropertiesService.getScriptProperties().getProperty("SHEET_ID");
   const MAPS_API_KEY = PropertiesService.getScriptProperties().getProperty("MAPS_API_KEY");
   const OPENAI_API_KEY = PropertiesService.getScriptProperties().getProperty("OPENAI_API_KEY");
   const TELEGRAM_BOT_TOKEN = PropertiesService.getScriptProperties().getProperty("TELEGRAM_BOT_TOKEN");
   const TELEGRAM_CHAT_ID = PropertiesService.getScriptProperties().getProperty("TELEGRAM_CHAT_ID");
   ```

4. **Развертывание:**

   - Сохраните проект.
   - При необходимости настройте триггеры для автоматического запуска функции `processPlaces()` (например, по расписанию).

## Использование

- **Запуск вручную:** Вы можете запускать функцию `processPlaces()` напрямую из редактора Google Apps Script.
- **Автоматизация:** Настройте триггеры для периодического выполнения, чтобы автоматизировать публикацию обзоров.
- **Логирование:** Просматривайте логи (через `console.log` и `console.error`) для отслеживания работы и выявления возможных ошибок.

## Безопасность

- Никогда не публикуйте API-ключи и другие конфиденциальные данные в публичном репозитории.
- Используйте Скриптовые свойства для безопасного хранения секретов.
- Если вы работаете с другими технологиями (например, Node.js), убедитесь, что соответствующие файлы (.env) добавлены в `.gitignore`.

## Вклад

Если у вас есть предложения по улучшению или обнаружены ошибки, создайте Pull Request или откройте Issue в репозитории. Ваш вклад поможет улучшить проект!

## Лицензия

Этот проект распространяется под лицензией [MIT License](LICENSE).
```

Скопируйте этот текст в редактор файла `README.md` через веб-интерфейс GitHub, внесите при необходимости свои изменения, сохраните и ваш репозиторий будет выглядеть максимально чисто и профессионально для других разработчиков.
