# 效率的编写css
---

## gulp-sass

https://www.npmjs.com/package/gulp-sass
强大的css扩展语言，让css编写更效率。

```
$ npm install --save-dev gulp-sass
```

## sass.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个sass.js

```js
var gulp = require('gulp');
var sass = require('gulp-sass');

gulp.task('sass', function () {
    return gulp.src('./src/sass/*.scss')//scss目录
        .pipe(sass({
            outputStyle: 'compact'
        }).on('error', sass.logError))
        .pipe(gulp.dest('./dest/css'));//css导出目录
});

```





