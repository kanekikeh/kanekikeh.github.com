#### Learning Record

一些关于初次学习Web的记录。

# HTML

简介：HTML是超文本标记语言（HyperText Markup Language）的缩写。HTML 是构成 Web 世界的一砖一瓦。它定义了网页内容的含义和结构。HTML 不是一门编程语言，而是一种用于定义内容结构的标记语言。

#### HTML 文档结构
```markdown
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
  <title>【网页标题】</title>
</head>
<body>
  <h1>【页面内容题目】</h1>
  <p>【文本内容】</p>
</body>
</html>
```
##### 结构解析
1\.`<!DOCTYPE html>`:声明文档类型。（可有可无）  
2\.`<html></html>`:包含整个完整的页面。（根元素，其他元素都嵌套在其中。）  
3\.`<head></head>`:包含所有想包含在HTML页面中但不想在HTML页面中显示的内容。（包括想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。）  
4\.`<meta charset="utf-8">`:设置文档使用utf-8字符集编码。（utf-8字符集包含了人类大部分的文字。）  
5\.`<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`:指定页面的图标。（出现在浏览器标签上。）  
6\.`<title></title>`:设置页面标题。（出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面。）  
7\.`<body></body>`:包含页面所有内容，如文本，图片，音频，游戏等等。  

#### 元素
```markdown
<开始标签>内容</结束标签>
```
以上结构便是完整元素，整个HTML就由一个个元素组成（可以嵌套），而元素则一般由一对标签（tag）构成。
##### 标题
HTML提供了从小到大六级标题，分别是`<h1>`~`<h6>`。 
标题的作用:   
1\.搜索引擎用标题来索引页面的内容。  
2\.用户也习惯以标题进行主要内容浏览，以决定是否查看该页面。  
使用方法如下：  
```markdown
<h1>head</h1>
<p>text</p>
<hr>
```
#### 超链接
```markdown
<a href="https://www.baidu.com/" target="_blank">百度一下</a>
```
说明：
1\.`href`即为要跳转去的地址 URL（Uniform Resorce Locator)  
2\.`target`属性为_blank表示在新的页面打开超链接（默认是在当前页面打开即_self）  
3\.超链接标签包含的内容（当前为文字"百度一下"）即为显示在页面上供用户点击的  

#### 锚点
锚点，也称为书签，用于标记页面的某个元素或位置。通过锚点，我们可以轻易的在长页面内实现跳转。  
先使用id属性生成某元素的锚点，然后再使用超链接指向该锚点即可。  
```markdown
<!-- 文档其余部分 -->
<h2 id="C4">第四章</h2>
<!-- 文档其余部分 -->
<a href="#C4">跳到第四章</a>
<!-- 文档其余部分 -->
...
```
注意：  
1\.元素的id值必须是唯一的，也即页面不能再有其它元素的id值为C4。  
2\.超链接中的地址需要有#符号。  

#### 图片
在html中插图片如下：
```markdown
<img src="https://mdbootstrap.com/img/logo/mdb192x192.jpg" alt="MDB Logo" width="200" height="200">
```
说明：  
1\.`src`属性为要显示图片文件的位置 URL，即图片文件的路径。  
2\.`alt`属性当获取图片出现问题时显示的文字（占位符）。  
3\.可为图片指定高宽度，但不建议（可能导致图片变形）。  

#### 文件路径
为获取图片文件，我们需要指定该文件位于何处，这称为文件路径。文件路径有相对路径和绝对路径两种。
上面图片的例子即为绝对路径。下面是相对路径的例子：

| 例子 | 解释 |
| -----|:----:| 
| `<img src="picture.jpg">` | 该图片文件与当前文档在同一目录中 | 
| `<img src="./images/picture.jpg">` | 该图片文件在当前目录下的images目录中 | 
| `<img src="../picture.jpg">` | 该图片文件在上一级目录中 |

#### 表格
使用格式如下：  
```markdown
  <table>
    <tr>
      <th>Firstname</th>
      <th>Lastname</th>
      <th>Age</th>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Smith</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Eve</td>
      <td>Jackson</td>
      <td>94</td>
    </tr>
  </table>
```
其中`<tr>`表示行, `<td>`表示行中的单元, `<th>`是表头的单元。

