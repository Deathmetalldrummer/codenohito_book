Web site development
====================

Данный список подготовлен с учетом того, что все ведущие вопросы по дизайну и usability закрывает профессиональный дизайнер, а содержание контролирует профессиональный SEOшник. Этот чеклист только для команды разработки.


Подготовка и сбор информации
----------------------------

* [x] включить мозг
* [ ] определить, должен ли сайт быть **адаптивным** или у него должна быть **мобильная версия** или просто должен без горизонтального скролла отображаться на мобильных устройствах
* [ ] анализ и оценка каждого блока сайта
* [ ] выбор платформы разработки
* [ ] узнать будущий домен сайта

* [ ] результат подготовки: **Техническая Спецификация** сайта или **Техническое Задание**, а так же стоимость работ


Дизайн
------

* [ ] выставить требования к дизайну:
    * [ ] страница со всеми заголовками, параграфами, отступами, таблицами, цитатами и прочим добром
    * [ ] несколько состояний всех видов ссылок и кнопок
    * [ ] для формы стиль поля в фокусе, а так же при ошибке
    * [ ] favicon в размере минимум 310x310px


Разработка
----------

### HTML и его формирование

* [ ] doctype каждой страницы корректно указан
* [ ] есть корневой тег `<html>`, а `<head>` и `<body>` единственные 'дети' - все остальные теги в них
* [ ] для тега `<html>` указан атрибут `lang`
* [ ] в теге `<head>` первым вложенным тегом идёт указатель кодировки файла `<meta charset="utf-8">`
* [ ] подключение основных стилей происходит в `<head>`
* [ ] подключение скриптов происходит в `<body>` после всего контента, а в `<head>` остаются только те скрипты, которые нужны для рендера страницы, например "html5shim"
* [ ] не забываем кавычки в атрибутах и, ни в коем случае, не пропускаем для каждого тега `<img>` его атрибут alt
* [ ] теги, которые надо закрывать мы закрываем в правильном порядке (`<div> ... <p>...</p></div>`)
* [ ] теги, которые не нужно закрывать, пишем в соответствии с doctype: если html, то `<br>`, а если xhtml, то `<br />`
* [ ] соблюдён порядок заголовков (h1 -> h2 -> h3, а не h1 -> h3)
* [ ] для аббревиатур используем `<abbr> ... </abbr>`
* [ ] дублированные ссылки закрыты через nofollow (например, повторение навигации из шапки в футере)
* [ ] поле поиска по сайту вложено в `<form> ... </form>`
* [ ] отметить checkbox можно с помощью клика по его label
* [ ] ошибка в форме отображаются рядом с полем, в котором ошибка, а не в начале формы
* [ ] все страницы проходят [валидацию](http://validator.w3.org/)
* [ ] на сайте нет сломанных ссылок ([проверка](http://validator.w3.org/checklink))
* [ ] сайт проходит тест [mobileOK](http://validator.w3.org/mobile/) на корректное отображение на мобильных устройствах

* [ ] все данные, которые подходят для описания в [schema.org](http://schema.org) (контакты, афиша, персоны и т.п.), описаны с помощью schema.org
* [ ] в копирайте футера есть динамический год, например чтобы сначала 2013, потом 2013—2014, 2013—2015 и т.д.

* [ ] title есть на каждой странице
* [ ] для страницы можно задать title вручную, иначе используется заголовок страницы
* [ ] title имеет структуру, которая разделяется с помощью одного символа, отбитого пробелами, например 'Австралия | Страны | Турагентство Солнышко' или 'Австралия - Страны - Турагентство Солнышко', но не 'Австралия :: Страны :: Турагентство Солнышко', хотя так и лучше смотрится
* [ ] в title со структурой всегда первым идёт часть title именно этой страницы, а название сайта - в конце
* [ ] есть возможность для любой страницы показывать title без структуры - только title этой страницы
* [ ] тег title расположен в теге head и максимально близко к его началу (выше только meta charset)

* [ ] meta тег description можно задать для каждой страницы
* [ ] meta тег keywords можно задать для каждой страницы
* [ ] ни description, ни keywords не наследуются - если они не заданы для страницы, то этих тегов просто не должно быть
* [ ] meta тег copyright задан и в нём указан владелец сайта и текущий год
* [ ] если на сайте есть система авторства статей, то обязательно указан meta тег author и, если есть возможность, `<meta http-equiv="Reply-to"` с указанием email автора
* [ ] в `<head>` указана ссылка на humans.txt: `<link rel="author" type="text/plain" href="humans.txt">`

* [ ] в `<head>` используем теги [The Open Graph protocol](http://ogp.me/), которые берут данные из title, description и keywords
* [ ] в `<head>` используем теги [Twitter Cards](https://dev.twitter.com/docs/cards), которые берут данные из title, description и keywords
* [ ] в `<head>` используем теги [MSApplication](http://msdn.microsoft.com/en-us/library/gg491732(v=vs.85).aspx)
* [ ] для каждой страницы можно задать изображение, которое используют Open Graph и Twitter Cards в своих тегах, а если это изображение не задано, то в этих тегах указана ссылка на самый большой favicon

* [ ] в корне сайта лежит favicon.ico, который состоит из 4 изображений разных размеров: 16x16 32x32 48x48 64x64 и глубиной цвета 8 бит
* [ ] в `<head>` есть линки и на базовый favicon.ico и на изображения для Apple Touch Icons, и для IE 10 Metro tile icon, и, возможно на IE 11 live tiles, а так же для прочих сервисов, типа GoogleTV, Opera и т.п. - вот [памятка](https://github.com/audreyr/favicon-cheat-sheet)

Пример правильно скомпонованной html страницы - [index.html из html-css-template от Dymio](http://github.com/dymio/html-css-template/blob/master/index.html).


### CSS и немного JS

* [ ] сайт корректно и без горизонтального скролла отображается в браузере с окном 980px в ширину или больше
* [ ] при отключенных стилях можно прочитать содержание сайта и воспользоваться навигацией по сайту
* [ ] при отключенном javascript можно прочитать содержание сайта и воспользоваться навигацией по сайту 
* [ ] предусмотрены стили для печати страницы
* [ ] у ссылок есть и :hover и :focus поведение, а так же не проигнорирован outline
* [ ] можно пользоваться навигацией по сайту с помощью только клавиатуры
* [ ] все стили и скрипты максимально возможно минимизированы и скомпонованы
* [ ] весь текст должен соответствовать правилам web-типографии (подготовка Типографом)


### Редиректы, ссылки, служебные файлы и др.

* [ ] включён 301 редирект с www.sitename.com на sitename.com (или наоборот)
* [ ] если есть ридерект с родительской на дочернюю страницу, то он с кодом 302 и вообще все коды редиректов используем [правильно](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes#3xx_Redirection))
* [ ] каждая страница отвечает с HTTP заголовками Last-Modiﬁed и If-Modiﬁed‐Since и вообще с заголовками всё в [порядке](https://redbot.org/)
* [ ] есть страницы 404, 500 и 422 ошибок и они статичны и не зависят от движка сайта
* [ ] в корне сайта размещён корректный sitemap.xml
* [ ] все страницы имеют человекочитаемый url, там где это можно сделать
* [ ] url состоит из строчных латинских символов, слова разделены символом '-', нет пробелов и используются только допустимые символы
* [ ] sitemap.xml представляет собой статичный и сжатый файл, который генерируется не по запросу клиента, а при изменении данных сайта
* [ ] в корне сайта размещён корректный robots.txt с отдельными секциями под Yandex, Google и для прочих, в котором, в том числе, указана ссылка на файл sitemap.xml
* [ ] в корне сайта размещён корректный [humans.txt](http://humanstxt.org/)


Сразу после первого деплоя на production
----------------------------------------

* [ ] открыть robots.txt
* [ ] заркгистрировать в Яндекс.Вебмастер
* [ ] подключить Яндекс.Метрику
* [ ] отправить менеджеров регистрировать сайт в Яндекс.Каталог, Гугл.Ардресах и DMOZ
* [ ] отправить менеджеров регистрировать сайт в соц. сетях
* [ ] проверить работу социальных блоков и ссылок
* [ ] мониторим работоспособность сайта [Uptime robot](http://www.uptimerobot.com/), [GotSiteMonitor.com](http://www.gotsitemonitor.com/)
* [ ] автобэкап
* [ ] проверить производительность страницы [Google Page Speed](https://developers.google.com/speed/pagespeed/), [Yahoo's YSlow](http://yslow.org/)
* [ ] проверить, нет ли ссылок на dev сайт
* [ ] проверить настройки на наличие dev данных (типа email разработчика вместо менеджера)
* [ ] заменить пароль админа
* [ ] пострелизный бэкап


Полезные ссылки
---------------

[Web Developer Checklist](http://webdevchecklist.com/)