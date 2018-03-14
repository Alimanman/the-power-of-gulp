# 同步执行任务
---

## run-sequence

https://www.npmjs.com/package/run-sequence
`run-sequence` 的作用就是控制多个任务进行顺序执行或者并行执行

```
$ npm install --save-dev run-sequence
```

## gulpfile.js配置

```js
var gulp = require('gulp');
const runSequence = require('run-sequence');

gulp.task('default', (callback) => {
    runSequence('one', 'two', 'three', callback);//设置运行顺序
});

gulp.task('one', function () {
    return console.log('~one~');
});
gulp.task('two', function () {
    return console.log('~two~');
});
gulp.task('three', function () {
    return console.log('~three~');
});
```

输出结果：

```
~one~
~two~
~three~
```


