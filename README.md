[![Gitter](https://badges.gitter.im/CinemaPress/CinemaPress-CMS.svg)](https://gitter.im/CinemaPress/CinemaPress-CMS?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge)

# CinemaPress CMS
 :movie_camera: Система управления самообновляемым кино-сайтом.
 
# CinemaPress DataBase
 :minidisc: База данных ~ 500 000 фильмов (все фильмы/сериалы планеты).

## Установка:
Работает на Debian 7,8 (64-bit)
```
~# wget https://git.io/v2XAV -qO install.sh
~# sh install.sh [domain] [theme]
```

##### Пример:
```
~# sh install.sh mydomain.com barney

---------------------- DOMAIN URL --------------------------------
mydomain.com
------------------------ THEME -----------------------------------
barney
------------------------------------------------------------------
```

### Установка темы оформления

- [Barney (kinogo.cc)](https://github.com/CinemaPress/Theme-Barney)
```
~# sh theme.sh barney
```
<a href="https://github.com/CinemaPress/Theme-Barney"><img src="https://raw.githubusercontent.com/CinemaPress/Theme-Barney/master/screenshot.jpg" width="400"></a>
---
- [Ted (kinogb.net)](https://github.com/CinemaPress/Theme-Ted)
```
~# sh theme.sh ted
```
<a href="https://github.com/CinemaPress/Theme-Ted"><img src="https://raw.githubusercontent.com/CinemaPress/Theme-Ted/master/screenshot.jpg" width="400"></a>
---
- [Lily (kinokong.net)](https://github.com/CinemaPress/Theme-Lily)
```
~# sh theme.sh lily
```
<a href="https://github.com/CinemaPress/Theme-Lily"><img src="https://raw.githubusercontent.com/CinemaPress/Theme-Lily/master/screenshot.jpg" width="400"></a>
---
- [Marshall (zerx.cc)](https://github.com/CinemaPress/Theme-Marshall)
```
~# sh theme.sh marshall
```
<a href="https://github.com/CinemaPress/Theme-Marshall"><img src="https://raw.githubusercontent.com/CinemaPress/Theme-Marshall/master/screenshot.jpg" width="400"></a>

# Что такое CinemaPress CMS?
Это система управления самообновляемым кино-сайтом, которая строится на базе данных CinemaPress и работает на nodeJS (express) + Sphinx.

![Admin page CinemaPress CMS](https://raw.githubusercontent.com/CinemaPress/CinemaPress.github.io/master/images/admin/screen.png)

# Основное
- **Домен** - доменное имя Вашего сайта, без http:// и обратного слеша в конце, например «example.com»;
- **Email** - электронная почта для связи с администрацией сайта;
- **Disqus** - Ваш "shortname".disqus.com на сайте [disqus](https://disqus.com/admin/create/), требуется для того, чтобы Вы через свой аккаунт могли модерировать комментарии Ваших пользователей;
- **Тема** - название темы оформления, должно быть с точности таким как называется папка с темой в дирректории themes.

# Параметры URL
- **Страница фильма** - Как будет выглядеть URL страница фильма;

```
По умолчанию: http://example.com/movie/id299-Матрица-The Matrix

Доступные параметры:
[prefix_id] - обязательный праметр, отображает ID фильма, например «id299»;
[separator] - разделитель между параметрами, например «-»;
[title_ru] - русское название, например «Матрица»;
[title_en] - оригинальное название, например «The Matrix»;
[genre] - жанр фильма, например «комедия»;
[country] - страна фильма, например «США»;
[year] - год фильма, например «2016»;
[actor] - главный актер, например «Том Круз»;
[director] - режиссер, например «Тим Бертон».
```

- **URL фильма** - Как будет выглядеть URL страница фильма;

```
Например: http://example.com/movie/id299-Матрица-The Matrix
```

- **URL года** - Как будет выглядеть URL страница года;

```
Например: http://example.com/year/2016
```

- **URL жанра** - Как будет выглядеть URL страница жанра;

```
Например: http://example.com/genre/комедия
```

- **URL страны** - Как будет выглядеть URL страница страны;

```
Например: http://example.com/country/США
```

- **URL актера** - Как будет выглядеть URL страница актера;

```
Например: http://example.com/actor/Том Круз
```

- **URL режиссера** - Как будет выглядеть URL страница режиссера;

```
Например: http://example.com/director/Тим Бертон
```

- **URL типа** - Как будет выглядеть URL страница типа;

```
Например: http://example.com/type/Сериалы
```

- **URL поиска** - Как будет выглядеть URL страница поиска;

```
Например: http://example.com/search/Аватар
```

- **URL карты сайта** - Как будет выглядеть URL страница карты сайта;

```
Например: http://example.com/sitemap
```

- **URL админ панели** - Должен начинаться с **admin**-secret-key, вместо secret-key любое секретное слово;

```
Например: http://example.com/admin-idiot
```

# Топ фильмы

![Top movies CinemaPress CMS](https://raw.githubusercontent.com/CinemaPress/CinemaPress.github.io/master/images/admin/top.png)

- **ID** - ID фильмов которые будут отображаться в «карусели фильмов» вверху (если это поддерживает тема оформления).

```
Например: 299,300,301,302
```

# Скрыть фильмы
- **ID** - ID фильмов на которые поступили жалобы от правообладателей и требуется ограничить их скачивание и онлайн просмотр.

```
Например: 299,300,301,302
```

# Числовые параметры
- **Время кэша (в секундах)** - Задает число в секундах, сколько будет храниться кэш в памяти, чтобы не нагружать Sphinx ресурсоёмкими запросами;
- **Полное кэширование** - включать когда ждете на сайт большой поток посетителей, после включения никакие изменения в конфигурации не будут работать, придется ждать время окончания кэша или очистить кэш через консоль:

```
~# echo "flush_all" | nc -q 2 localhost 11211
```

#### Счетчик
- **Главная** - Число фильмов на главной странице (в каждой категории «Фильмы года», «Новинки», и т.д.);
- **Категория** - Число фильмов в категориях;
- **Топ в категории** - Число топовых фильмов в категории, в большинстве шаблонах, вставляются в «карусель фильмов» в категории;
- **Связанные фильмы** - Число связанных фильмов в каждой категории, которые отображаются на странице фильма;
- **Карта сайта** - Число фильмов в карте сайта в каждом году.

# Связанные фильмы

![Related movies CinemaPress CMS](https://raw.githubusercontent.com/CinemaPress/CinemaPress.github.io/master/images/admin/related.png)

- **Страны** - Отображать связанные фильмы по всем странам оригинального фильма, одной стране или не отображать;
- **Жанры** - Отображать связанные фильмы по всем жанрам оригинального фильма, одному жанру или не отображать;
- **Актеры** - Отображать связанные фильмы по всем актерам оригинального фильма, одному актеру или не отображать;
- **Режиссеры** - Отображать связанные фильмы по всем режиссерам оригинального фильма, одному режиссеру или не отображать;
- **Год** - Отображать связанные фильмы по году или не отображать.

#### Названия связанных категорий
- **Связанные фильмы по году** - можно использовать ключ [year], куда будет подставлен год связанных фильмов;
- **Связанные фильмы по жанру** - можно использовать ключ [genre], куда будет подставлен жанр связанных фильмов;
- **Связанные фильмы по стране** - можно использовать ключ [country], куда будет подставлена страна связанных фильмов;
- **Связанные фильмы по актеру** - можно использовать ключ [actor], куда будет подставлено имя актера связанных фильмов;
- **Связанные фильмы по режиссеру** - можно использовать ключ [director], куда будет подставлено имя режиссера связанных фильмов;

# Параметры названий, описаний, ключевых слов

##### [Что такое «синонимация»?](https://github.com/CinemaPress/CinemaPress-CMS/wiki/%D0%A7%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-%C2%AB%D1%81%D0%B8%D0%BD%D0%BE%D0%BD%D0%B8%D0%BC%D0%B0%D1%86%D0%B8%D1%8F%C2%BB-%D0%B2-CinemaPress-CMS%3F)
##### [Как написать текст для определенного фильма, жанра, страны, года, актера, режиссера?](https://github.com/CinemaPress/CinemaPress-CMS/wiki/%D0%9A%D0%B0%D0%BA-%D0%BD%D0%B0%D0%BF%D0%B8%D1%81%D0%B0%D1%82%D1%8C-%D1%82%D0%B5%D0%BA%D1%81%D1%82-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D1%84%D0%B8%D0%BB%D1%8C%D0%BC%D0%B0,-%D0%B6%D0%B0%D0%BD%D1%80%D0%B0,-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D1%8B,-%D0%B3%D0%BE%D0%B4%D0%B0,-%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B0,-%D1%80%D0%B5%D0%B6%D0%B8%D1%81%D1%81%D0%B5%D1%80%D0%B0%3F)

- **Главная** - Можно использовать «синонимацию»;
- **Категория - год** - Можно использовать «синонимацию», текст для определенного года и ключи:

```
[year] - год текущей категории, на сайте отобразится например, как «2016»;
[sort] - название сортировки;
[page] - текст и номер страницы при переходе.
```

- **Категория - годы** - Можно использовать «синонимацию»;
- **Категория - жанр** - Можно использовать «синонимацию», текст для определенного жанра и ключи:

```
[genre] - жанр текущей категории, на сайте отобразится например, как «комедия»;
[sort] - название сортировки;
[page] - текст и номер страницы при переходе.
```

- **Категория - жанры** - Можно использовать «синонимацию»;
- **Категория - страна** - Можно использовать «синонимацию», текст для определенной страны и ключи:

```
[country] - страна текущей категории, на сайте отобразится например, как «Россия»;
[sort] - название сортировки;
[page] - текст и номер страницы при переходе.
```

- **Категория - страны** - Можно использовать «синонимацию»;
- **Категория - актер** - Можно использовать «синонимацию», текст для определенного актера и ключи:

```
[actor] - актер текущей категории, на сайте отобразится например, как «Том Круз»;
[sort] - название сортировки;
[page] - текст и номер страницы при переходе.
```

- **Категория - актеры** - Можно использовать «синонимацию»;
- **Категория - режиссер** - Можно использовать «синонимацию», текст для определенного режиссера и ключи:

```
[director] - режиссер текущей категории, на сайте отобразится например, как «Тим Бертон»;
[sort] - название сортировки;
[page] - текст и номер страницы при переходе.
```

- **Категория - режиссеры** - Можно использовать «синонимацию»;
- **Категория - тип** - Можно использовать «синонимацию», текст для определенного типа и ключи:

```
[type] - тип текущей категории, на сайте отобразится например, как «Сериалы»;
[sort] - название сортировки;
[page] - текст и номер страницы при переходе.
```
- **Страница поиска** - Можно использовать «синонимацию», текст для определенного поискового запроса и ключи:

```
[search] - поисковый запрос пользователя, на сайте отобразится например, как «Аватар»;
[sort] - название сортировки;
[page] - текст и номер страницы при переходе.
```

## На странице фильма
Везде можно использовать «синонимацию», текст для определенного фильма и ключи:

> **[id]** - ID фильма, например «299»;

> **[title]** - название фильма, например «Аватар / Avatar»;

> **[title_ru]** - русское название фильма, например «Аватар»;

> **[title_en]** - оригинальное фильма, например «Avatar»;

> **[description]** - стандартное описание фильма;

> **[year]** - год фильма, например «2016»;

> **[countries]** - страны фильма через запятую, например «США,Япония»;

> **[country]** - одна из стран фильма, например «США»;

> **[genres]** - жанры фильма через запятую, например «комедия,драма»;

> **[genre]** - один из жанров фильма, например «комедия»;

> **[actors]** - актеры фильма через запятую, например «Том Круз,Бред Питт»;

> **[actor]** - один из актеров фильма, например «Бред Питт»;

> **[directors]** - режиссеры фильма через запятую, например «Стивен Брилл,Питер Фаррелли»;

> **[director]** - один из режиссеров фильма, например «Стивен Брилл»;

> **[premiere]** - дата премьеры фильма, например «2016-02-12»;

# Имена сортировок
- **Сортировка по умолчанию** - сортировка по умолчанию для всех категорий.

# Аккаунты соц. сетей
- **ВКонтакте** - URL страницы ВКонтакте;
- **facebook** - URL страницы facebook;
- **twitter** - URL страницы twitter.