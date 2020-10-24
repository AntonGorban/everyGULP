# everyGULP

Language: [EN](https://github.com/AntonGorban/everyGULP/blob/master/README.md) | [RU](https://github.com/AntonGorban/everyGULP/blob/master/README.RU.md)

## About

`everyGULP` is a task-manager developed for front-end web developers. Its main functions are:

- build a project
  - minification of code and images
  - compilation of preprocessors
  - CSS autoprefixing
  - generating sourcemaps
  - work with PHP
- start live server

---

## Getting started

### Installing

Initially you need to install
[Node.js](https://nodejs.org)
(latest or LTS version)

Next, you will need a console, you can install
[Git bash](https://git-scm.com/download)
, or use your own.

You need to install `gulp` and `bower` globally. To do this, enter the following commands into the console:

```
npm i -g gulp
npm i -g bower
```

Download `everyGULP` to your project folder. You can download and unpack the archive, or use the command:

```
git clone https://github.com/antongorban/everygulp.git
```

or such that the repository is downloaded to the root of the folder:

```
git clone https://github.com/antongorban/everygulp.git ./
```

> `everuGULP` files must be in the root of the project folder, no nesting

Then open a console in the project folder and install all dependencies by entering these commands into the console:

```
npm i
bower i
```

Done, now you can create the project structure yourself or write a command to deploy the `gulp project`. To run everyGULP, enter `gulp` in the console. To see all the commands, you can type `gulp help`.

---

## Command list

- `gulp` - Start default task (build, server, watching)
- `gulp build` - Build a project
- `gulp server` - Start live server
- `gulp project` - Deploy template project
- `gulp clean` - Remove build project
- `gulp help` - Show info about commands
- `gulp watching` - Start watching files
- `gulp vendorJS` - Drop bower JS files in project
- `gulp vendorCSS` - Drop bower CSS files in project
- `gulp build:PUG` - Build PUG files
- `gulp build:HTML` - Build HTML files
- `gulp build:PHP` - Build PHP files
- `gulp build:SCSS` - Build SCSS files
- `gulp build:CSS` - Build CSS files
- `gulp build:JS` - Build JS files
- `gulp build:img` - Build img files
- `gulp build:fonts` - Build fonts files

---

## Settings

At the beginning of the `gulpfile.js` there is a settings, and this is what you can configure there:

- `coloring` - coloring logs
  - `true` [default]
  - `false`
- `voice` - voice notifications
  - `true` [default]
  - `false`
- `notifies` - default notifications
  - `true` [default]
  - `false`
- `preprocHTML` - choose HTML preprocessor
  - `html`
  - `pug` [default]
- `preprocCSS` - choose CSS preprocessor
  - `css`
  - `scss` [default]
- `usePHP` - use PHP server
  - `true`
  - `false` [default]
- `serverPHP` - domain PHP server

---

## Bower

> `bower` manages packages that you directly use on the site, such as `Bootstrap` or `jQuery`.

`Bower.json` contains common packages that I personally use, you can remove them or write packages that you need. Packages are written in the `dependencies` section, and you can change them both at the beginning and during development. To install packages from `dependencies`, you should write the `bower i` command in the console.

Packages written in `dependencies` by default:

- `JQuery` - [site](https://jquery.com/)
- `normalize.css` - [site](https://necolas.github.io/normalize.css/)
- `Bootstrap` - [site](https://getbootstrap.com/)
- `slick-carousel` - [site](https://kenwheeler.github.io/slick/)
- `bx-slider` - [site](https://bxslider.com/)
- `arcticModal` - [site](https://arcticlab.ru/arcticmodal/)
- `animate.css` - [site](https://animate.style/)

> WARN: if you don't use at least one CSS and JS package each, everyGULP will crash. Development fix.

---

## Preprocessors

`everyGULP` supports HTML and CSS preprocessors, such as:

- HTML
  - PUG - [site](https://pugjs.org/api/getting-started.html)
- CSS
  - SCSS - [site](https://sass-scss.ru/)

To choose which preprocessor you will work with, write its name in `gulpfile.js` in the section `settings`.

> If you have not found the preprocessor you are using in this list, write to me about it, and I will try to add support for it.

---

## Template project

The `gulp project` command deploys a template project that includes:

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

> The generated files and the code in them will be different when choosing other preprocessors.

---

## PHP server (integration with OpenServer)

`everyGULP` has the ability to work with PHP and [OpenServer](https://ospanel.io). To enable this option, you must change the `usePHP` parameter to `true` in `gulpfile.js` in `settings`.

> Your project folder should be in the `domains` folder.

Next, start `OpenServer`, open the settings, go to the `Domains` tab, select `Manual + Autosearch` in `Domain Management` and add a domain, `Domain name` can be any, and in the `Domain folder` field select the path `/site/dist`.

![Setting OpenServer (register the domain)](https://i.imgur.com/vbBJYCl.png)

Click the `Add` button and then `Save`.

![Setting OpenServer (save domain)](https://i.imgur.com/fK37BS2.png)

Then, go to `gulpfile.js` and in `settings` in `serverPHP` write `[domain name]: [domain port]`, the domain port can be found by opening the project through `OpenServer` or in the settings, in the `Server` tab , the value will be `HTTP`.

![Settings OpenServer (domain port)](https://i.imgur.com/vPIDqVR.png)

---

## Live server

`everyGULP` has the ability to run a live server. With the help of it and the `watching` task, automatic server restart is implemented when the code changes. You can also log into the server from any device connected to the same WI-FI network as the device on which the server is running. To do this, a special `External` link is given to you in the console.

![Git bash (server)](https://i.imgur.com/pwvmHB6.png)

---

## License

This project is licensed under the terms of the MIT license.
