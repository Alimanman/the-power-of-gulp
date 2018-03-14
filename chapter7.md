# 实时刷新页面
---

## browser-sync

http://www.browsersync.cn/docs/gulp/
省时的浏览器同步测试工具。

```
$ npm install -g browser-sync
$ npm install --save-dev browser-sync
```

## dev-server.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个dev-server.js

```js
var gulp = require('gulp');
var sass = browserSync = require('browser-sync').create();

gulp.task('init-dev-server', function () {
    browserSync.init({
        server: './dest'
    });
});

```





