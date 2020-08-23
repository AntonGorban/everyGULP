# gulpfile
This is my gulpfile.js
## About
It is built on Gulp 4. It supports preprocessors:
* Pug/Jade
* SCSS

Implemented:
* minification of code and images
* building project
* live server
* deployment of the template project
* automatic prefixing in CSS code
* command reference `gulp help`
* on compilation error, work will not stop
* the error log is displayed in red
* in case of an error, a voice notification will occur
## Command List
* `gulp` - Start default task 
* `gulp build` - Build a project 
* `gulp server` - Start live server 
* `gulp project` - Deploy template project 
* `gulp clean` - Remove build project 
* `gulp help` - Show info about commands 
* `gulp watching` - Start watching files 
* `gulp vendorJS` - Drop bower JS files in project 
* `gulp vendorCSS` - Drop bower CSS files in project 
* `gulp build:PUG` - Build PUG files 
* `gulp build:HTML` - Build HTML files 
* `gulp build:SCSS` - Build SCSS files 
* `gulp build:CSS` - Build CSS files 
* `gulp build:JS` - Build JS files 
* `gulp build:img` - Build img files 
* `gulp build:fonts` - Build fonts files
## Download
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
By the way, bower is used to install frameworks like `Bootstrap` or `jQuery`, by going to `bower.json` you can write the frameworks you need.

Next, open the console in the project folder and install all dependencies by typing these commands into the console:
```
npm i
bower i
```
Done, now you can create a structure or write a command to deploy a template project `gulp project`. To run the default task type `gulp`, and to see all the commands you can type `gulp help`.
