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


####
####
