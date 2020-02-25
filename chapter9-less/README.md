## less

### 简介

less是css的一门预处理语言，通过less可以编写更少的代码实现更强大的样式，在less中添加了许多的新特性，如对变量的支持，对mixin的支持，less的语法大致和css的语法一致，但是增加了许多对css的扩展。

```less
// 单行注释
// 更加结构化的后代选择器写法
.box{
    color: red;
    .box2{
        color: black;
        .box3{
            color: orange;
        }
    }
}

// 变量的支持
@a: 100px;

// 使用变量时，如果是直接使用，使用@变量名即可
.box4{
    width: @a;
}

// 如果是作为类名使用或部分值使用需要使用@{变量名}的方式
@path: '../image';
.box5{
    background-image: url('@{path}');
}

// $符号，可以引用已经指定值的对应的属性的值
.box6{
    color: red;
    background-color: $color;
}

// &符号，代表父元素
.box7{
    width: 100px;
    height: $width;

    &:hover{
        width: 200px;
        height: $width;
    }
}

// :extend()，对当前选择器扩展指定选择器的样式
.p1{
    width: 100px;
    height: 100px;
}
.p2:extend(.p1){
    color: red;
}

// mixin混合函数
.p3(){
    width: 100px;
    height: 100px;
}
.p4{
    .p3();
    color: blue;
}

// 混合函数可以用于传入变量：主要用法
.p3(@w, @h, @c){
    width: @w;
    height: @h;
    color: @c;
}
.p4{
    .p3(100px, 100px, #bfa);
}

// 可以通过import将其他的less文件引入到当前的文件中
@import "other.less";


```

