# JavaScript学习笔记

## 一、核心概念

JavaScript（简称JS）是一门跨平台、面向对象的脚本语言，主要用于为网页添加交互效果（如表单验证、动态样式、动画等），常与HTML、CSS配合开发动态网站。其核心组成包括三部分：

- ECMAScript（ES）：定义基础语法规范（如变量、循环、函数等），目前主流版本为ES6及以上。
- DOM（文档对象模型）：提供操作网页元素的API（如增删节点、修改样式）。
- BOM（浏览器对象模型）：提供操作浏览器的API（如弹窗、页面跳转、本地存储）。

## 二、基础语法

### 1.引入方式

- 内部脚本：在HTML中用 <script> 标签包裹代码，建议放在 <body> 底部（避免阻塞页面加载）。

<script>
  alert("Hello, JS!"); // 弹窗显示文本
</script>

- 外部脚本：通过 <script src="路径.js"></script> 引入外部文件，适合代码复用。

### 2.变量与数据类型

- 变量定义：使用 var （函数作用域）、 let （块级作用域）或 const （常量，不可修改）声明。

let name = "Alice"; // 字符串类型
const age = 20;     // 数字类型（不可修改）

- 数据类型：
- 基本类型：Number（数字）、String（字符串）、Boolean（布尔值）、Undefined（未赋值）、Null（空值）。
- 引用类型：对象（ {} ）、数组（ [] ）、函数等。

### 3.输出语句

-  console.log("内容") ：在浏览器控制台打印（推荐调试用）。
-  alert("内容") ：弹出警告框。
-  document.write("内容") ：直接写入HTML页面。

## 三、核心语法

### 1.流程控制

- 条件语句： if...else 、 switch 

if (age >= 18) {
  console.log("成年");
} else {
  console.log("未成年");
}

- 循环语句： for 、 while 、 for...in （遍历对象）。

### 2.函数

- 定义与调用：封装可复用代码块，支持参数和返回值。

function add(a, b) {
  return a + b; // 返回计算结果
}
console.log(add(2, 3)); // 输出：5

### 3.数组与对象

- 数组：有序集合，支持增删改查。

let fruits = ["[苹果](https://open.toutiao.com/article/url/?param=UY8vg8rg8Uwb93zX1mar8DK1NMK6S16bQ1wzHCF5jPxWz22mkULsqFNTGeXGtsxxVNq38KGQSZdfvvhdNGSiwMB55p9c96iEb2pEFbsHEDKpJgzPyZoszPfYJmaEsBJ5P9i5KuAV5Fa5RBereiyyZUmU3g8ZzWbYZDFbxmNyzxt6dfCzWon6DuZYhyqrLcveeFb54z7UBsxDqkYj5xtfoEdXwL9Z2Vbb9UZYUnKNmb7RT8q8BW1yhcq3A3zp2ej&partner=agent_bot_7520145467502544393_default_content&version=3)", "[香蕉](https://open.toutiao.com/article/url/?param=UY8vg8rg8Uwb93zX1mar8DK1NMK6S16bQ1wzHCF5jR89n2T6tVfMs5jdyfShQ9zjrQ7jUxidrWxvQ4LnigG1E7uU9UhXfgEbLPLSkM1mYJr49aUi1CSvXhmgaLLQR3HgzgoDAjshoL8pxrXxdF1azD5a3yPWYprnTaHq5yC7SBtJRqvtuW2cSWZWsxWZy3WzAnqxZYSY71BJNEeV3HLmmzhDEiQpz3PpTUvcYRPtzTVwkYgoCnebVmcg5zywpo1&partner=agent_bot_7520145467502544393_default_content&version=3)"];
fruits.push("橙子"); // 添加元素，数组变为 ["苹果", "香蕉", "橙子"]

- 对象：键值对集合，用于描述复杂数据。

let person = {
  name: "Bob",
  age: 25,
  sayHi: function() { // 方法
    console.log("Hi!");
  }
};

### 4.DOM事件基础

事件是用户与页面的交互行为（如点击、输入），三要素为事件源、事件类型、事件处理函数。

- 绑定方式：推荐使用 addEventListener （可多次绑定同一事件）。

// 点击按钮时执行函数
document.querySelector("button").addEventListener("click", function() {
  alert("按钮被点击了！");
});

参考资料：[bilibili]([3小时前端入门教程（HTML+CSS+JS）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1BT4y1W7Aw/?spm_id_from=333.1387.homepage.video_card.click&vd_source=6024f9725f9aefcc7edef6a7b96f4535))