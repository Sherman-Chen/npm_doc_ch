# 使用package.json

管理安装在本地的npm包最好的方式就是去创建一个`package.json`文件。

`package.json`文件能够提供很多有用的事情：
1. 它可以描述你的项目所依赖的包的信息

2. 它可以让你自定义你所依赖的包的版本

3. 它可以让你的构造可重复，这意味着其他程序员可以很容易与你协作

## 要求

package.json的最低要求是：
+ “name”
  + 运行小写
  + 单个单词，没有空格
  + 可以使用分隔线和下划线
+ “version”
  + 格式为：x.x.x
  + 允许语义化的版本

例如：

    {
        "name": "my-awesome-package",
        "version": "1.0.0"
    }

## 创建一个package.json文件

要创建一个package.json文件，我们可以使用：

    npm init

这行命令会以问答的形式帮助你在当前目录下创建package.json文件。

## --yes初始化标志

`npm init`的问答环节通常比较繁琐冗长，如果你想要迅速创建一个`package.json`文件，你可以使用`npm init --yes`或者是`npm init -y`来快速创建一个`package.json`文件：

    npm init --yes

这个时候，它不会再问你任何问题，而是以缺省的形式在当前目录下创建package.json文件。

```
npm init --yes
Wrote to /home/ag_dubs/my_package/package.json:
 
{
  "name": "my_package",
  "description": "",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/ashleygwilliams/my_package.git"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/ashleygwilliams/my_package/issues"
  },
  "homepage": "https://github.com/ashleygwilliams/my_package"
}
```

+ name: 当前目录的名字
+ version: 总是1.0.0
+ description: 从README.MD中获取信息或者是空字符串
+ main: 总是index.js
+ scripts: 默认创建一个空的test脚本
+ keywords: 空
+ author: 空
+ license: ISC
+ bugs: 从当前目录获取信息
+ homepage: 从当前目录获取信息

当然我们可以给init命令设置一些配置选项，比如：

```
> npm set init.author.email "wombat@npmjs.com"
> npm set init.author.name "ag_dubs"
> npm set init.license "MIT"
```

## 注意：

如果`package.json`的`description`不存在，那么npm会获取README.MD或者是README的第一行充当`description`。这个`description`字段可以帮助人们在搜索包的时候检索到你的包，因此在这个字段中应该设置一些有用的信息来让人们更好地发现你的包。

## 自定义init的处理
我们能够自定义npm init时消息和问题如何提问。可以通过创建.npm-init.js文件来实现。默认情况下，npm会查找在home目录中的.npm-init.js文件：~/.npm-init.js。

一个简单的.npm-init.js文件如下：

```
module.exports = {
  customField: 'Custom Field',
  otherCustomField: 'This field is really cool'
}
```

运行npm init在我们的home目录下的话，输出的package.json类似如下：

```
{
  customField: 'Custom Field',
  otherCustomField: 'This field is really cool'
}
```

通过使用prompt函数还可以自定义问题：

```
module.exports = prompt("what's your favorite flavor of ice cream buddy?", "I LIKE THEM ALL");
```

了解更多关于如何创建更高级的自定义文件，请查看XXX;

## 指定的包

为了支出你的项目所依赖的包，你需要将包列举在package.json中。有两种类型的包你可以指定：

+ "dependencies": 在生产环境中，该字段下的包需要被require
+ "devDependencies": 在开发环境中，该字段下的包需要被require

## 手动编辑package.json

我们还能够手动编辑package.json。你需要在package对象下增加一个dependencies属性，该属性指向某个对象。这个对象保存了一些你需要使用的包名，包名作为属性名，而值则是语义化的版本信息。

如果依赖是在开发环境中的话，则这些依赖的包应该保存在devDependencies属性下。

例如：下面的项目在生产环境中使用了大版本为1的任意版本包my_dep和在开发环境中使用了大版本为3的任意版本包`my_test_framework`：

```
{
  "name": "my_package",
  "version": "1.0.0",
  "dependencies": {
    "my_dep": "^1.0.0"
  },
  "devDependencies" : {
    "my_test_framework": "^3.1.0"
  }
}
```

## --save和--save-dev安装标志

添加一个依赖到package.json中最简单的方式是使用命令行npm install --save或者是npm install --save-dev，两种方式使用哪一种决定于如何使用包。

增加一个包到package.json的dependencies：

`npm install <package_name> --save`

增加一个包到package.json的dependencies：

`npm install <package_name> --save-dev`

## 管理依赖的版本

npm使用语义化的版本号去管理版本和适用的版本范围。

如果在你当前目录存在package.json，并且运行npm install，那么npm将会寻找所有列举在文件中的所有依赖，然后下载合适的版本。

想要了解更多关于语义化版本，请查看xxx;
