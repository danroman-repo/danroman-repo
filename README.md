## Здравствуйте!

Меня зовут Роман. Я программист Frontend-разработчик.

г. Мурманск, Россия.

[![Email](https://img.shields.io/badge/Email-danroman%40yandex.ru-blue?style=flat-square&logo=gmail)](mailto:danroman@yandex.com)
 — предпочитаемый способ связи

[![GitHub followers](https://img.shields.io/github/followers/danroman-repo?label=Follow&style=social)](https://github.com/danroman-repo)
[![Resume views](https://img.shields.io/badge/googledrive-resume-blue?logo=googledrive&logoColor=green)](https://docs.google.com/document/d/1OireBkZJMweHggbbcLLOhNGTAFyKuLxysQdgBWlfqYs/edit?usp=drive_link&color=blue&style=flat-square) - резюме (нажать для перехода)

Ключевые компетенции
 
- Frontend-разработка на JavaScript и React
- Вёрстка сайтов в HTML и CSS
- Работа с изменениями кода проекта с помощью Git и GitHub
- Решение универсальных задач с использованием Python
- Разработка сайтов с помощью фреймворка Django
- Применение принципов клиент-серверного взаимодействия
- Работа с базами данных с использованием SQLAlchemy и PostgreSQL
- Работа с API сторонних сервисов
- Unit-тестирование при помощи PyTest и Jest


[![My Skills](https://skillicons.dev/icons?i=pycharm "Pycharm")](https://www.jetbrains.com/ru-ru/pycharm/)
[![My Skills](https://skillicons.dev/icons?i=react "React")](https://ru.react.dev/)
[![My Skills](https://skillicons.dev/icons?i=django "Django")](https://www.djangoproject.com/)
[![My Skills](https://skillicons.dev/icons?i=git "Git")](https://git-scm.com)
[![My Skills](https://skillicons.dev/icons?i=js "JavaScript")](https://ru.wikipedia.org/wiki/JavaScript)
[![My Skills](https://skillicons.dev/icons?i=ts "TypeScript")](https://www.typescriptlang.org/)
[![My Skills](https://skillicons.dev/icons?i=html "HTML")](https://en.wikipedia.org/wiki/HTML)
[![My Skills](https://skillicons.dev/icons?i=css "CSS")](https://ru.wikipedia.org/wiki/CSS)

## Мои работы:

### Сайт ООО «Энергия» — корпоративный сайт услуг судоремонта

[![Сайт компании](https://github.com/danroman-repo/site-company/blob/main/pic/2026-09-24_21-22-09.png)](https://github.com/danroman-repo/translit/)

#### Поставленные задачи

- Разработать корпоративный сайт для демонстрации услуг судоремонта, промышленных работ и лабораторной диагностики.
- Реализовать многостраничную навигацию через react-router-dom v7.
- Создать общие компоненты (Header, Footer) и обёртку для страниц производства.
- Разработать отдельные страницы: о компании, контакты, лаборатория НК, портфолио.
- Реализовать страницы производственных участков: слесарно-механический, токарный парк, трубопроводный, электрика и автоматика.
- Настроить систему глобальных стилей на CSS-переменных (токены, сбросы, компонентные стили).
- Настроить сборку через Vite с HMR и продакшн-бандлом.

#### Результат

- Готовый многостраничный сайт с единым оформлением и навигацией.
- Структурированная архитектура: components, pages, production, styles, assets.
- Единая система стилей через CSS-переменные — цвета и шрифты меняются централизованно.
- Страницы производственных участков вынесены в отдельные маршруты с общей обёрткой ProductionLayout.
- Быстрая сборка и dev-сервер на Vite, стилизация на Bootstrap 5 без JS-плагинов.
- Интерфейс на русском языке, ориентирован на десктопные экраны.

### Translit — веб-приложение для транслитерации.

[![Translit](https://github.com/danroman-repo/translit/blob/main/pic/screenshot-light_64.png)](https://github.com/danroman-repo/site-company/)

#### Поставленные задачи

- SPA с двумя полями: при вводе кириллицы во втором поле динамически, без перезагрузки, появляется латиница («вода» → «voda»).
- Эндпоинт POST /api: {"data":"апишка"} → {"status":"success","data":"apishka"}
- Эндпоинт GET /history?n=N → {"data":["voda","apishka",...]}.
- Все запросы сохранять в LevelDB.

#### Результат

- Fullstack-приложение с разделением на backend/ и frontend/.
- Frontend: компоненты TranslitInput и History, real-time транслит через fetch с двухуровневым debounce (200 мс — UI, 1500 мс — запись в БД), что не засоряет историю промежуточными ki → kir → kirpich. Адаптивная вёрстка, proxy в Vite.
- Backend: POST /api с флагом save (по умолчанию не пишет в БД), GET /history?n=N с валидацией (1–100, дефолт 5), отдача собранной статики из frontend/dist. Таблица транслитерации на ~66 символов с диграфами (ж → zh, щ → shch и т.д.).
- LevelDB: ключи-счётчики (000000000001), восстановление счётчика при старте, дедупликация (не пишем дубль последнего output), выборка через iterator({ reverse: true, limit: n }).

Стек: React 18, TypeScript, Vite, Node.js, Express, LevelDB

### Currency Converter - веб-приложение для конвертации валют по курсам Центрального банка РФ. 

[![Translit](https://github.com/danroman-repo/currency_converter/blob/main/pic/screenshot-dark.png)](https://github.com/danroman-repo/currency_converter/)

#### Поставленные задачи

- Разработать SPA с двумя страницами: конвертер и таблица актуальных курсов.
- Реализовать парсер ввода в свободной форме (15 usd in rub).
- Реализовать конвертацию через промежуточную базу (рубль) по курсам ЦБ РФ.
- Добавить выбор базовой валюты с автоопределением по языку браузера и сохранением в localStorage.
- Реализовать тёмную/светлую тему с автоопределением системной и ручным переключением.
- Настроить кэширование данных ЦБ на 30 минут.
- Обеспечить адаптивность и доступность (ARIA, семантика, prefers-reduced-motion).
- Покрыть ключевую логику тестами (Vitest + Testing Library).

#### Результат

- Готовое SPA с конвертером свободного ввода и таблицей курсов относительно выбранной базовой валюты.
- Универсальный механизм конвертации через рубль — работает для любой пары валют из списка ЦБ.
- Кэш на 30 минут: повторные запросы мгновенны, данные ЦБ не перегружаются.
- Базовая валюта и тема сохраняются между сессиями, тема подхватывает системную.
- Доступный интерфейс: семантическая разметка, aria-label, role="alert", видимый фокус.
- Покрыты тестами парсер ввода и форматирование чисел, настроен CI-режим (test:run).
- Адаптивная вёрстка на CSS-переменных, работает на мобильных и десктопе.

Стек: React 19, TypeScript, Vite 8, React Router 7, Vitest, ESLint 9

### TaskFlow — личный менеджер задач для начинающего специалиста.

[![Translit](https://github.com/danroman-repo/taskflow/blob/main/pic/tasks.png)](https://github.com/danroman-repo/taskflow/)

#### Поставленные задачи

- Регистрация и авторизация пользователей (JWT).
- Доступ к API только для авторизованных, работа только со своими задачами.
- CRUD задач, смена статуса (new, in_progress, done), фильтр по статусу.
- Прикрепление одного файла: изображение или PDF до 5 МБ.
- Валидация: название 3–100 символов, описание до 500 символов.
- SPA на React: страницы регистрации, входа, списка, создания, просмотра, редактирования.
- Превью изображения и ссылка на PDF, индикаторы загрузки, сообщения об ошибках.
- Адаптивная вёрстка от 375 px.
- README с инструкцией по запуску.

#### Результат

- Готовое fullstack-приложение в публичном репозитории.
- Backend: Django + DRF + PostgreSQL. REST API с JWT, модель Task, разграничение доступа, валидация полей и файлов, фильтр по статусу, раздача media, CORS.
- Frontend: React + Vite + React Router + Axios. Приватные маршруты, контекст авторизации, автообновление токена, фильтр, формы с загрузкой файла, превью в карточке, индикаторы загрузки и ошибки, адаптив от 375 px.
- Документация: README, разделение на backend/ и frontend/, .env.example, .gitignore.

Стек: Python 3.13, Django 6, DRF, SimpleJWT, PostgreSQL, React 18, React Router 6, Axios, Vite.

### My Cloud — Облачное хранилище файлов

[![Translit](https://github.com/danroman-repo/mycloud/blob/main/pic/Main.png)](https://github.com/danroman-repo/mycloud/)

Полнофункциональное веб-приложение для облачного хранения файлов с разграничением прав доступа, публичными ссылками для обмена и административной панелью. Разработано как дипломный проект по профессии «Fullstack-разработчик на Python».

#### Поставленные задачи

- Разработать REST API для хранения, скачивания и управления файлами.
- Реализовать регистрацию и аутентификацию с валидацией данных и CSRF-защитой.
- Добавить просмотр файлов в браузере (изображения, PDF, видео).
- Реализовать обмен файлами через обезличенные публичные ссылки (UUID) без авторизации.
- Создать админ-панель: управление пользователями, правами и их файлами.
- Настроить production-развёртывание (Gunicorn + Nginx, сборка фронтенда).

#### Результат

- Полнофункциональное SPA-приложение с разграничением прав (пользователь / админ / аноним).
- Полный CRUD для файлов: загрузка с комментариями, переименование, редактирование, удаление, скачивание с оригинальным именем.
- Публичный доступ к файлам по UUID-ссылкам без авторизации.
- Админ-панель со статистикой по количеству и объёму файлов пользователей.
- Готовый к деплою проект с конфигурацией через .env и раздельными настройками dev/prod.

Стек: Python, Django, DRF, PostgreSQL, React, Redux Toolkit, Nginx, Gunicorn

### Дипломы и сертификаты:

<div>
<img src="https://github.com/danroman-repo/resources/blob/main/Fullstack-development.jpg" height="64" title="Fullstack-разработчик"> 
 <img src="https://github.com/danroman-repo/resources/blob/main/React.png" height="64" title="React">
<img src="https://github.com/danroman-repo/resources/blob/main/Django.png" height="64" title="Django - создание backend-приложений"> 
 <img src="https://github.com/danroman-repo/resources/blob/main/Git.png" height="64" title="Git - система контроля версий"> 
<img src="https://github.com/danroman-repo/resources/blob/main/JavaScript_an_advanced_course_in_Web.png" height="64" title="JavaScript углубленный курс вебразработки">
 <img src="https://github.com/danroman-repo/resources/blob/main/HTML-CSS.png" height="64" title="HTML и CSS основы веб-верстки">
</div>


### О себе:

Самостоятельно изучал языки программирования, программирование баз данных. По работе делал проекты по программированию промышленных контроллеров. 

Нашел и изучил курс Нетологии «Fullstack-разработчик на Python». Решил продолжить карьеру в программировании. 

Увлекает создание нового и решения сложных задач.
