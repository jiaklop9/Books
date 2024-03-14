# BOM
## windows 对象
&emsp; &emsp; 既是javascript访问浏览器窗口的一个接口，又是ECMAScript规定的一个全局对象。<br>
&emsp; &emsp; 定义全局变量与在 window 对象上直接定义属性还是有一点差别：全局变量不能通过 delete 操作符删除，而直接在 window 对象上的定义的属性可以

## 窗口关系及框架
&emsp; &emsp; 如果页面中包含框架，则每个框架都拥有自己的 window 对象，并且保存在 frames 集合中。
在 frames 集合中，可以通过数值索引（从 0 开始，从左至右，从上到下）或者框架名称来访问相应的 window 对象<br>
&emsp; &emsp; **top对象**始终指向最高层(最外层)框架。

## location对象
&emsp; &emsp; location 对象是很特别的一个对象，因为它既是 window 对象的属性，也是
document 对象的属性；换句话说，window.location 和 document.location 引用的是同一个对象。
location 对象的用处不只表现在它保存着当前文档的信息，还表现在它将 URL 解析为独立的片段，让
开发人员可以通过不同的属性访问这些片段

## navigator对象
