# 实时刷新页面
---

## browser-sync

http://www.browsersync.cn/
省时的浏览器同步测试工具。

```
$ npm install -g browser-sync
$ npm install --save-dev browser-sync
```

## pug.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个sass.js

```js
var gulp = require('gulp');
var sass = require('gulp-sass');

gulp.task('sass', function buildHTML() {
    return gulp.src('./src/*.scss')//scss目录
        .pipe(sass({
            outputStyle: 'compact'
        }).on('error', sass.logError))
        .pipe(gulp.dest('./dest/css'));//css导出目录
});

```





