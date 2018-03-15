# 启动初始化
---

每次gulp开启后，能初始化开发目录里的内容。
流程如下：
1. 清空clean开发目录（dest）
2. 编译pug内容
3. 编译sass内容
4. 压缩图片（生产环境）
5. 拷贝copy

## del

https://www.npmjs.com/package/del

```
$ npm install --save-dev del
```

## clean.js配置

安装require-dir插件管理后，在gulp_task文件夹下新建一个clean.js

```js
const gulp = require('gulp');
const del = require('del');

// task
gulp.task('clean', function () {
  return del(config.path.dest);
});
```
