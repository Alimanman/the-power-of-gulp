# 效率的编写css
---

## gulp-sass

https://www.npmjs.com/package/gulp-sass
强大的css扩展语言，让css编写更效率。

```
$ npm install gulp-sass --save-dev
```

## pug.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个sass.js

```js
var gulp = require('gulp');
var sass = require('gulp-sass');

gulp.task('sass', function buildHTML() {
    return gulp.src('./src/*.sass')//sass目录
        .pipe(sass({
            outputStyle: 'compact'
        }).on('error', sass.logError))
        .pipe(gulp.dest('./dest/css'));//css导出目录
});

```





