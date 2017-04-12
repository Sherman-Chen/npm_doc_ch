# 安装node.js和更新npm


## 安装node.js

当你使用OS X或者Windows的时候，安装Node.js的最好方式就是使用[Node.js下载页面](https://nodejs.org/en/download/)中的安装程序。如果你使用的是Linux，你可以使用安装器安装，也可以从[node二进制源](https://github.com/nodesource/distributions)检出来查看是否有适用你系统的最新版本。

测试：运行node -v来查看node的版本。node的版本应该要高于V0.10.32,。

## 更新npm

Node中捆绑了npm，因此现在我们电脑上应该有某个版本的npm了。不过npm的更新比Node频繁多了，因此我们应该确保我们适用的是最新版本的npm。

```npm install npm@latest -g```

测试：运行npm -v。npm的版本应该高于2.1.8.

## 手动安装npm

这种方式是提供给更高级的用户。

npm模块可以在下面地址中下载到：
https://registry.npmjs.org/npm/-/npm-{VERSION}.tgz