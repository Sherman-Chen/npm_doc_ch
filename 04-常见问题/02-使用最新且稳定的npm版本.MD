# 使用最新且稳定的npm版本

## 查看你运行的npm是什么版本

使用下面的命令：

npm -v

## 在类UNIX系统中更新

（在linux或者OS系统中，如果你使用缺省方式安装的话，你可能需要使用sudo前缀）

你可以使用下面的命令更新到最新版本：

npm install -g npm@latest

或者是使用下面命令来更新下个发行版的npm：

npm install -g npm@next

## 在windows中更新

微软写了一个小的命令行工具去自动化下面的步骤。你可以在这里下载到，或者是跟着下面的步骤做。

---

默认情况下，npm是捆绑在node中的，它的安装位置通常是在C:\Program Files (x86)\nodejs。npm的全局安装包则是独自安装在用户指定的路径中（`C:\Users\<username>\AppData\Roaming\npm`）；因为安装器将路径(PATH)中C:\Program Files (x86)\nodejs放在了C:\Users\<username>\AppData\Roaming\npm的前面，因此会造成即使你使用了npm -g install npm@<version>安装另外一个版本的npm，它也会使用node捆绑的npm。为了绕过node中的Npm，你可以使用下面的方法：

+ 选项一：编辑你的windows安装器的PATH，将%appdata%\npm放到%ProgramFiles%\nodejs的前面。需要注意的是，当你改变了PATH或者是重新安装了npm，你需要将cmd.exe重启(或许还需要重启系统)。

+ 选项二：将下面两个都移除掉
    + %ProgramFiles%\nodejs\npm
    + %ProgramFiles%\nodejs\npm.cmd

+ 选项三：移动到%ProgramFiles%\nodejs\node_modules\npm，将npmrc复制到其他目录或者死桌面。然后打开cmd.exe，运行下面的命令：

```
cd %ProgramFiles%\nodejs
npm install npm@latest
```

如果你安装npm是通过安装node的这种方式，在做完上面的步骤之后，还需要做下面几个步骤：

+ 选项一或者二：
    + 到%ProgramFiles%\nodejs\node_modules\npm目录下，到%appdata%\npm\node_modules\npm复制npmrc过来。这个将会通知新的npm：全局安装包的位置在哪里。

+ 选项三：
    + 将npmrc文件复制会%ProgramFiles%\nodejs\node_modules\npm。

（如果你使用的是WIN7，并且没有%appdata%\npm目录，请接着看下面）。

## 

