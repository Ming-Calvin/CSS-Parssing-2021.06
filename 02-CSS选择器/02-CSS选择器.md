# 选择器

## 1.基础选择器

### 1.1 通用选择器（*）

```css
* {
  padding: 0;
  margin: 0;
}
```

### 1.2 元素(标签)选择器 （div, h1, p）

```html
 <h2> 标签 </h2>
```

```css
h2 {
  color: yellow;
}
```

### 1.3 id选择器（#myId）

```html
<div id="myId">id</div>
```

```css
#myId {
  width: 100px;
  height: 100px;
  background-color: pink;
}
```

### 1.4 类选择器（.myClassName）

```html
<div class="mingCalvin">类</div>
```

```css
.myClassName {
  height: 200px;
  width: 200px;
  background-color: red;
}
```

### 1.5 属性选择器

#### 1.5.1 匹配指定的属性名的所有元素	[attr]

```html
<h2 align="">这是有align属性且值为“ ”的</h2>
<h2>这是没有有align属性的</h2>
```

```css
[align] {
  color: red;
}
```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105145826.png" alt="image-20210105145825060" style="zoom: 50%;" />

#### 1.5.2 匹配属性等于指定的值所有元素	[attr=val]

```html
<h2 align="center">这是有align属性且值为“center”的</h2>
<h2 align=" ">这是有align属性且值为“ ”的</h2>
```

```css
[align=center] {
  color: red;
}
```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105150322.png" alt="image-20210105150321452" style="zoom: 50%;" />

#### 1.5.3 匹配属性以指定的属性值开头的所有元素	[attr^=val]

```html
<font color="#ff0000">这是有color属性且值为“#ff0000”的</font>
<br>
<font color="#aa0000">这是有color属性且值为“#aa0000”的</font>
```

```css
[color^="#f"] {
  background-color: aquamarine;
}
```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105151654.png" alt="image-20210105151653156" style="zoom:50%;" />

#### 1.5.4 匹配属性以指定的属性值结尾的所有元素	[attr$ =val]

```html
<font color="#ff00aa">这是有color属性且值为"#ff00aa"的</font>
<br>
<font color="#ff0000">这是有color属性且值为“#aa0000”的</font>
```

```css
[color$="aa"] {
  background-color: aquamarine;
}
```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105152127.png" alt="image-20210105152126440" style="zoom:50%;" />

#### 1.5.5 匹配属性中包含指定的属性值所有元素	[attr*=val]

```html
<font color="#ff00aa">这是有color属性且值为"#ff00aa"的</font>
<br>
<font color="#ff0000">这是有color属性且值为“#aa0000”的</font>
```

```css
[color*="aa"] {
  background-color: aquamarine;
}
```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105152426.png" alt="image-20210105152424500" style="zoom:50%;" />

#### 参考文档

