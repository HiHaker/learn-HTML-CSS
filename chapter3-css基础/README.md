## CSS基础

CSS是层叠样式表，用于负责网页的表现，负责元素的样式。

### CSS编写位置

#### 内联样式

在标签的内部通过style属性来设置元素的样式，这种方式没有将结构与表现分离，样式仅仅对一个标签生效，如果希望多个元素生效，必须在所有的标签中写一遍，开发时绝对不要使用内联样式。

```html
<p style="color: red; font-size: 30px;">今天天气真不错！</p>
```

#### 将样式编写到style标签里

将样式编写到html里的style标签中，通过CSS选择器来选中元素，并为其设置各种样式，这种方式也有缺点，只能对当前网页起作用，不能对其他页面起作用。

#### 外部样式表

将CSS样式文件写到外面，再通过link标签引入到网页中，是最佳实践。

```html
<link rel="stylesheet" href="./css/index3.css">
```

### CSS基本语法

CSS的基本语法包括**选择器**和**声明块**两个部分，选择器即为选择哪个元素来设定样式，声明块声明了样式的内容。

#### CSS选择器

##### 元素选择器

```html
<body>
    <h1>标题1</h1>
    <h1>标题2</h1>

    <p class="poem1" id="p1">落霞与孤鹜齐飞</p>
    <p class="poem1" id="p2">秋水共长天一色</p>
    <p class="poem2" id="p3">少小离家老大回</p>
    <p class="poem2" id="p4">乡音无改鬓毛衰</p>
    <p class="poem2" id="p5">儿童相见不相识</p>
    <p class="poem2" id="p6">笑问客从何处来</p>
</body>
```

通过元素来选择，一次性选中所有元素。

```css
h1{
    color: blue;
}
```

##### id选择器

通过元素的id来选择，选中对应id的元素，元素的id不能重复。

```css
#p3{
     color: red;
}
```

##### 类选择器

通过元素的类来选择，选中对应的类，元素可以有多个类，类可以重复。

```css
.poem1{
     color: green;
}
```

##### 通配选择器

选中整个页面中的所有元素。

```css
* {
    color: red;
}
```

##### 复合选择器

一般在使用选择器的时候，都会将选择器组合起来进行使用，称为复合选择器。

###### 交集选择器

比如说，想要选中class为mid的div元素，格式为：选择器1选择器2选择器3...选择器n{}。

```css
div.mid{
	color: red;
}
```

###### 选择器分组

我想同时选中p标签和span标签。

```css
p, span{
	color: violet;
}
```

##### 关系选择器

首先，元素与元素之间有如下的几种关系：

- 父与子的关系
- 祖先与后代的关系
- 兄弟关系

```html
<div>
        <p>
            div里的p元素
            <span>div里的p里的span元素</span>
        </p>
        <span>div里的span元素</span>
</div>
```

如上面的代码：div元素与p元素就是父子关系也是祖先关系，div和p里的span就只是祖先关系，不是父子关系，p元素和span元素就是兄弟关系。

###### 子元素选择器

```css
div > span{
	color: red;
}
/* 多层子元素 */
div > p > span{
	font-style: italic;
}
```

###### 后代元素选择器

```css
p ~ span{
	color: lightblue;
}
```

###### 兄弟元素选择器

```css
/*后面紧邻的兄弟元素*/
p + span{
	color: blue;
}
/*后面的所有兄弟元素*/
p ~ span{
	color: lightblue;
}      
```

##### 属性选择器

属性选择器可以让我们根据标签的属性来选择元素：

```css
/* 第一种用法：[属性名] */
p[title]{
	color: orange;
}

/* 第二种用法：[属性名]=属性值 */
p[title="abc"]{
	font-size: 20px;
}

/* 第二种用法扩展：[属性名]^=属性值(以属性值开头) */
p[title^="abc"]{
	color: purple;
}

/* 第二种用法扩展：[属性名]$=属性值(以属性值结尾) */
p[title$="o"]{
	font-size: 20px;
}

/* 第二种用法扩展：[属性名]*=属性值(以属性值结尾) */
p[title*="e"]{
	color: green;
}
```

##### 伪类选择器

什么是伪类呢？伪类从字面意思上去理解，伪类就是一个不存在的类，一个特殊的类，表示标签的特殊状态，比如：第一个子元素、被点击的元素，、鼠标移入的元素，伪类一般情况下使用`:`开头。

```css
/* 伪类选择器 */
/* :first-child子元素的第一个 */
ul > li:first-child{
	font-size: 20px;
}

/* :first-of-type指定元素的第一个 */
ul > li:first-of-type{
	color: red;
}

/* :last-child */
ul > li:last-child{
	color: blue;
}

/* :last-of-type */
ul > li:last-of-type{
	font-size: 20px;
}

/* :nth-child() */
ul > li:nth-child(2n){
	color: orange;
}
```

附html代码：

```html
<body>
    <ul>
        <span>这是span</span>
        <li>第一</li>
        <li>第二</li>
        <li>第三</li>
        <li>第四</li>
        <li>第五</li>
    </ul>
</body>
```

###### 超链接的伪类

超链接也有一些特殊的状态：是否被访问过、是否被点击中，所以也有如下的一些伪类：

```css
<style>
	/* 正常的链接 */
	a:link{
		color: green;
	}

	/* 访问过的链接(因为隐私的原因，这里样式只能更改颜色) */
	a:visited{
		color: orange;
	}

	/* 鼠标移动到 */
	a:hover{
		color: red;
	}

	/* 鼠标点击 */
	a:active{
		font-size: 20px;
	}
</style>
```

##### 伪元素选择器

表示页面中一些不存在的元素，用于表示特殊的位置。

