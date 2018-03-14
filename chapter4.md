# 管理tasks
---

## require-dir

https://www.npmjs.com/package/require-dir
gulp的各种task放在指定文件夹中，方便结构清晰。

```
npm install require-dir
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



