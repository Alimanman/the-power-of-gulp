# pug
---

## pug

https://www.npmjs.com/package/pug
gulp的各种task放在指定文件夹中，方便结构清晰。

```
$ npm install pug
$ npm install pug-cli -g
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




