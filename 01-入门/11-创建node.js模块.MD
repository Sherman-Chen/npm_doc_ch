# 创建node.js模块

node.js模块也是一种能够发布到npm上的包。当你创建一个新的模块的时候，你或许该先从package.json文件开始。

你可以运行npm init来创建一个packae.json文件。它将会引导你填写一些值用来设置package.json。有两个字段是必须的，分别是name和version。除此之外，你或许还想设置入口文件名(entry point)，不过也可以使用默认的文件名：index.js。

如果你想设置作者字段的话，你应该使用下面的格式：

你的名字 <邮箱> (个人网站)

一旦你创建好了package.json，你还应该创建一个入口文件，这个文件会在你的模块被require的时候加载。如果在创建package.json的时候你使用缺省配置，这个时候你应该创建的文件应该是index.js。

在index.js文件中，创建一个函数，并且设置为exports的属性。那么这个函数就对外暴露，能够在其他模块或者代码中使用了。

```
exports.printMsg = function() {
  console.log("This is a message from the demo package");
}
```

测试：

1. 发布你的包到npm中
2. 创建一个新的目录（不是你已经创建了的node.js模块），并且cd到里面
3. 运行npm install <你发布的包名>
4. 创建一个test.js文件，在这个文件中require你创建的包，和调用暴露的函数
5. 运行node test,js。This is a message from the demo package消息将会被打印。