##### 无序列表
无序列表使用`<ul>`标签，默认使用实心圆点作为每项的标志，其它的标志可以是空心圆circle，实心方块square以及不出现标志。
```markdown
<ul>
<!--<ul type="square">-->
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```
##### 有序列表
有序列表使用`<ol>`标签，默认使用数字作为每项的标志，其它的标志可以是大写字母A，小写字母a，罗马字母i等。
```markdown
<ol>
<!--<ol type="a">-->
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```
#### 表单
当网站需要获取我们的一些信息如：用户名、密码、选择买什么、买多少、提出意见等等时，我们就需要使用表单（form）来让用户填写或选择。
```markdown
<form>
  <!-- 文本框，注意有 placeholder 提示符 -->
  用户名：<br>
  <input type="text" name="name" placeholder="请输入用户名"><br>
  <!-- 密码框 -->
  密码：<br>
  <input type="password" name="ps" placeholder="请输入密码"><br>
  年龄：<br>
  <!-- 数字输入框，注意 min 和 value 属性-->
  <input type="number" name="age" min="18" value="18"><br>
  <!-- 单选按钮, 注意 checked 属性 -->
  性别：<br>
  <input type="radio" name="gender" value="male" checked> 男<br>
  <input type="radio" name="gender" value="female"> 女<br>
  <input type="radio" name="gender" value="other"> 其它<br>
  <!-- 下拉列表，注意 selected 属性 -->
  党派：<br>
  <select name="party">
    <option value="D">民主党</option>
    <option value="R" selected>共和党</option>
    <option value="N">无党派</option>
  </select><br>
  <!-- 多选框 -->
  您有哪些交通工具：<br>
  <input type="checkbox" name="vehicle1" value="Bike"> 自行车<br>
  <input type="checkbox" name="vehicle2" value="Motocycle" checked> 摩托车<br>
  <input type="checkbox" name="vehicle3" value="Car"> 轿车<br>
  <input type="checkbox" name="vehicle4" value="Jet"> 飞机<br>
  <!-- 日期选择器 -->
  您的工作日期：<br>
  <input type="date"><br>
  <!-- 文件选择器 -->
  上传您的照片:<br>
  <input type="file" name="photo"><br>
  <!-- 文本输入区域，注意 rows 和 cols 属性 -->
  您的建议：<br>
  <textarea name="message" rows="5" cols="30">
    The cat was playing in the garden.
  </textarea><br><hr>
  <!-- 表单提交/重置按钮，将表单中的数据取消或传输给服务器端进行处理 -->
  <input type="submit" value="提 交">
  <input type="reset" value="重 置">
</form>
```

#### 特殊元素
##### 注释
注释格式`<!--内容-->`,使用方式如下
```markdown
<p>可以显示</p>
<!-- <p>不可显示</p> -->
```

##### 空元素
一般元素包括开始标签，内容，结束标签。但有一些特殊元素只有一个开始标签，通常用来在此元素所在位置插入/嵌入一些东西，如`<br>`, `<hr>`, `<input>`, `<img>`, `<a>`等等。我们称其为空元素。  
```markdown
<!-- 换行 -->
<p>我可以<br>换行</p> 
<!-- 水平分割线 -->
<hr>
<!-- 输入框 -->
<input>
```
#### 元素的属性
元素是可以有相关属性的。属性包含元素的额外信息，这些信息不会在浏览器中显示出来。
```markdown
<!-- 带属性的段落输入框 -->
<p title="这是个title属性">鼠标移上来试试！</p>
<!-- 带属性的输入框 -->
<input type="text">
<input type="password">
```
一个属性必须包含以下内容：  
1\.一个空格，在属性和元素名称之间。(如果已经有一个或多个属性，就与前一个属性之间有一个空格。)  
2\.属性名称，后面跟着一个 = 号。  
3\.一个属性值，由一对引号 "" 引起来。  

#### 元素显示的方式
HTML 的元素可以以称为区块 或 内联的方式进行显示。
##### 区块元素
区块元素在浏览器显示时，通常会以新行来开始（和结束）。如：`<h1>`, `<pre>`, `<ul>`, `<table>`，`<div>` 等。
```markdown
<h2>区块元素</h2>
<div>Hello</div>
<div>World</div>
<p>单独一行</p>
```
##### 内联元素
内联元素相反，他们总是一个接一个进行显示，不会新起一行。如： `<span>`, `<input>`, `<td>`, `<a>`, `<img>`等。
```markdown
<h3>下面的元素将在一行中显示</h3>
<span>姓名：</span>
<input name="username">
<span>哈哈哈</span>
<a href="https://google.com/">Google</a>
<img src="https://mdbootstrap.com/img/logo/mdb192x192.jpg">
```

