# CSS学习笔记

## 一、核心概念

CSS（层叠样式表）是用于美化HTML页面的样式语言，通过控制文本、布局、颜色等视觉效果，实现内容与表现的分离。其核心优势包括：

- 样式复用：统一管理页面风格，降低维护成本。
- 灵活布局：支持多种定位和浮动方式，适配不同屏幕。

## **二、基础语法**

CSS规则由 选择器和 声明块组成，声明块包含属性与值的键值对：

选择器 {
  属性1: 值1;  /* 声明1 */
  属性2: 值2;  /* 声明2 */
}


示例：将所有段落文本设为蓝色、16px字号

p {
  color: blue;
  font-size: 16px;
}

#### **三、引入方式（优先级从高到低）**

1. **行内样式**：直接写在HTML标签的`style`属性中，仅作用于单个元素。  
   ```html
   <p style="color: red;">行内样式文本</p>
   ```@ref[1,4]  

2. **页面级CSS**：在`<head>`中用`<style>`标签包裹，作用于当前页面。  
   ```html
   <style>
     p { color: green; }
   </style>
   ```@ref[1,6]  

3. **外部CSS文件**：通过`<link>`标签引入`.css`文件，可跨页面复用（推荐）。  
   ```html
   <link rel="stylesheet" href="style.css">
   ```@ref[1,4]  

#### **四、核心选择器**
| 类型           | 语法示例          | 作用描述                       |
| -------------- | ----------------- | ------------------------------ |
| **标签选择器** | `p { ... }`       | 选中所有`<p>`标签元素          |
| **类选择器**   | `.box { ... }`    | 选中所有`class="box"`的元素    |
| **ID选择器**   | `#header { ... }` | 选中唯一`id="header"`的元素    |
| **后代选择器** | `div p { ... }`   | 选中`<div>`内的所有`<p>`子元素 |
| **伪类选择器** | `a:hover { ... }` | 鼠标悬停在链接上时生效         |

**优先级规则**：ID选择器 > 类选择器 > 标签选择器，行内样式 > 页面级CSS > 外部CSS@ref[6]。  

#### **五、常用属性**
1. **字体文本** 
   - `font-size: 16px`：字号（px为像素单位）  
   - `color: #333`：文本颜色（支持十六进制、RGB等格式）  
   - `text-align: center`：文本居中对齐@ref[9,10]  

2. **背景** 
   - `background-color: #f5f5f5`：背景色  
   - `background-image: url("bg.jpg")`：背景图片@ref[7,9]  

3. **盒模型** 
   - `width: 200px`、`height: 100px`：内容区域尺寸  
   - `padding: 10px`：内边距（内容与边框的距离）  
   - `margin: 20px`：外边距（元素与其他元素的距离）  
   - `border: 1px solid #000`：边框（宽度、样式、颜色）@ref[10]  

#### **六、元素分类**
1. **块级元素**（`display: block`）：独占[一行](https://open.toutiao.com/article/url/?param=UY8vg8rg8Uwb93zX1mar8DK1NMK6S16bQ1wzHCF5jR9EHeZHTMSTkmM1T2EZA4veo6NgDVx1RJjj8gv6NCAi9DnBMDuurVVnUT9nTGbANnFmHC6MYicu6fgFxkBrMwVKYYkqajfKjpZ4pS6vxwFHFGFygLP3uUh1PiPRmPHLpW2hz2zxkFongykWNApqgXU3xe9tVp6ctmfrm6BEheGDw7SAifkPXzXwJNk3xDJ9E2vjdKXkcghbQQhxZQJecsZ&partner=agent_bot_7520145467502544393_default_content&version=3)，可设置宽高（如`<div>`、`<p>`）。  
2. **行内元素**（`display: inline`）：不换行，宽高由内容决定（如`<span>`、`<a>`）。  
3. **行内块元素**（`display: inline-block`）：兼具行内与块级特性（如`<img>`）。@ref[8]  

参考资料：[bilibili]([3小时前端入门教程（HTML+CSS+JS）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1BT4y1W7Aw/?spm_id_from=333.1387.homepage.video_card.click&vd_source=6024f9725f9aefcc7edef6a7b96f4535))