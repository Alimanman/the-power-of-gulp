# 同步执行任务
---

## run-sequence

https://www.npmjs.com/package/run-sequence

```
npm install --save-dev run-sequence
```

## gulpfile.js配置

```js
const gulp = require('gulp');
const runSequence = require('run-sequence');
require('require-dir')('./gulp_task', {
    recurse: true
});

gulp.task('default', (callback) => {
    runSequence('build', 'init-dev-server', 'watch', callback);
});
```


