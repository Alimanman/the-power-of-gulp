# 管理任务
---

## require-dir

https://www.npmjs.com/package/require-dir
gulp的各种任务（task）放在指定文件夹中，方便结构清晰。

```
$ npm install --save-dev require-dir
```

## gulpfile.js配置

```js
require('require-dir')('./gulp_task', {
    recurse: true
});
```

## task文件夹结构

```
+ gulp_task
  - build.js
  - sass.js
  - watch.js
  - ...
```




