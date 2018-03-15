# 图片压缩
---

## 基本流程

1. 清空原始图片
2. 压缩图片

## gulp-imagemin

https://www.npmjs.com/package/gulp-imagemin

```
$ npm install --save-dev gulp-imagemin
```

## sass.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个imagemin.js

```js
var gulp = require('gulp');
var sass = require('gulp-sass');

gulp.task('sass', function () {
return gulp.src('./src/*.scss')//scss目录
.pipe(sass({
outputStyle: 'compact'
}).on('error', sass.logError))
.pipe(gulp.dest('./dest/css'));//css导出目录
});

```