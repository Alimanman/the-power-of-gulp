# 启动初始化
---

## 基本流程

每次gulp开启后，能初始化开发目录里的内容。

流程如下：
1. 清空clean开发目录（dest）
2. 编译pug内容
3. 编译sass内容
4. 压缩图片（生产环境）
5. 拷贝copy，复制html和css以外的内容

先看gulefile.js的default部分的最终代码

```js
gulp.task('default', (callback) => {
    runSequence('clean', ['pug', 'sass', 'copy'], 'init-dev-server', 'watch', callback);
});
```

pug和sass已有了，先来建立clean任务。

---

## del

https://www.npmjs.com/package/del

```
$ npm install --save-dev del
```

## clean.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个clean.js

```js
var gulp = require('gulp');
var del = require('del');

gulp.task('clean', function () {
    return del('./dest');//直接删除dest文件夹
});
```

然后我们来建立copy任务。

---

## gulp.dest

使用gulp内置的dest写入文件来拷贝
同样，在gulp_task文件夹下新建一个copy.js

```js
var gulp = require('gulp');

gulp.task('copy', function () {
    gulp.start('copy-images');//集合处理
    gulp.start('copy-js');
});

gulp.task('copy-images', function () {
    gulp.src('./src/images/**/*', {//文件夹内没内容，不会拷贝
        base: './src'
    })
        .pipe(gulp.dest('./dest'));
});

gulp.task('copy-js', function () {
    gulp.src('./src/js/**/*', {//文件夹内没内容，不会拷贝
        base: './src'
    })
        .pipe(gulp.dest('./dest'));
});
```





