# 《Cascading Style Sheets》博士论文翻译

- 原文 <https://www.wiumlie.no/2006/phd/>

* [摘要](#摘要)
* [灵感](#灵感)
* [致谢](#致谢)

* [一、介绍](#介绍)
  * [1.1结构vs呈现](#结构vs呈现)
    * [1.1.1抽象级别](#抽象级别)



# 一、介绍

大约在1990年，Tim Berners-Lee设计了构筑万维网(world wide web)基础的三大技术规范：为web提供文档格式化的超文本标记语言(HTML)；为文档之间添加链接的Universal Resource Locators(URL)技术；为各机器在internet上传送文件的超文本传输协议（HTTP），这些技术的规范及实现都由CERN组织免费提供。

web世界快速发展，1993年，国家超级计算应用中心NCSA(National Center for Supercomputing Applications)推出了Mosaic浏览器，用户突然拥有了一个魅力浏览器，利用它可以在各个相互关联的文档之间进行网络冲浪了，伴随着用户量的激增，更多的创作者被web所吸引，更多的内容随之被传播。

在最开始，HTML只是一个简单的结构化文档格式，用来在文本字符串之间添加标签(tags)来指明文本的角色。例如：一个文本的字符串可以被标记为段落，同时另一些字符串可以被标记为可点击链接，这些元素在早期的HTML中，其逻辑性更胜其于呈现性。例如，HTML将会把一些文本标记为标题元素(heading)，但不会描述标题(heading)元素该如何呈现。文本的呈现-包括使用字体、颜色、大小等主要由浏览器决定。

## 1.1 结构vs呈现

像CERN这样的科研组织更注重逻辑、结构和内容，而不是美学、意象和样式，这种结构化的观念反映到了HTML设计中——每个段落就标记为"段落"(paragraph)，每个标题(heading)都被赋予一个级别编号，以指明它们在文档结构中的位置(译者注: 如h1、h2这种标题编号)。

由于web吸引了更多的科研组织以外的人，web创作者们开始抱怨他们没有足够的覆盖原生页面外观的影响力，新的web创作者们最常抱怨的一个问题就是如何更改元素的字体和颜色。以下内容是1994年初发送到www-talk邮件列表的邮件摘要，由此可以看出web创作者们和浏览器标准制定者的紧张关系(我在本章中引用了发送给开发者社区的邮件消息列表，并将在后续章节中反复引用，邮件列表对于早期的网络社区聚集至关重要，邮件列表的超文本档案在20世纪90年代初快速崛起并发展壮大，10年后的今天，这些档案为web的设计和开发提供了宝贵的视角)：

>事实上，在过去一年里，我不断的告诉那些成群结队(反正就是很多很多的意思)的人——那些想要把自己绑在这里，试着像在Tex、Microsoft Word等常见文本处理软件那样在web上处理好文本展示的人：“哈哈，对不起，你完蛋了！”，这对我来说是一件无比搞笑的事。

这篇消息的作者是Marc Andreessen，他是流行浏览器——NCSA Mosaic背后的一名开发者，后来他成为了网景浏览器(Netscape)的联合创始人，网景浏览器通过在HTML中引入表示性的标签来满足创作者们的需求。1994年10月13日，网景公司发布了他们的第一款beta版浏览器，网景浏览器支持一组新的表示性HTML标签(如居中标签：center)，不久，更多的同类标签加入进来。

通过将展示表情添加到HTML中

### 1.1.1 抽象级别
通过向html中添加展示性标签，它从一种抽象的、结构化的超文本标记语言(创作者们为文本标记不同的逻辑性角色(段落、标题、列表等))，演变为强调文档的最终呈现方式(字体、颜色和布局)的具体的展示性语言。
在传统的印刷出版时代，读者会收到经过处理后的成品印刷物，印刷物上的每个文字都有其固定的位置、形状、大小和颜色，读者无法更改其展现方式。然而，电子文档是半成品，必须经过装配(assembly)处理后才能呈现给人类读者，装配过程中(常被称为格式化(formatting)过程)，对如何呈现文档提供了多种多样的选择性。例如：浏览器在彩色屏幕上呈现文档时必须要选择要使用的字体和颜色。电子文档所需处理的等级将会因文档的不同格式而有很大的差异，电子文档类似于家具：有些家具已事先预装好，而有些家具买来时只是一个个打包的平面板子，需要买主自己组装好。如果一方文档需要做大量的处理，我们称其为较高级别的抽象，如果一份文档只需要少量的处理，我们则称其为较低级别的抽象。
确定合适的抽象级别是文档格式设计的重要环节，如果抽象的级别较高，创作和格式化的复杂度也会随之增加，创作者必须涉及到不可见的抽象概念，在接收端，如果元素的抽象级别较高，浏览器必须把高度抽象的元素转变为具体的对象，这将变得非常复杂，不过高级抽象也并非没有好处，它的好处是便于在多处上下文中复用，例如：标题元素可以在印刷文档中以大写字母的形式呈现，并且标题元素在文本转换为语音的系统中将会具有更大的声音。
相反，较低的抽象级别将会使创作和格式化过程变得更加简易(在某种成都上来说),创作者将会使用所见即所得的富文本编辑工具(WYSIWYG)，并且浏览器在呈现视图的过程中也无需执行复杂的转换任务，使用“面向表现对象”的文档格式的缺点是——内容在其它上下文中难以复用，例如：难以在不同屏幕尺寸的设备上实现“面向表示对象”的内容，也很难让视力障碍者获取“面向表示对象”的内容。
将文档从一种格式转换为另一种格式时，两种格式可能处于不同的抽象级别，通常，可以将文档从较高级别的抽象转换为较低级别的抽象，但反之则不行。本论文将介绍一种度量抽象级别的“抽象阶梯”。