#### 预设格式
如果你想在网页中展示一首诗或一些特别格式的文本，那么请使用`pre`标签。
```markdown
<pre>
涉江采芙蓉，兰泽多芳草。
采之欲遗谁，所思在远道。
还顾望旧乡，长路漫浩浩。
同心而离居，忧伤以终老。
</pre>
```
#### 特殊字符
在 HTML 中，某些字符是预留的。
在 HTML 中不能使用小于号（<）和大于号（>），这是因为浏览器会误认为它们是标签。
如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用字符实体（character entities）。  
特殊字符可参考<https://www.runoob.com/tags/ref-entities.html>


# CSS
简介：CSS是级联样式表（Cascading Style Sheets）的缩写。HTML 用于撰写页面的内容，而 CSS 将决定这些内容该如何在屏幕上呈现。如果说HTML是一砖一瓦，那么css就是房屋的修饰如油漆、墙纸等。

#### 语法
一条CSS样式规则由两个主要的部分构成：选择器，以{}包裹的一条或多条声明:
```markdown
选择器 {属性:值;属性:值;……}
```
说明：  
1\.选择器是您需要改变样式的对象（上图的规则就一级标题生效）。  
2\.每条声明由一个属性和一个值组成。（无论是一条或多条声明，都需要用`{}`包裹，且声明用`;`分割）。
3\.属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。  

#### 选择器
一个页面上的元素众多，选择器就用于在页面中找到/选择需要应用这个样式的对象。
除我们前示的元素选择器外，还有`id`和`class`选择器。其中`class`选择器使用非常普遍。  
##### id选择器
```markdown
/* 注意：id选择器前有 # 号。 */
#sky{
  color: blue;
}
```
这条规则表明，找到页面上id为sky的那个元素让它呈现蓝色，如下所示的页面，蓝色的天空这几个字就将会是蓝色的。
```markdown
<p id="sky">蓝色的天空</p>
<p id="forest">绿色的森林</p>
```
注意：id 选择器适用范围只有一个元素。

##### class选择器
```markdown
/* 注意：class选择器前有 . 号。 */
.center{
  text-align: center;
}
.large{
  font-size: 30px;
}
.red{
  color: red;
}
```
以上代码定义了三条规则，分别应用于页面上对应的元素，如只要页面上某元素的class为red，那么就让它呈现红色。
```markdown
<p class="center">我会居中显示的</p>
<p class="red">我是红色的</p>
<p class="center large red">我又红又大还居中</p>
<p class="red">我也可以是红的</p>
```
注意：元素的class值可以多个，也可以重复。

#### 生效方式
##### 外部样式表
新建一个 HTML文件（后缀为.html)。  
在同一目录新建一个样式表文件mycss.css（注意后缀名为css）。  
注意：  
 一般我们会在项目目录下建一个文件夹如css专门存放样式表文件，如此我们引入样式文件时路径就变为 ./css/mycss.css之类的。

##### 内部样式表
样式放在 HTML 文件中，这称为内部样式表。
在`<head>`元素中引入了`<style>`标签，放入了样式。
```markdown
<head>
  <meta charset="utf-8">
  <!-- 注意下面这个语句，将导入外部的 mycss.css 样式表文件 -->
  <link rel="stylesheet" type="text/css" href="mycss.css">
  <title>页面标题</title>
  <style>
    body {
      background-color: linen;
      text-align: center;
    }
  </style>
</head>
```
提示：只有页面的样式规则较少时可采用这种方式。

##### 内联样式
直接把样式规则直接写到要应用的元素中，如下：
```markdown
<h3 style="color:green;">I am a heading</h3>
```
提示：内联样式是最不灵活的一种方式，完全将内容和样式合在一起，实际应用中非常少见。

##### 级联的优先级
从高到低分别为：  
1\.内联样式  
2\.内部样式表或外部样式表  
3\.浏览器缺省样式  
提示：哪个样式定义离元素的距离近，哪个就生效。


