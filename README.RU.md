# everyGULP

Language: [EN](https://github.com/AntonGorban/everyGULP/blob/master/README.md) | [RU](https://github.com/AntonGorban/everyGULP/blob/master/README.RU.md)

## About

`everyGULP` это task-manager, созданный специально для front-end web-разработчиков. Его основными функциями являются:

- сборка проекта
  - минимизация кода и изображений
  - компиляция препроцессоров
  - автоматическое проставление префиксов в CSS
  - генерация sourcemaps
  - работа с PHP
- запуск live server

---

## Getting started

### Installing

Изначально нужно установить
[Node.js](https://nodejs.org)
(latest или LTS версию)

Далее, вам понадобиться консоль, можно установить
[Git bash](https://git-scm.com/download)
, или вы можете использовать свою.

Вы должны установить `gulp` и `bower` глобально. Для этого введите в консоль следующие команды:

```
npm i -g gulp
npm i -g bower
```

Скачайте `everyGULP` в папку проекта. Вы можете скачать и распаковать архив, или воспользоваться командой:

```
git clone https://github.com/antongorban/everygulp.git
```

или такой, скачать чтобы репозиторий в корень папки:

```
git clone https://github.com/antongorban/everygulp.git ./
```

> файлы `everuGULP` должны находится в корне папки проекта, без вложенностей

Затем откройте консоль в папке проекта и установите все зависимости, введя эти команды в консоль:

```
npm i
bower i
```

Готово, теперь вы можете сами создать структуру проекта или написать команду для развертывания `gulp project`. Чтобы запустить работу everyGULP введите в консоль `gulp`. Чтобы ознакомиться со всеми командами, вы можете ввести `gulp help`.

---

## Command list

- `gulp` - запустить стандартый task (build, server, watching)
- `gulp build` - собрать проект
- `gulp server` - запустить живой сервер
- `gulp project` - развернуть шаблонный проект
- `gulp clean` - удалить собранный проект
- `gulp help` - вывести информацию о командах
- `gulp watching` - запустить слежение за файлами
- `gulp vendorJS` - переместить JS файлы из bower в проект
- `gulp vendorCSS` - переместить CSS файлы из bower в проект
- `gulp build:PUG` - собрать файлы PUG
- `gulp build:HTML` - собрать файлы HTML
- `gulp build:SCSS` - собрать файлы SCSS
- `gulp build:CSS` - собрать файлы CSS
- `gulp build:JS` - собрать файлы JS
- `gulp build:img` - собрать изображения
- `gulp build:fonts` - собрать шрифты

---

## Settings

В начале `gulpfile.js` есть пользовательские настройки, и вот, что вы можете там настроить:

- `coloring` - подсветка логов
  - `true` [default]
  - `false`
- `voice` - голосовые уведомления
  - `true` [default]
  - `false`
- `notifies` - обычное уведомление
  - `true` [default]
  - `false`
- `preprocHTML` - выбор HTML препроцессора
  - `html`
  - `pug` [default]
- `preprocCSS` - выбор CSS препроцессора
  - `css`
  - `scss` [default]
- `usePHP` - использование PHP сервера
  - `true`
  - `false` [default]
- `serverPHP` - адрес PHP сервера

---

## Bower

> `bower` управляет пакетами, которые вы непосредственно используете на сайте, такими как `Bootstrap` или `JQuery`.

В `bower.json` записаны распространенные пакеты, которыми пользуюсь лично я, вы можете их удалить или записать пакеты, которые нужны вам. Пакеты записаны в разделе `dependencies`, и вы можете их изменить, как в начале, так и в процессе разработки. Чтобы установить пакеты из `dependencies`, следует прописать в консоли команду `bower i`.

Пакеты записанные в `dependencies` по умолчанию:

- `JQuery` - [site](https://jquery.com/)
- `normalize.css` - [site](https://necolas.github.io/normalize.css/)
- `Bootstrap` - [site](https://getbootstrap.com/)
- `slick-carousel` - [site](https://kenwheeler.github.io/slick/)
- `bx-slider` - [site](https://bxslider.com/)
- `arcticModal` - [site](https://arcticlab.ru/arcticmodal/)
- `animate.css` - [site](https://animate.style/)

> WARN: если не использовать хотя бы по одному CSS и JS пакету, everyGULP будет крашиться. Исправление в разработке.

---

## Preprocessors

`everyGULP` поддерживает работу с HTML и CSS препроцессорами, такими как:

- HTML
  - PUG - [site](https://pugjs.org/api/getting-started.html)
- CSS
  - SCSS - [site](https://sass-scss.ru/)

Чтобы выбрать, с каким препроцессором вы будете работать, напишите его название в `gulpfile.js` в разделе `settings`.

> Если вы не нашли в этом списке препроцессора, которым пользуетесь вы, напишите об этом мне, и я постараюсь добавить его поддержку.

---

## Template project

Команда `gulp project` разворачивает шаблонный проект, в который входят:

    app / index.pug
    app / css / main.scss
    app / css / media.scss
    app / js / media.js
    app / img
    app / fonts

`index.pug`:

```pug
-var title = ""
-var description = ""
-var keywords = ""
-var og_img = "img/"
-var url = "https://"

doctype html
html(lang="ru")
  head
    //- About document
    meta(charset="UTF-8")
    meta(name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0")
    meta(name="description" content=description)
    meta(name="keywords" content=keywords)
    title= title
    //- Icons
    link(rel="icon" href="img/ico.ico")
    link(rel="shortcut icon" href="img/ico.ico")
    //- OG
    meta(property="og:title" content=title)
    meta(property="og:type" content="website")
    meta(property="og:image" content=og_img)
    meta(property="og:url" content=url)
    meta(property="og:description" content=description)
    //- Styles
    link(rel="stylesheet" href="css/main.css")
  body

    script(src="js/main.js")');
```

`media.scss`:

```scss
@media screen and (max-width: 991px) {
}
```

`main.js`:

```js
$(document).ready(function () {});
```

> Созданные файлы и код в них будут отличаться при выборе других препроцессоров.

---

## PHP server (integration with OpenServer)

У `everyGULP` есть возможность работать с PHP и [OpenServer](https://ospanel.io). Для включения данной опции, вы должны в `gulpfile.js` в `settings` изменить параметр `usePHP` на `true`.

> Ваша папка проекта должна находиться в папке `domains`.

Далее запустите `OpenServer`, откройте настройки, перейдите во вкладку `Домены`, выберите в `Управление доменами` пункт `Ручное + Автопоиск` и добавьте домен, `Имя домена` может быть любое, а в поле `Папка домена` выберите путь `/site/dist`.

![Setting OpenServer (register the domain)](https://i.imgur.com/NnUmyRs.png)

Нажмите кнопку `Добавить`, а за тем `сохранить`.

![Setting OpenServer (save domain)](https://i.imgur.com/rSG8R12.png)

Затем, перейдите в `gulpfile.js` и в `settings` в `serverPHP` пропишите `[domain name]:[domain port]`, порт домена можно узнать открыв проект через `OpenServer` или в настройках, во вкладке `Сервер` ,будет значение `HTTP`.

![Settings OpenServer (domain port)](https://i.imgur.com/8g4NoBn.png)

---

## Live server

У `everuGULP` есть возможность запускать live server. С помощью него и `watching` task реализована автоматическая перезагрузка сервера при изменении кода. Также вы можете зайти на сервер с любого устройства, которе подключено к той-же WI-FI сети, что и устройство на котором запущен сервер. Для этого в консоли вам выдается специальная ссылка `External`.

![Git bash (server)](https://i.imgur.com/pwvmHB6.png)

---

## License

Этот проект лицензирован в соответствии с условиями лицензии MIT.
