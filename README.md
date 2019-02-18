# 《Cascading Style Sheets》博士论文翻译

- 原文 <https://www.wiumlie.no/2006/phd/>

* [摘要](#摘要)
* [灵感](#灵感)
* [致谢](#致谢)

* [一、介绍](#介绍)
  * [1.1结构vs展示](#结构vs呈现   )



# 一、介绍

大约在1990年，Tim Berners-Lee设计了构筑万维网(world wide web)基础的三大技术规范：为web提供文档格式化的超文本标记语言(HTML)；为文档之间添加链接的Universal Resource Locators(URL)技术；为各机器在internet上传送文件的超文本传输协议（HTTP），这些技术的规范及实现都由CERN组织免费提供。

web世界快速发展，1993年，国家超级计算应用中心NCSA(National Center for Supercomputing Applications)推出了Mosaic浏览器，用户突然拥有了一个魅力浏览器，利用它可以在各个相互关联的文档之间进行网络冲浪了，伴随着用户量的激增，更多的创作者被web所吸引，更多的内容随之被传播。

在最开始，HTML只是一个简单的结构化文档格式，用来在文本字符串之间添加标记来指明文本的角色。例如：一个文本的字符串可以被标记为段落，同时另一些字符串可以被标记为可点击的链接，这些元素在早期的HTML中，其逻辑性更胜其于呈现性。例如，HTML将会把一些文本标记为heading元素(头部)，但不会描述heading(头部)元素该如何呈现。文本的呈现-包括使用字体、颜色、大小等主要由浏览器决定。

## 1.1 结构vs呈现

通过将展示表情添加到HTML中
