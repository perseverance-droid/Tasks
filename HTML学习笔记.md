# HTML学习笔记

## 核心概念

- HTML（HyperText Markup Language）：用于创建网页结构的标记语言，通过标签描述页面元素（如文本、图片、链接等）。
- 标签语法：通常由尖括号  <>  包裹，分为双标签（如  <html></html> ）和单标签（如  <img /> ）。

基础结构


<!DOCTYPE html>  <!-- 声明文档类型为HTML5 -->
<html>           <!-- 根标签，包含整个页面内容 -->
  <head>         <!-- 头部，存放元数据（如标题、样式链接等） -->
    <meta charset="UTF-8">  <!-- 设置字符编码 -->
    <title>页面标题</title>  <!-- 浏览器标签页显示的标题 -->
  </head>
  <body>         <!-- 主体，页面可见内容 -->
    <h1>这是一级标题</h1>
    <p>这是一个段落。</p>
  </body>
</html>
 

常用标签分类

- 文本标签：

-  <h1> - <h6> ：标题（h1最大，h6最小）
-  <p> ：段落
-  <strong> ：加粗（强调重要性）
-  <em> ：斜体（强调语气）
- 链接与图片：

-  <a href="https://example.com">链接文本</a> ：超链接（ href 属性指定目标地址）
-  <img src="image.jpg" alt="图片描述"> ：图片（ src 为路径， alt 为替代文本）
- 列表：

- 无序列表： <ul><li>项目1</li><li>项目2</li></ul> （默认显示圆点）
- 有序列表： <ol><li>步骤1</li><li>步骤2</li></ol> （默认显示数字）

核心注意事项

- HTML标签不区分大小写，但推荐小写（符合规范）
- 标签需正确嵌套（如  <p><strong>文本</strong></p> ，而非交叉嵌套）
- 学习时可结合浏览器“开发者工具”（F12）查看真实网页的HTML结构，帮助理解

参考资料：[bilibili]([3小时前端入门教程（HTML+CSS+JS）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1BT4y1W7Aw/?spm_id_from=333.1387.homepage.video_card.click&vd_source=6024f9725f9aefcc7edef6a7b96f4535))