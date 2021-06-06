#### Learning Record

一些关于初次学习Web的记录。

# HTML

简介：HTML是超文本标记语言（HyperText Markup Language）的缩写。HTML 是构成 Web 世界的一砖一瓦。它定义了网页内容的含义和结构。HTML 不是一门编程语言，而是一种用于定义内容结构的标记语言。

## HTML 文档结构
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
## 结构解析
1.`<!DOCTYPE html>`: 声明文档类型。（可有可无。）  
2.`<html></html>`: <html>元素。包含整个完整的页面。（根元素，其它元素都嵌套在其中。）  
3.`<head></head>`: <head>元素。 包含所有想包含在HTML页面中但不想在HTML页面中显示的内容。（包括想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。）  
4.`<meta charset="utf-8">`: 设置文档使用utf-8字符集编码。（utf-8字符集包含了人类大部分的文字。）  
5.`<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`: 指定页面的图标。（出现在浏览器标签上。）  
6.`<title></title>`: 设置页面标题。（出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面。）  
7.`<body></body>`: <body>元素。 包含页面所有内容，如文本，图片，音频，游戏等等。


## 元素
```markdown
<开始标签>内容<结束标签>
```
以上结构便是完整元素，整个HTML就由一个个元素组成（可以嵌套），而元素则一般由一对标签（tag）构成。

### 标题
  HTML提供了从大到小6级标题，分别是：<h1> ~ <h6>。


#### 标题的作用：
  1\.搜索引擎用标题来索引页面的内容
  2\.用户也习惯以标题进行主要内容浏览，以决定是否查看该页面


#### 使用方法
```markdown
  <h1>heading</h1>
  <p>text</p>
  <hr>
```

# CSS
简介：CSS是级联样式表（Cascading Style Sheets）的缩写。HTML 用于撰写页面的内容，而 CSS 将决定这些内容该如何在屏幕上呈现。如果说HTML是一砖一瓦，那么css就是房屋的修饰如油漆、墙纸等。




