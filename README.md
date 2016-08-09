#**How to minify projects with Gulp**

##**What is Gulp?**

Gulp is a build system which allows automate common development tasks, such as code minification, image compression, syntax validation code and much more.

Gulp.js is built with Javascript and works on Node.js and is Open Source Code you can find it on Github.

###**How does Gulp.js work?**
Gulp.js uses Stream Node.js module, it makes faster to build than Grunt.js.

Don´t need to write temporary files in Hard Disk, which means that perform the same tasks as Grunt.js but in less time.


###*Requeriments*
+ You need install Node.js 

###**Installation**
To install Gulp.js globally in your system

	npm install -g -gulp

If you are using Unix based systems maybe you need administrator privilegies adding *sudo* before command, like this:

	sudo install -g -gulp

to verify it was installed correctly:

	gulp -v 

If is installed correctly, you will see something like this:

	CLI version 3.9.1
	Local version 3.9.1

+ *CLI version:* Is the Gulp.js version installed.
+ *Local version* Is Gulp.js version installed on the local project.


Create **gulpfile.js** file in the root directory of your project.

After that, enter the command 

	npm init

NPM uses the package.json file to store all important datas into your application.
After entering the command, questions will be prompt to you to properly configure the app. (project name, version, etc.).

When configure is finished a new file was created called *package.json* and will contain something like that: 

	{
	 "name": "gulp-demo",
	"version": "0.0.0",
	"description": "",
    "main": "gulpfile.js",
    "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
    },
    "author": "Luis",
    "license": "ISC",
    }

Now you need to add the development dependencies to the project and the first to install will be **Gulp** with the next command:

	npm install --save-dev gulp

After that **gulp-concat** 
	
	npm install --save-dev gulp-concat

And finally **gulp-uglify**

	npm install --save-dev gulp-uglify

It´s necessary to add *--save-dev* in command  to add this package as a devlopment dependency of your project.

After that you need to create a directory called **js** and other inside called **source** here we keep the files **.js**

Now you need to add this code in gulpfile.js

```json
	/*
	    * Dependencias
	    */
	    var gulp = require('gulp'),
	    concat = require('gulp-concat'),
	    uglify = require('gulp-uglify');
		 /*
	    * Configuración de la tarea 'demo'
	    */
	   gulp.task('demo', function () {
	   gulp.src('js/source/*.js')
       .pipe(concat('todo.js'))
       .pipe(uglify())
       .pipe(gulp.dest('js/build/'))
       });
```

And with that the configuration is ready!

To test use te command:

	gulp demo


If everything its correct you finally see something like this:

	[13:18:30] Using gulpfile ~/Desktop/gulp-      demo/gulpfile.js
	[13:18:30] Starting 'demo'...
	[13:18:30] Finished 'demo' after 13 ms

	







