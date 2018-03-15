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

## imagemin.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个imagemin.js

```js
var gulp = require('gulp');
var runSequence = require('run-sequence');
var imagemin = require('gulp-imagemin');
var del = require('del');

gulp.task('imagemin', (callback) => {
    runSequence('clean-image', 'comp-image', callback);//先删除再压缩图片
});

gulp.task('comp-image', function () {
    return gulp.src('src/images/**/*.+(jpg|jpeg|png|gif|svg)')
        .pipe(imagemin([
            imagemin.optipng({//png
                optimizationLevel: 5
            }),
            imagemin.jpegtran({//jpeg
                progressive: true
            }),
            imagemin.svgo(),//svg
            imagemin.gifsicle({//png
                interlaced: true
            })
        ]))
        .pipe(gulp.dest('./dest/images/'));
});

gulp.task('clean-image', function () {
    return del('./dest/images/');
});
```