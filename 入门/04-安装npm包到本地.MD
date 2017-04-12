# 本地安装npm包

有两种方式用来安装npm包：本地和全局。适用哪种方式来安装，取决于我们如何适用这个包。

如果你自己的模块依赖于某些包（比如node.js中使用require来引用），那么你应该选择本地安装，这种方式也是npm install的默认行为。或者你想将包作为一种命令行公交，比如grunt CLI，那么你应该选择全局安装。

想要了解更多关于install命令行的行为，可以查看CLI的文档。

## 安装

可以使用下面的命令来下载一个包：

`npm install <包名>`

使用之后将会在当前的目录下创建一个node_modules的目录，和将下载的包保存到这个目录下。

### 测试

想要确定npm install是否正常工作，可以检查node_modules目录是否存在，并且里面是否含有你安装的包的文件夹。在Unix系统，你可以使用ls node_modules来查看。在Windows则可以使用dir node_modules来查看。

### 示例

安装一个lodash的包。安装成功之后，如果node_modules目录下存在一个名为lodash的文件夹，则说明成功安装了这个包。

```
npm install lodash
ls node_modules   #在window中则是使用dir node_modules

#=> lodash
```

## 哪个版本的包会被安装？

在本地目录中如果没有package.json这个文件的话，那么最新版本的包会被安装。

如果存在package.json文件，则在这个文件中关于这个包约定的版本规则的最新版本会被安装。

## 使用已安装的包

一旦包存在unode_modules中，我们就可以使用它。比如在你所创建的node.js模块中，你可以require这个包。

### 示例

创建一个文件，名为index.js，代码如下：

```
// index.js 
var lodash = require('lodash');
 
var output = lodash.without([1, 2, 3], 1);
console.log(output);
```

运行node index.js，它将会输出[2,3]。

如果你没能正确安装lodash，你将会得到下面的错误信息：
```
module.js:340
    throw err;
          ^
Error: Cannot find module 'lodash'
```

可以在index.js所在的目录中使用npm install lodash来修复这个问题。