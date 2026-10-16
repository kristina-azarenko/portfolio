# Портфолио — Кристина Азаренко

Статичный сайт без сборки: один `index.html` + папка `assets`. Двуязычный (RU / EN, язык выбирается по настройкам браузера, есть переключатель), тёмная и светлая тема.

## Что в папке

```
index.html          # весь сайт: разметка, стили, скрипты, тексты RU/EN
favicon.svg         # иконка вкладки
assets/
  *-cover.mp4/.webm # видео-обложки кейсов (mp4 + webm как запасной формат)
  *-cover-poster.jpg# кадр-заставка, пока грузится видео
  concept-1..3.webp # картинки в блоке «Мои концепты»
  Kristina_Azarenko_CV.pdf  # резюме (кнопка «Смотреть CV / резюме»)
.nojekyll           # чтобы GitHub Pages отдавал файлы как есть
```

Все пути относительные, поэтому сайт работает и в корне домена, и в подпапке (`username.github.io/repo/`).

## Как выложить на GitHub Pages

1. Создайте на GitHub пустой репозиторий (без README и лицензии), например `kristina-portfolio`.
2. В этой папке выполните:

```bash
git init
git add .
git commit -m "Портфолио"
git branch -M main
git remote add origin https://github.com/<ваш-логин>/kristina-portfolio.git
git push -u origin main
```

3. В репозитории: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
4. Через 1–2 минуты сайт будет по адресу `https://<ваш-логин>.github.io/kristina-portfolio/`.
   Если назвать репозиторий `<ваш-логин>.github.io`, адрес будет без подпапки: `https://<ваш-логин>.github.io/`.
5. Свой домен: **Settings → Pages → Custom domain**.

Подойдут и другие хостинги (Netlify, Vercel, Cloudflare Pages): достаточно перетащить папку целиком.

## Как посмотреть локально

Видео и шрифты лучше смотреть через локальный сервер, а не двойным кликом по файлу:

```bash
python3 -m http.server 8000
# открыть http://localhost:8000
```

## Как менять содержимое

| Что менять | Где |
|---|---|
| Тексты на странице (био, опыт, подписи) | в `index.html`, объекты `TRANSLATIONS` → `ru` и `en` |
| Кейсы в попапах (контекст, аудит, результаты) | в `index.html`, объект `PROJECTS_I18N` → `ru` и `en` |
| Резюме | заменить файл `assets/Kristina_Azarenko_CV.pdf` (имя оставить прежним) |
| Контакты (почта, Telegram) | блок `contact-list` в `index.html` |
| Ссылки Dribbble / Pinterest | блок `concepts__links` в `index.html` |
| Аватарка (клик — смена фото) | `assets/avatar-1..4.webp`, блок `#avatarBtn` в `index.html` |
| Папка с мемами | `assets/meme-1..9.webp`; добавить мем: файл в `assets`, затем `<img>` в `.ios-folder` и `<img class="meme-card" data-ar="высота/ширина">` в `#memeLayer`, обновить цифру на бейдже |

### Размеры медиа

| Что | Размер | Формат |
|---|---|---|
| Обложка кейса | 1200 × 900 px (4:3) | видео mp4 (H.264, без звука) + webm, постер jpg |
| Картинка в блоке «Мои концепты» | 320 × 470 px (строго такая пропорция) | webp / jpg, до ~50–80 КБ |

Если пропорция другая, картинка обрежется по центру. Нужны новые обложки или кейсы: заменить файлы в `assets` и поправить пути/тексты в `index.html`.

## Заметки

- Ссылка на почту открывает окно нового письма в Gmail в новой вкладке; адрес при клике копируется в буфер обмена как запасной вариант.
- Шрифт Geist подгружается с Google Fonts, поэтому для идеального вида нужен интернет.
