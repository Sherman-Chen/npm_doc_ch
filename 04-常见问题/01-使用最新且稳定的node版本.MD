# 使用最新且稳定的node版本

node的0.4, 0.6, 0.10和iojs版本不再支持。

当你在使用不再被支持的node版本（比如0.4或者0.6）或者是不稳定的版本（比如奇数的版本，如0.7.x, 0.9.x, 0.11.x），那么你现在遇到的问题可能在最新和稳健的版本中已经被修复了。

## 查看你所使用的Node版本

使用下面的命令：

node -v

## linux系统中更新node

对于linux某些发行版（Debian/Ubuntu和RedHat/CentOS）来说，由发行版所提供的node版本可能落后于目前稳健的版本。这里有些来自NodeSource的指令可以用来获取最新版的node。

## windows系统中更新Node

从`https://nodejs.org/download`安装最新的MSI。

## 在OSX系统中更新node

从`https://nodejs.org/download`中安装最新的包，或者使用homebrew:

brew install node

## 一种更方便的方法去保持最新

因为node.js的开发者很活跃，因此nodejs有很多版本。一个好的实践去管理不同的版本，我们推荐你去使用版本管理器去安装nodejs。这里有很多很好的选择，他们分别是：

+ NVM
+ nodist
+ n
+ nave
+ nodebrew