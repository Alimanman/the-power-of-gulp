# 优雅的编写html
---

## gulp-pug

https://www.npmjs.com/package/gulp-pug
Pug原名不叫Pug，是大名鼎鼎的jade，后来由于商标的原因，改为Pug。
使用缩进排列来方式来写html，功能强大。

```
$ npm install --save-dev gulp-pug
```

## pug.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个pug.js

```js
var gulp = require('gulp');
var pug = require('gulp-pug');

gulp.task('pug', function () {
    return gulp.src('./src/*.pug')//pug目录
        .pipe(pug({
            pretty: true
        }))
        .pipe(gulp.dest('./dest/'));//html导出目录
});
```

> return是实现链式调用，类似jQuery。





