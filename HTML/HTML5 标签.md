# HTML5 标签参考手册

## 1. 标签概述

### 1.1 定义

标签（Tag）是 HTML 文档的基本组成单位，使用尖括号 `<>` 表示。标签也称为**元素**（Element）。

### 1.2 分类

|类型|格式|示例|
|---|---|---|
|**双标签**|`<标签名>` + 内容 + `</标签名>`|`<h1>标题</h1>`|
|**单标签**（空元素）|`<标签名>` 或 `<标签名 />`|`<hr>`、`<img>`|

> 单标签（空元素）在 HTML5 中尾部斜杠可选，参见 [9. 空元素列表](HTML5%20标签#9.空元素列表)。

---

## 2. 文档结构标签

| 标签                | 说明                    | 属性                                      |
| ----------------- | --------------------- | --------------------------------------- |
| `<!DOCTYPE html>` | 文档类型声明，必须置于 HTML 文档首行 | —                                       |
| `<html>`          | 根元素，所有其他元素的后代         | `lang`：语言代码（`en`、`zh-CN` 等）             |
| `<head>`          | 文档元数据容器，内容不直接显示       | —                                       |
| `<meta>`          | 元数据，如字符集、视口、SEO 信息    | `charset`、`name`、`content`、`http-equiv` |
| `<title>`         | 页面标题，显示于浏览器标签栏        | —                                       |
| `<link>`          | 引入外部资源（CSS、图标等）       | `rel`、`href`、`type`、`media`             |
| `<style>`         | 内部 CSS 样式             | `type`、`media`                          |
| `<script>`        | 嵌入或引用 JavaScript      | `src`、`type`、`async`、`defer`            |
| `<body>`          | 页面可见内容容器              | —                                       |

---

## 3. 文本标签

|标签|说明|显示类型|
|---|---|---|
|`<h1>`~`<h6>`|标题，`<h1>` 层级最高|块级|
|`<p>`|段落|块级|
|`<br>`|强制换行|空元素（行内）|
|`<hr>`|水平分割线|空元素（块级）|
|`<span>`|通用行内容器，无语义|行内|
|`<div>`|通用块级容器，无语义|块级|
|`<strong>`|重要强调，默认粗体|行内|
|`<em>`|强调，默认斜体|行内|
|`<b>`|粗体（无语义）|行内|
|`<i>`|斜体（无语义）|行内|
|`<u>`|下划线|行内|
|`<s>`|删除线|行内|
|`<mark>`|高亮文本|行内|
|`<small>`|小号文字（如版权声明）|行内|
|`<code>`|代码片段|行内|
|`<pre>`|预格式化文本（保留空格与换行）|块级|
|`<blockquote>`|长引用（块级）|块级|
|`<q>`|短引用（自动加引号）|行内|
|`<abbr>`|缩写或首字母缩略词|行内|
|`<time>`|时间或日期|行内|
|`<sub>`|下标|行内|
|`<sup>`|上标|行内|

---

## 4. 列表标签

|标签|说明|子元素|
|---|---|---|
|`<ul>`|无序列表|`<li>`|
|`<ol>`|有序列表|`<li>`|
|`<li>`|列表项|—|
|`<dl>`|描述列表|`<dt>`、`<dd>`|
|`<dt>`|术语名称|—|
|`<dd>`|术语描述|—|

---

## 5. 表格标签

|标签|说明|属性|
|---|---|---|
|`<table>`|表格容器|`border`、`cellpadding`、`cellspacing`（建议 CSS）|
|`<thead>`|表头分组|—|
|`<tbody>`|表体分组|—|
|`<tfoot>`|表尾分组|—|
|`<tr>`|表格行|—|
|`<th>`|表头单元格|`colspan`、`rowspan`、`scope`|
|`<td>`|数据单元格|`colspan`、`rowspan`|

---

## 6. 链接与媒体标签

|标签|说明|必须属性|常用属性|
|---|---|---|---|
|`<a>`|超链接|`href`|`target`、`rel`、`download`、`title`|
|`<img>`|图片|`src`、`alt`|`width`、`height`、`loading`、`srcset`|
|`<picture>`|响应式图片容器|—|—|
|`<source>`|为 `<picture>` / `<video>` / `<audio>` 提供资源|`src` 或 `srcset`|`type`、`media`|
|`<video>`|视频|—|`src`、`controls`、`autoplay`、`loop`、`muted`、`width`、`height`、`poster`|
|`<audio>`|音频|—|`src`、`controls`、`autoplay`、`loop`、`muted`|
|`<track>`|视频/音频字幕|`src`、`kind`、`srclang`|`label`、`default`|
|`<iframe>`|内嵌页面|`src`|`width`、`height`、`allow`、`allowfullscreen`、`sandbox`|
|`<canvas>`|绘图画布（需 JavaScript 操作）|—|`width`、`height`|
|`<svg>`|矢量图形|—|—|
|`<embed>`|嵌入外部资源（已不推荐）|`src`|`type`、`width`、`height`|
|`<object>`|嵌入外部资源（替代方案）|`data`、`type`|—|

---

## 7. 表单标签

|标签|说明|常用属性|
|---|---|---|
|`<form>`|表单容器|`action`、`method`（`GET`/`POST`）、`enctype`、`novalidate`、`target`|
|`<input>`|输入控件|`type`、`name`、`value`、`placeholder`、`required`、`disabled`、`readonly`、`maxlength`、`pattern`、`min`、`max`、`step`、`checked`|
|`<label>`|输入控件标签|`for`（关联 `input.id`）|
|`<button>`|按钮|`type`（`submit`/`reset`/`button`）、`name`、`value`、`disabled`|
|`<select>`|下拉选择框|`name`、`multiple`、`size`、`required`|
|`<option>`|下拉选项|`value`、`selected`、`disabled`|
|`<optgroup>`|选项分组|`label`|
|`<textarea>`|多行文本输入|`name`、`rows`、`cols`、`placeholder`、`maxlength`、`required`|
|`<fieldset>`|表单字段分组|`disabled`、`form`|
|`<legend>`|分组标题|—|
|`<datalist>`|输入框预定义选项（自动补全）|—|
|`<output>`|计算结果输出|`name`、`for`|
|`<progress>`|进度条|`value`、`max`|
|`<meter>`|度量条|`value`、`min`、`max`、`low`、`high`、`optimum`|

### 7.1 `input` 的 `type` 属性值

|值|说明|
|---|---|
|`text`|单行文本|
|`password`|密码（输入内容被遮掩）|
|`email`|邮箱地址（含格式校验）|
|`number`|数字|
|`tel`|电话号码（移动端调出数字键盘）|
|`url`|URL 地址|
|`search`|搜索框|
|`date`|日期选择器|
|`datetime-local`|本地日期时间|
|`time`|时间|
|`month`|月份|
|`week`|周|
|`file`|文件上传|
|`checkbox`|复选框|
|`radio`|单选框（同 `name` 互斥）|
|`range`|滑块|
|`color`|颜色选择器|
|`hidden`|隐藏字段（不显示）|
|`submit`|提交按钮|
|`reset`|重置按钮|
|`button`|普通按钮|

---

## 8. 语义化结构标签（HTML5 新增）

|标签|语义|典型用途|
|---|---|---|
|`<header>`|页面或章节的头部|包含 logo、导航、标题|
|`<footer>`|页面或章节的底部|版权信息、联系方式、相关链接|
|`<nav>`|导航链接区域|主导航菜单|
|`<main>`|页面主体内容|每个页面仅使用一次|
|`<section>`|文档中的独立章节|具有主题性的内容区块|
|`<article>`|独立、可复用的内容块|博客文章、新闻条目、评论|
|`<aside>`|侧边栏或补充内容|广告、相关阅读、标签云|
|`<figure>`|自包含的插图/图表/代码|配合 `<figcaption>` 使用|
|`<figcaption>`|`<figure>` 的标题/说明|—|
|`<details>`|可展开/折叠的详情区域|常见问题（FAQ）|
|`<summary>`|`<details>` 的可见标题|—|
|`<dialog>`|对话框或弹窗|模态框、提示框|
|`<address>`|联系信息|作者邮箱、公司地址|

---

## 9. 空元素列表

空元素（Void Element）指不允许包含子节点或文本内容的 HTML 元素。此类元素在开始标签处闭合，**不得书写结束标签**。

### 9.1 分类列表

|分类|标签|用途说明|
|---|---|---|
|**文档基础**|`<base>`|设置文档中所有相对 URL 的基准路径|
||`<link>`|引入外部资源（CSS 样式表、网站图标等）|
||`<meta>`|定义字符集、视口设置、SEO 元数据等|
|**文本与排版**|`<br>`|强制换行|
||`<hr>`|主题分隔线（水平线）|
||`<wbr>`|建议换行点（单词过长时浏览器可在此断行）|
|**多媒体与嵌入**|`<img>`|嵌入图像|
||`<embed>`|嵌入外部资源（已不推荐）|
||`<source>`|为 `<picture>` / `<video>` / `<audio>` 指定资源|
||`<track>`|为 `<video>` / `<audio>` 指定字幕或元数据轨道|
|**表单与交互**|`<input>`|输入控件（`type` 属性决定具体类型）|
|**表格与映射**|`<col>`|定义表格列的样式属性（位于 `<colgroup>` 内）|
||`<area>`|定义图像映射中的可点击区域（位于 `<map>` 内）|

### 9.2 语法规范

|格式|示例|适用场景|
|---|---|---|
|**HTML5 格式**（无斜杠）|`<br>`、`<img src="a.jpg" alt="">`|纯 HTML5 文档（推荐）|
|**XHTML 格式**（加斜杠）|`<br />`、`<img src="a.jpg" alt="" />`|需兼容 XML / XHTML 解析器|

> 在 HTML5 中，尾部斜杠 `/` 被解析器忽略，两种写法等效。空元素不能包含内容，也不能书写 `</标签名>` 形式的结束标签。

### 9.3 常见错误

|错误写法|后果|
|---|---|
|`<br></br>`|无效，浏览器可能忽略或产生意外换行|
|`<img src="a.jpg">文字</img>`|文字不会被解析为内容，`</img>` 被忽略|
|`<div />` 或 `<p />`|`div`、`p` 非空元素，`/` 被忽略，浏览器继续寻找闭合标签，可能导致结构错乱|

> **核心原则**：仅限 9.1 中列出的空元素可以省略结束标签，非空元素必须使用 `<标签名>内容</标签名>` 的完整形式。

---

## 10. 全局属性

所有 HTML 标签均可使用的属性：

|属性|说明|
|---|---|
|`id`|唯一标识符|
|`class`|类名（可多个，空格分隔）|
|`style`|内联 CSS 样式|
|`title`|悬停提示文本|
|`data-*`|自定义数据属性|
|`hidden`|隐藏元素|
|`lang`|元素内语言|
|`contenteditable`|是否可编辑（`true`/`false`）|
|`tabindex`|Tab 键导航顺序|
|`role`|ARIA 角色（辅助功能）|
|`aria-*`|ARIA 状态与属性|

---

## 11. 事件属性（常用）

|属性|触发时机|
|---|---|
|`onclick`|鼠标点击|
|`ondblclick`|鼠标双击|
|`onmouseenter`|鼠标进入|
|`onmouseleave`|鼠标离开|
|`onfocus`|获取焦点|
|`onblur`|失去焦点|
|`onchange`|值发生变化（表单）|
|`oninput`|输入时（实时）|
|`onsubmit`|表单提交|
|`onload`|资源加载完成|
|`onerror`|加载失败|

---

## 12. 标签嵌套规范（简要）

|规则|说明|
|---|---|
|块级元素可包含行内元素与块级元素|如 `<div>` 可包含 `<span>` 和 `<p>`|
|行内元素一般只包含行内元素|如 `<span>` 不宜包含 `<div>`|
|`<p>` 标签内不能包含块级元素|如 `<p><div></div></p>` 无效|
|`<ul>` / `<ol>` 的直接子元素只能是 `<li>`|—|
|`<table>` 的直接子元素应为 `<thead>` / `<tbody>` / `<tfoot>` / `<tr>`|—|
|`<a>` 不可嵌套 `<a>`|—|
|`<button>` 内不可包含 `<input>`、`<a>` 等交互元素|—|

---

_本手册基于 HTML5 规范编写，适用于现代 Web 开发。_