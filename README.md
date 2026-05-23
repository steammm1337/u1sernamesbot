# 🌐 Telegram Mini App - Деплой

## Что это?

Веб-интерфейс для бота с красивым UI и слайдерами. Работает прямо в Telegram.

## Быстрый деплой (GitHub Pages)

### 1. Создай репозиторий на GitHub

```bash
cd webapp
git init
git add index.html
git commit -m "Add webapp"
git branch -M main
git remote add origin https://github.com/твой-username/u1sernamesbot.git
git push -u origin main
```

### 2. Включи GitHub Pages

1. Открой репозиторий на GitHub
2. Settings → Pages
3. Source: Deploy from a branch
4. Branch: `main` → `/root`
5. Save

Через 1-2 минуты сайт будет доступен по адресу:
`https://твой-username.github.io/u1sernamesbot/`

### 3. Обнови URL в боте

Открой `handlers/commands.py` и замени URL:

```python
web_app=WebAppInfo(url="https://твой-username.github.io/u1sernamesbot/")
```

### 4. Перезапусти бота

```bash
pkill -f "python bot.py"
cd /c/Users/synta/Desktop/idk/telegram-username-bot
nohup python bot.py > bot.log 2>&1 &
```

## Альтернативные варианты деплоя

### Vercel (рекомендуется)

1. Установи Vercel CLI:
```bash
npm i -g vercel
```

2. Деплой:
```bash
cd webapp
vercel --prod
```

3. Скопируй URL и обнови в `handlers/commands.py`

### Netlify

1. Перетащи папку `webapp` на https://app.netlify.com/drop
2. Скопируй URL
3. Обнови в `handlers/commands.py`

### Cloudflare Pages

1. Зайди на https://pages.cloudflare.com
2. Create a project → Upload assets
3. Загрузи `index.html`
4. Скопируй URL

## Локальное тестирование

```bash
cd webapp
python -m http.server 8000
```

Открой: http://localhost:8000

⚠️ **Важно**: Telegram Web App работает только через HTTPS (кроме localhost)

## Что дальше?

После деплоя пользователи увидят кнопку "🎯 Открыть генератор" в боте. При нажатии откроется красивый интерфейс с слайдерами прямо в Telegram.
