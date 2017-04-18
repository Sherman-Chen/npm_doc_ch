# 发布npm包

你可以发布任何带有package.json文件的目录。比如一个node模块。

## 创建一个用户

在发布之前，你应该拥有一个npm registry的账号。如果没有的话，使用npm adduser创建一个。创建好了之后，使用npm login登录并且将登录信息保存到你的客户端中。

测试：使用npm config lsto确保你的登录信息已经保存到你的客户端中。并且检查你的账号已经添加到[registry]( https://npmjs.com/~)中。

## 发布一个包

使用npm publis来发布一个包。

注意：文件夹中的所有内容都会被发布，除了在.gitignore或者是.npmignore文件中指明的文件。这两个文件的介绍可以查看xxx。

并且还需要确保你的包名在registry中没有跟其他人的包名有冲突。

测试：去https://npmjs.com/package/<package>这个页面中，将会看到你发布的包的信息。

## 更新包

当你更新了你的包之后，你应该使用npm version <update_type>来更新你的包。update_type是一种包版本的语义化规则。上面那个命令会更新package.json中的包信息。需要注意的是，如果你的包有使用git管理的话，这个操作会增加一个tag到你的git仓库中，tag名为更新的版本号。

更新完之后，你就需要再次使用npm publish来发布你的包了。

测试：到https://npmjs.com/package/<package>中查看你的包是否有更新了。

README文件只有当你的包有新版本发布的时候才会被更新。因此你如果只是修改README的话，则应该使用npm version patch和npm publis配合使用来修复。