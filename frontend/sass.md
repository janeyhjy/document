#sass安装
+ 是ruby写的，需要安装`ruby`
    * 安装ruby: `sudo apt-get install ruby`
    * 安装sass: `gem install sass`
## sass的使用
* 变量:以`$`开头

```
$blue: #1875e7;
div {
    color: $blue;
}
```
* 若变量需要镶嵌在字符串中，需要写在`#{}`中

    ```
    $side: left;
    .rounded {
        border-#{$side}-radius: 5px;
    ```

* 计算功能
```
body {
    margin: (10px/2);
    top: 1px + 3px;
    right: $var * 10%;
}
```
* 嵌套
```
div {
    //元素嵌套
    h1 { 
        color: red;
    }
    //属性嵌套
    border {
        color: red;
    }
}
```
* 注释
    * `/* comment */`会保留到编译后的文件
    * `// comment`只保留在SASS源文件中，编译后被省略
    * `/*! comment */`表示重要注释，即使压缩也会保留
* 继承
```
.class1 {
    border: 1px solid $ccc;
}
.class2 {
    //@extends命令继承
    @extend .class1
    font-size: 120%;
}
```
* Mixin: `@mixin`定义可以重用的代码块
```
@mixin left {
    float: left;
    margin-left: 10px;
}
div {
    //@include命令调用mixin代码块
    @include left;
}
```
* mixin指定参数和缺省值
```
@mixin left($value: 10px) {
    float: left;
    margin-left: $value;
}
div {
    @include left(20px);
}
```
* 插入文件
```
@import "path/filename.scss";
```
* 条件语句
```
//@if
p {
    @if 1+1==2 {border: 1px solid;}
    @if 1+1 > 3 {border: 2px dotted;}
}
//@else
@if lightness($color) > 30% {
    background-color: #000;
} @else {
    background-color: #fff;
}
```
* 循环语句
```
//@for
@for $i from 1 to 10 {
    .border-#{$i} {
        border: #{$i}px solid blue;
    }
}
//while
$i:6;
@while $i>0 {
    .item-#{$i} {width: 2em*$i;}
    $i: $i - 2;
}
//@each
@each $m in a,b,c,d {
    .#{$m} {
        background-image: url(imageurl);
    }
}
```
* 自定义函数
```
@function double($n) {
    @return $n*2;
}
#sidebar {
    width: double(5px);
}
```
