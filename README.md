# iView-project

This project is build for Vue.js 2 + vue-router + webpack2 + iView 3, just install and run.

## Install
```bush
// install dependencies
npm install
```
## Run
### Development
```bush
// For the first time, run init to create index.html
npm run init
npm run dev
```
### Production(Build)
```bush
npm run build
```

### 问题解决
```bush
mac电脑上运行前准备阶段会出现两个问题（简单记录，不排除个人原因）：
1.npm ERR! iview-project@3.0.0 init: `webpack --progress --config webpack.dev.config.js
  解决方法：
  fs.write(fd, buf, 0, buf.length, 0, function (err, written, buffer){});
  修改成
  fs.write(fd, buf, 0, 'utf-8', function (err, written, buffer) {})
2.gyp ERR! cwd /Users/bobo/j2ee/gitcodes/renren-fast-vue/node_modules/node-sass
  解决方法：
  先在package.json文件中的 dependencies 下配置：
  ...
  "node-sass":"^4.13.0"
  ...
  然后：
  // 1、清除npm缓存（由于是在Mac系统下，执行npm cache clean --force命令时前面需要加sudo获取权限）
  sudo npm cache clean --force
  // 2、删除node_modules文件（也可手动删除node_modules文件夹）
  rm -rf node_modules
  // 3、重新执行安装
  npm install
```