#### 基础
##### 颜色
颜色在网页中的重要性不言而喻。
我们可以采用颜色名称也可以使用颜色RGB16进制值，来设定前景或背景的颜色。如：
```markdown
<!--颜色名称-->
<h3 style="background-color:Tomato;">Tomato</h3>
<!--颜色值，3个字节分别代表RGB（Red，Green，Blue）的0～255的值-->
<h3 style="background-color:#ff0000;">#ff0000</h3>
<!--文本颜色-->
<h3 style="color:Tomato;">Hello World</h3>
```
注意：为演示方便，我们的样式采用了内联方式，实际中不能这样做！如果需要好的配色方案可去<https://colordrop.io/>或<https://www.webdesignrankings.com/resources/lolcolors/>挑选。

##### 尺寸
我们可以用 `height` 和 `width` 设定元素内容占据的尺寸。常见的尺寸单位有：像数 `px`，百分比 `%`等。  
新建如下 HTML 文件：
```markdown
<html>
  <head>
    <link rel="stylesheet" href="./mycss.css">
  </head>
  <body>
    <div class="example-1">
      这个元素高 200 pixels，占据全部宽度
    </div>
  </body>
</html>
```
再建对应的 CSS 文件如下：
```markdown
.example-1 {
  width: 100%;
  height: 200px;
  background-color: powderblue;
  text-align: center;
}
```
##### 对齐
对于元素中的文本，我们可以简单的设置`text-align`属性为`left`, `center`, `right`即可（显然缺省的是左对齐），上例中已有相关的应用。
#### 盒子模型
盒子模型指的是一个 HTML 元素可以看作一个盒子。从内到外，这个盒子是由`内容 (content)`, `内边距 (padding)`, `边框 (border)`, `外边距 (margin)`构成的。  
说明：  
1\.Content 盒子的内容，如文本、图片等  
2\.Padding 填充，也叫内边距，即内容和边框之间的区域  
3\.Border 边框，默认不显示  
4\.Margin 外边距，边框以外与其它元素的区域  
使用：  
新建HTML文件： 
```markdown
<html>
  <head>
    <link rel="stylesheet" href="./mycss.css">
  </head>
  <body>
    <div class="box1">我是内容，外面红色的是我的边框。注意边框的内外都有25px的距离。</div>
  </body>
</html>
```
再建对应的css文件如下：  
```markdown
.box1 {
  height: 200px;
  width: 200px;
  background-color:#615200;
  color: aliceblue;
  border: 10px solid red;
  padding: 25px;
  margin: 25px;
}
```
#### 边框与边距
无论边框、内边距还是外边距，它们都有上下左右四个方向。
##### 边框
```markdown
<p class="example-1">I have black borders on all sides.</p>
<p class="example-2">I have a blue bottom border.</p>
<p class="example-3">I have rounded grey borders.</p>
<p class="example-4">I have a purple left border.</p>
```
```markdown
.example-1 {
  border: 1px dotted black; /* 上下左右都相同 */
}
.example-2 {
  border-bottom: 1px solid blue; /* 只设置底部边框 */
}
.example-3 {
  border: 1px solid grey;
  border-radius: 15px; /* 边框圆角 */
}
.example-4 {
  border-left: 5px solid purple;
}
```
##### 边距
内边距设置：
```markdown
padding: 20px; /* 上下左右都相同 */
padding-top: 20px;
padding-bottom: 100px;
padding-right: 50px;
padding-left: 80px;
padding: 25px 50px 75px 100px; /* 简写形式，按上，右，下，左顺序设置 */
padding: 25px 10px; /* 简写形式，上下为25px，左右为10px */
```
#### 定位
`position`属性用于对元素进行定位。该属性有以下一些值：  
\*static 静态  
\*relative 相对  
\*fixed 固定  
\*absolute 绝对  
设置了元素的`position`属性后，我们才能使用`top`, `bottom`, `left`, `right`属性，否则定位无效。
##### static
设置为静态定位`position: static`;，这是元素的默认定位方式，也即你设置与否，元素都将按正常的页面布局进行。  
即：按照元素在 HTML出现的先后顺序从上到下，从左到右进行元素的安排。  
##### relarive
设置为相对定位`position: relative;`，这将把元素相对于他的静态（正常）位置进行偏移。  
试试如下的代码：
```markdown
<!-- HTML -->
<div class="example-relative">内容</div>
<!-- CSS -->
.example-relative {
  position: relative;
  left: 60px;
  top: 40px;
  background-color: rgb(173, 241, 241);
}
```
##### fixed
设置为固定定位`position: fixed;`，这将使得元素固定不动（即使你上下左右拖动浏览器的滚动条）。  
此时元素固定的位置仍由`top`, `bottom`, `left`, `right`属性确定，但相对的是视口（viewport，就是浏览器的屏幕可见区域）。  

