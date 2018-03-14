# Hello World
---

## 作为项目的开发依赖安装

1.生成package.json

> 这个文件很重要，其他人拿到你的项目，可以直接通过`$ npm i`来安装所需要的依赖包。

2.cd到目录后安装

```
$ npm install --save-dev gulp
```

```
$ npm init
```

3.在项目根目录下创建一个名为 `gulpfile.js` 的文件

```js
var gulp = require('gulp');

gulp.task('default', function() {
    console.log('Hello World');
});
```

4.中端输入gulp

```
$ gulp
```




