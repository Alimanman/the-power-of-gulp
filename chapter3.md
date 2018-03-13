# 同步执行任务
---

## run-sequence

https://www.npmjs.com/package/run-sequence
`run-sequence` 的作用就是控制多个任务进行顺序执行或者并行执行

```
npm install --save-dev run-sequence
```

## gulpfile.js配置

```js
const gulp = require('gulp');
const runSequence = require('run-sequence');
require('require-dir')('./gulp_task', {//设置文件夹名字和位置
    recurse: true
});

gulp.task('default', (callback) => {
    runSequence('build', 'init-dev-server', 'watch', callback);
});
```


