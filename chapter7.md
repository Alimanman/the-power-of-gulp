# 实时刷新页面
---

## browser-sync

http://www.browsersync.cn/docs/gulp/
省时的浏览器同步测试工具。
监听html，结构必须符合标准，否则可能无法实施刷新。

```
$ npm install --save-dev browser-sync
```

## dev-server.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个dev-server.js

```js
var gulp = require('gulp');
var browserSync = require('browser-sync').create();

gulp.task('init-dev-server', function () {
    browserSync.init({
        server: './dest'
    });
});

module.exports = browserSync;//模块导出，便于其他组件使用
```

---

## gulp-watch

https://www.npmjs.com/package/gulp-watch/
监听文件变化

```
$ npm install --save-dev gulp-watch
```

## watch.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个watch.js

```js
var gulp = require('gulp');
var watch = require('gulp-watch');

gulp.task('watch', function () {
    watch('src/*.scss', function () {//监听scss
        gulp.start('sass');
    });

    watch('src/*.pug', function () {//监听pug
        gulp.start('pug');
    });
});
```

---

## pug和sass调用browserSync

```js
var gulp = require('gulp');
var pug = require('gulp-pug');
var browserSync = require('./dev-server');

gulp.task('pug', function () {
    return gulp.src('./src/*.pug')
        .pipe(pug({
            pretty: true
        }))
        .pipe(gulp.dest('./dest/'))
        .on('end', function () {
            browserSync.reload();
        });
});
```

```js
var gulp = require('gulp');
var sass = require('gulp-sass');
var browserSync = require('./dev-server');

gulp.task('sass', function L() {
    return gulp.src('./src/*.scss')
        .pipe(sass({
            outputStyle: 'compact'
        }).on('error', sass.logError))
        .pipe(gulp.dest('./dest/css'))
        .pipe(browserSync.stream({ match: '**/*.css' }));
});
```

这两种监听方法都可以实现监听刷新。