##### absolute
设置为绝对定位`position: absolute;`，将使元素相对于其最近设置了定位属性（非static）的父元素进行偏移。  
如果该元素的所有父元素都没有设置定位属性，那么就相对于`<body>`这个父元素。  

#### 溢出
当元素内容超过其指定的区域时，我们通过溢出`overflow`属性来处理这些溢出的部分。  
溢出属性有一下几个值：
\*visible 默认值，溢出部分不被裁剪，在区域外面显示
\*hidden 裁剪溢出部分且不可见
\*scroll 裁剪溢出部分，但提供上下和左右滚动条供显示
\*auto 裁剪溢出部分，视情况提供滚动条
使用方法：  
```markdown
<!-- HTML -->
<div class="example-overflow-scroll-y">You can use the overflow property when you want to have better control of the
    layout. The overflow property specifies what happens if content overflows an element's box.
</div>
<!-- CSS -->
.example-overflow-scroll-y {
  width: 200px;
  height: 100px;
  background-color: #eee;
  overflow-y: scroll;
}
```

#### 浮动
在一个区域或容器内，我们可以设置`float`属性让某元素水平方向上向左或右进行移动，其周围的元素也会重新排列。  
一个浮动元素会尽量向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。浮动元素之后的元素将围绕它。  
一个元素浮动后，其后的元素将尽可能包围它，或者说出现在这个浮动元素的左或右方。  
如果希望浮动元素后面的元素在其下方显示，可使用`clear: both`样式来进行清除。  
#### 不透明度
我们可以用`opacity`对任何元素（不过常用于图片）设置不透明度。  
值在`[0.0～1.0]`之间，值越低，透明度越高。
#### 组合选择器
前面我们学习了 CSS有三种选择器：元素、id 和 class 。但我们也可以进行组合，以得到简洁精确的选择。
##### 后代选择器
以空格作为分隔，如：`.haha p `代表在`div`元素内有`.haha`这种类的所有元素。
使用方法：
```markdown
<html>
<head>
  <style>
    .haha p {
      background-color: yellow;
    }
  </style>
</head>
<body>
  <div class="haha">
    <p>Paragraph 1 in the div .haha.</p>
    <span>
        <p>Paragraph 2 in the div .haha.</p>
    </span>
  </div>
  <p>Paragraph 3. Not in a div .haha.</p>
</body>
</html>
```
段落1、2都将有黄色的背景，而段落3没有。


##### 子选择器（后代选择器）
也称为直接后代选择器，以`>`作为分隔，如：`.haha > p `代表在有`.haha`类的元素内的直接`<p>`元素。
使用方法：
```markdown
<html>
<head>
  <style>
    .haha > p {
      background-color: yellow;
    }
  </style>
</head>
<body>
  <div class="haha">
    <p>Paragraph 1 in the div .haha.</p>
    <span>
        <p>Paragraph 2 in the div .haha - it is descendant but not immediate child.</p>
    </span> <!-- not Child but Descendant -->
  </div>
</body>
</html>
```
虽然段落2在`.haha`类中，但它的直接父元素是`span`，不是`.haha`的直接后代，所以不能选择。只有段落1有黄色背景。
#### 伪类和伪元素
伪类（pseudo-class）或伪元素（pseudo-element）用于定义元素的某种特定的状态或位置等。  
使用伪类/伪元素的语法如下：
```markdown
/* 选择器后使用 : 号，再跟上某个伪类/伪元素 */
selector:pseudo-class/pseudo-element {
  property:value;
}
```
以下是常用的伪类/伪元素的简单使用：
```markdown
a:link {color:#FF0000;}     /* 未访问的链接 */
a:visited {color:#00FF00;}  /* 已访问的链接 */
a:hover {color:#FF00FF;}    /* 鼠标划过链接 */
/* 鼠标移到段落则改变背景颜色 */
p:hover {background-color: rgb(226, 43, 144);}
p:first-line{color:blue;}   /* 段落的第一行显示蓝色 */
p:first-letter{font-size: xx-large;}   /* 段落的第一个字超大 */

h1:before { content:url(smiley.gif); } /* 在每个一级标题前插入该图片 */
h1:after { content:url(smiley.gif); } /* 在每个一级标题后插入该图片 */
```

