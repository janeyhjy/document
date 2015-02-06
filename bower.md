#Bower学习笔记
##概念:
Bower是一个客户端技术的软件包管理器，它可用于搜索、安装和卸载如JavaScript、HTML、CSS之类的网络资源。其他一些建立在Bower基础之上的开发工具，如YeoMan和Grunt，这个会在以后的文章中介绍。
##前提准备
+ 安装Node
+ 安装Git
##安装
+ 命令安装全局Bower： `npm install -g bower`
##使用
+ 在项目根目录中创建`.bowerrc`文件
```
{
    "directory": "安装插件的目录"
}
```
+ 包的安装
    * 例(安装JQuery)： `bower install jquery`
    * 执行完`bower install jquery`后会产生一个bower_components文件夹
    * 可用`tree bower_components`查看文件夹目录
+ 包的搜索
    * 若想用框架但又不确定包的名字，可以使用search命令：`bower search bootstrap`
+ 包的信息
    * `bower info bootstrap`查看包的所有信息
+ 包的卸载
    * 卸载包可以使用uninstall命令：`bower uninstall jquery`
+ bower.json文件的使用
    * 可以使用`bower init`来形成`bower.json`文件