[如何使用属性选择器](https://www.cnblogs.com/lq0001/p/11939317.html)



## 2. 组合器

### 2.1 后代选择器（h1 p）

后代选择器可以选择父元素里面子元素

```html
<ul>
  <li>List item 1
    <ol>
      <li>List item 1-1</li>
      <li>List item 1-2</li>
      <li>List item 1-3
        <ol>
          <li>List item 1-3-1</li>
          <li>List item <em>1-3-2</em></li>
          <li>List item 1-3-3</li>
        </ol>
      </li>
      <li>List item 1-4</li>
    </ol>
  </li>
  <li>List item 2</li>
  <li>List item 3</li>
</ul>
```

```css
ul em {
  color:red;
  font-weight:bold;
}
```

运行结果：

**无论选中元素到哪，只要是父元素的后代则就会被选中**

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105142915.png" alt="image-20210105142913191" style="zoom:50%;" />

### 2.5 直接子选择器（ul > li）

又称**相邻后代选择器**，子元素选择器只能选择作为某元素的最近一级子元素

```html
<h1>这是<strong>非常</strong><strong>非常</strong>重要的</h1>
<h1>这是<em>非常<strong>非常</strong></em>重要的</h1>
```

```css
h1 > strong {
  color: red;
}
```

运行结果：

**只能选中“儿子”，其他的“孙子”、“其他堂亲”都不行**

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105143445.png" alt="image-20210105143443818" style="zoom:50%;" />

### 2.6 相邻兄弟选择器（li+a）

两个标签相邻时，使用相邻兄弟选择器，可以对后一个标签进行样式修改（只能选中一个）

```html
<h2>1111</h2>
<h1>2222</h1>
<p>3333</p>
<p>4444</p>
<p>5555</p>
```

```css
h1 + p {
  color: skyblue;
}
```

运行结果：

**‘+’选择器则表示某元素后==相邻==的兄弟元素，也就是紧挨着的，是单个的**

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105144449.png" alt="image-20210105144447737" style="zoom: 67%;" />

### 2.7 一般兄弟选择器（li~a）

当两个标签不相邻时，要想修改后一个标签的样式，需要使用通用兄弟选择器

```html
<h2>1111</h2>
<h1>2222</h1>
<p>3333</p>
<p>4444</p>
<p>5555</p>
```

```css
h2 ~ p {
  color: red;
}
```

运行结果：

**‘~’选择器则表示某元素后所有同级的指定元素，强调所有的**

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105144735.png" alt="image-20210105144734421" style="zoom: 67%;" />



## 3. 伪类和伪元素

### 3.1 伪类选择器（a:hover, li:nth-child）

伪类：用于选择处于特定状态的元素

#### 3.1.1 链接伪类选择器

```html
<a href="#">链接</a>
```

```css
a:link {color:#FF0000;} /* 未访问的链接 */
a:visited {color:#00FF00;} /* 已访问的链接 */
a:hover {color:#FF00FF;} /* 鼠标划过链接 */
a:active {color:#0000FF;} /* 已选中的链接 */
```

#### 3.1.2 :first-child 伪类

 :first-child 伪类来选择父元素的第一个子元素

```html
<p>我是一个<strong>强壮的</strong>男人我是一个<strong>强壮的</strong>男人</p>
```

```css
p > strong:first-child {
  color: red;
}
```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210605182919.png" alt="image-20210105154108134" style="zoom: 80%;" />

#### 3.1.3  :focus伪类

:focus 伪类选择器用于选取获得焦点(光标)的表单元素

```html
<form>
  First name: <input type="text" name="fname" />
  <br>
  <input type="submit" value="提交">
</form>
```

```css
input:focus {
  background-color: yellow;
}
```

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105154341.png" alt="image-20210105154339732" style="zoom: 67%;" />

#### 3.1.4  :nth-child伪类

:nth-child(n) 选择器匹配属于其父元素的第 N 个子元素，不论元素的类型。

n 可以是数字、关键词或公式。

```html
<h1>这是标题</h1>
<p>第一个段落</p>
<p>第二个段落</p>
<p>第三个段落</p>
<p>第四个段落</p>
```

```css
p:nth-child(odd)
{
  background-color: #ff0000;
}
p:nth-child(even)
{
  background-color: #0000ff;
}
```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105163546.png" alt="image-20210105163545251" style="zoom: 50%;" />

### 3.2 伪元素选择器（::before, ::after）

伪元素：往标记文本中加入全新的HTML元素，而不是向现有的元素上应用类

```html
<div>
  <p>内容</p>
</div>
```

```css
div {
  height: 150px;
  width: 200px;
  background-color: grey;
  color: white;
}
```

- 标签::before{属性: 值;}。在标签之前添加子元素

  ```css
  div:before {
    content: '前面';
    height: 40px;
    width: 100px;
    background-color: antiquewhite;
    display: block;
    color: black;
  }css
  ```

- 标签::after{属性: 值;}。在标签之后添加子元素

  ```css
  div:after {
    margin-top: 10px;
    content: '后面';
    height: 40px;
    width: 100px;
    background-color: cornsilk;
    display: block;
    color: black;
  }
  ```

运行结果：

<img src="https://calvin-typora-image.oss-cn-hangzhou.aliyuncs.com/img/20210105155311.png" alt="image-20210105155310429" style="zoom: 67%;" />

## 4. 并集选择器

```css
/* 选择所有 <span> 和 <div> 元素 */
span, div {
  border: red 2px solid;
}
```



## Qusetion:

### Q1. `::before `和` :after `中双冒号和单冒号的区别？这2个伪元素的作用？

> : 表示伪类， :: 表示伪元素

想让插入的内容出现在其他内容前，使用::befroe。否则，使用::after