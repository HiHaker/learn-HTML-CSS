## html基础

### 一个完整的网页

#### 文档声明

```html
<!DOCTYPE html>
```

#### 标签（元素）

##### 根标签-html

```html
<html>
	
</html>
```

##### head标签

head标签是网页的头部，主要帮助浏览器来解析网页，内有meta、title等标签或称元素。

```html
<head>
        <!-- head标签是网页的头部，主要帮助浏览器来解析网页 -->
        <!-- meta标签用于记录网页的元数据 -->
        <!-- 如1：指定字符集 -->
        <meta charset="UTF-8">
        <!-- title网页的标题 -->
        <title>完整的一个网页</title>

</head>
```

##### body标签

body是html的子元素，网页的可见内容应该写在body里。

```html
<body>
        
</body>
```

------

#### 实体

在有的时候，我们会需要输入一些特殊字符，比如说小于号`<`，大于号`>`，多个连续的空格，而直接输入它们的话会被浏览器解析为其他样子，就`<`号来说，它是html中标签的左括号。

在html中，有专门表示这些符号的内容，叫做 **实体**。语法为`&实体名;`，空格就是`&nbsp;`，小于号(greater than)`&gt;`。

#### meta标签

meta标签是表示网页的一些元数据，是单标签，具体例子如下：

```html
<meta charset="UTF-8">
<meta name="keywords" content="html,css,meta">
<meta name="description" content="学习meta标签">
```

#### 语义化标签的概念

> 在网页中，HTML是专门负责网页结构的，所以我们在使用HTML标签时，应该关注的是标签的语义，而不是它的样式。

#### 一些标签的介绍

##### 标题标签

h1~h6共有6级标题，重要性依次递减。h1在网页中的重要性仅次于title标签，一般情况下，一个页面中只会有一个h1。标题标签都是块元素（在页面中独占一行的元素称为块元素，反之称为行内元素）。

##### 块元素

在网页中会通过块元素来进行对网页界面的布局，行内元素用来包裹文字，一般情况下会在块元素中放行内元素，不在行内元素中放块元素。块元素中什么都能放，<u>p标签中不能出现块元素。</u>

##### hgroup标签

用于为标题分组。

```html
    <hgroup>
        <h1>h1</h1>
        <h2>h2</h2>
    </hgroup>
```

##### p标签

p标签表示一个段落，p标签也是一个块元素。

##### em标签

em标签用于表示语音、语调的加重，是一个典型的行内元素。

```html
<p>这是一段，p标签是<em>块</em>元素</p>
```

##### strong标签

strong标签也是一个行内元素，表示对内容的强调。

```html
<strong>strong</strong>标签
```

##### blockquote标签

表示长引用。

```html
<blockquote>这不是我说的</blockquote>
```

##### q标签

表示短引用。

```html
<q>这也不是我说的</q>
```

##### br标签

表示换行。

------

#### H5新增的一些标签和div标签与span标签

新增了如下的一些标签，但主要还是使用div和span标签来开发。

```html
<header></header>
<main></main>
<footer></footer>
<nav></nav>
<section></section>

<div>
        <span></span>
</div>
```

#### 列表标签

ul无序列表（使用最多），ol有序列表（使用最少），dl定义列表,列表之间可以互相嵌套。

```html
<ul>
    <li>香蕉</li>
    <li>苹果</li>
    <li>梨</li>
</ul>

<ol>
    <li>第一</li>
    <li>第二</li>
</ol>

<dl>
    <dt>结构</dt>
    <dd>hello</dd>
</dl>
```

#### 超链接标签

a标签，可以链接到外部地址或内部地址。

通过给页面内的元素指定元素唯一的id也可以超链接到指定的元素位置，去顶部，去底部等等。

```html
<a href="#bottom">去底部</a>
<a href="#p3">去p3</a>
```

#### 图片标签

使用img标签来引入外部图片，img标签是一个自结束标签，属于替换元素，介于块元素和行内元素之间。

img标签有一些属性：`src`图片的地址 `alt`图片的描述 `width`宽 `height`高，在PC端一般不去修改图片的宽度和高度，移动端会去。

```html
<img src="../images/pic1.png" alt="Van Gogh">
```

#### 内联框架

和img很像的一个标签-iframe标签，用于向网页中引入其他的网页。

```html
<iframe src="https://www.baidu.com" frameborder="0"></iframe>
```

#### 音频标签audio

属性有`src`文件地址 `controls`是否显示控制条。

```html
<audio src="xxx.mp3" controls></audio>
<audio controls>
    <source src="xxx.mp3">
</audio>
```

#### 视频标签

使用video视频标签来向网页中引入一个视频，用法和audio标签类似。