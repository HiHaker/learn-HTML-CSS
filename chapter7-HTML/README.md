## HTML的其他的一些标签

### 表格

使用`<table></table>`标签来在html中使用表格，在`<table></table>`标签里写入`<tr></tr>`标签表示一行，在`<tr></tr>`标签里写入`<td></td>`标签表示一个单元格。如果要合并单元格，`colspan`表示横向合并，`rowspan`表示纵向合并。

#### 长表格

三个结构化标签，`thead tbody tfoot`，此外还有一个特殊的表示表头单元格的元素`th`，和`td`类似。

### 表单

表单在html中用于向服务器端提交数据，使用`form`标签来创建一个表单，`form`表单里面有一些表单项：文本框、密码框、提交按钮，单选框、多选框、下拉列表，如下：

```html
<form action="./target.html">
        文本框 <input type="text" name="text">
        <br>
        密码框 <input type="password" name="password">
        <br>
        提交按钮
        <input type="submit" name="submitbutton">
        <br>
        按钮 <input type="button" name="button" value="点击">
        <br>
        单选框
        <!-- 通过name值来对单选框进行分组，name值相同，分为一组 -->
        <!-- 设置value值来表示选中了哪个框 -->
        <input type="radio" name="box1" value="a">
        <input type="radio" name="box1" value="b" checked>
        <br>
        多选框
        <!-- 和单选框一样指定name和value -->
        <input type="checkbox" name="box2" value="a" checked>
        <input type="checkbox" name="box2" value="b">
        <input type="checkbox" name="box2" value="c">
        <br>
        下拉列表
        <select name="selectbox" id="sb">
            <option value="a">hello</option>
            <option value="b">你好</option>
        </select>
    </form><form action="">
        文本框 <input type="text" name="text">
        密码框 <input type="password" name="password">
        按钮 <input type="button" name="button" value="点击">
</form>
```

注意下面的对比：

```html
<form action="./target.html">
        <input type="text" name="text" value="在这填写一些东西">
        <br>
        <input type="submit" name="b1">
        <input type="reset" name="b2">
        <input type="button" name="b3" value="点击">
        <br>
        <!-- 带有结束标签，更加灵活 -->
        <button type="submit">提交</button>
        <button type="reset">重置</button>
        <button type="button">点击</button>
</form>
```

