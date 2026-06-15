# Emmet 缩写语法参考手册

## 1. 概述

Emmet 是一款面向文本编辑器的插件，通过解析类似 CSS 选择器的缩写表达式，快速生成结构化 HTML、XML 及其他标记语言代码。本手册涵盖 HTML 片段生成及 CSS 属性缩写两大部分，适用于 VS Code、Sublime Text、WebStorm 等主流编辑器。

---

## 2. HTML 缩写核心规则

### 2.1 关系运算符

|运算符|名称|示例|输出结果（缩略）|
|---|---|---|---|
|`>`|子级|`div>p`|`<div><p></p></div>`|
|`+`|同级|`div+p`|`<div></div><p></p>`|
|`^`|提升一级|`div>p^span`|`<div><p></p></div><span></span>`|
|`*`|重复|`li*3`|`<li></li><li></li><li></li>`|
|`()`|分组|`(div>p)*2`|`<div><p></p></div><div><p></p></div>`|

> **注意**：`^` 可多次使用，如 `div>p^^span` 表示向上提升两级。

### 2.2 属性运算符

|运算符|用途|示例|输出|
|---|---|---|---|
|`#`|id 属性|`div#header`|`<div id="header"></div>`|
|`.`|class 属性|`div.box.red`|`<div class="box red"></div>`|
|`[]`|自定义属性|`a[href=# title=link]`|`<a href="#" title="link"></a>`|
|`{}`|文本内容|`p{Hello}`|`<p>Hello</p>`|

> **注意**：多个 class 需连续书写，无需分隔符（如 `.class1.class2`）。

### 2.3 编号与文本

|符号|说明|示例|输出|
|---|---|---|---|
|`$`|递增加1|`div$*3`|`<div1></div1><div2></div2><div3></div3>`|
|`$$`|补零（两位）|`div$$*3`|`<div01></div01><div02></div02><div03></div03>`|
|`$@N`|起始编号 N|`div$@5*2`|`<div5></div5><div6></div6>`|
|`$@-`|反向编号|`div$@-*3`|`<div3></div3><div2></div2><div1></div1>`|
|`lorem`|占位文本|`p>lorem10`|`<p>Lorem ipsum ... (10词)</p>`|

> **注意**：`lorem` 后可跟数字表示单词数，如 `lorem20`。

---

## 3. 隐式标签（默认标签）

当未显式指定标签名时，Emmet 根据上下文或根结构推断标签。

|上下文或缩写|隐式标签|示例|实际生成|
|---|---|---|---|
|任意位置（以 `.` 或 `#` 开头）|`div`|`.container`|`<div class="container"></div>`|
|`ul` / `ol` 内部|`li`|`ul>.item`|`<ul><li class="item"></li></ul>`|
|`select` 内部|`option`|`select>opt`|`<select><option class="opt"></option></select>`|
|`table` 内部|`tr`、`td`|`table>tr>td`|`<table><tr><td></td></tr></table>`|

---

## 4. 常用 HTML 片段快捷方式

|缩写|生成结果|
|---|---|
|`!` 或 `html:5`|HTML5 文档骨架（含 `<!DOCTYPE html>`、`<head>`、`<body>`）|
|`html:xt`|XHTML 过渡型文档|
|`html:4t`|HTML4 过渡型文档|
|`link:css`|`<link rel="stylesheet" href="style.css">`|
|`link:print`|`<link rel="stylesheet" href="print.css" media="print">`|
|`style`|`<style></style>`|
|`script`|`<script></script>`|
|`script:src`|`<script src=""></script>`|
|`img`|`<img src="" alt="">`|
|`img:z`|`<img src="" alt="" title="">`（无具体尺寸）|
|`input:text`|`<input type="text" name="" id="">`|
|`input:password`|`<input type="password" name="" id="">`|
|`input:checkbox`|`<input type="checkbox" name="" id="">`|
|`input:radio`|`<input type="radio" name="" id="">`|
|`input:submit`|`<input type="submit" value="">`|
|`input:button`|`<input type="button" value="">`|
|`input:file`|`<input type="file" name="" id="">`|
|`input:email`|`<input type="email" name="" id="">`|
|`btn`|`<button></button>`|
|`btn:s`|`<button type="submit"></button>`|
|`form:get`|`<form action="" method="get"></form>`|
|`form:post`|`<form action="" method="post"></form>`|
|`select`|`<select name="" id=""></select>`|
|`textarea`|`<textarea name="" id="" cols="30" rows="10"></textarea>`|
|`iframe`|`<iframe src="" frameborder="0"></iframe>`|
|`meta:utf`|`<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">`|
|`meta:vp`|`<meta name="viewport" content="width=device-width, initial-scale=1.0">`|

---

## 5. CSS 缩写规则

在 CSS 文件中使用 Emmet 时，支持**属性值缩写**，规则如下：

|缩写模式|含义|示例|输出|
|---|---|---|---|
|`m10`|margin: 10px;|`m10`|`margin: 10px;`|
|`m10-20`|margin: 10px 20px;|`m10-20`|`margin: 10px 20px;`|
|`m10-20-5`|margin: 10px 20px 5px;|`m10-20-5`|`margin: 10px 20px 5px;`|
|`m10-20-5-1`|margin: 10px 20px 5px 1px;|`m10-20-5-1`|`margin: 10px 20px 5px 1px;`|
|`p10`|padding: 10px;|同 margin|—|
|`w100`|width: 100px;|`w100`|`width: 100px;`|
|`h50`|height: 50px;|`h50`|`height: 50px;`|
|`c#333`|color: #333;|`c#333`|`color: #333;`|
|`bgc#fff`|background-color: #fff;|`bgc#fff`|`background-color: #fff;`|
|`fs16`|font-size: 16px;|`fs16`|`font-size: 16px;`|
|`fw700`|font-weight: 700;|`fw700`|`font-weight: 700;`|
|`lh1.5`|line-height: 1.5;|`lh1.5`|`line-height: 1.5;`|
|`dib`|display: inline-block;|`dib`|`display: inline-block;`|
|`df`|display: flex;|`df`|`display: flex;`|
|`jcc`|justify-content: center;|`jcc`|`justify-content: center;`|
|`aic`|align-items: center;|`aic`|`align-items: center;`|
|`posr`|position: relative;|`posr`|`position: relative;`|
|`posa`|position: absolute;|`posa`|`position: absolute;`|
|`t0`|top: 0;|`t0`|`top: 0;`|
|`l10`|left: 10px;|同理可推 `r`、`b`|—|
|`bd1`|border: 1px solid #000;|`bd1`|`border: 1px solid #000;`|
|`bdrs50%`|border-radius: 50%;|`bdrs50%`|`border-radius: 50%;`|

> **注意**：数值默认单位为 `px`，若需其他单位（如 `%`、`em`），须显式写出，如 `w50%`、`m1.5em`。

---

## 6. 组合与嵌套示例

|目标结构|Emmet 缩写|
|---|---|
|导航菜单（4项带链接）|`nav>ul>li*4>a[href="#"]{菜单$}`|
|3行×3列表格|`table>tr*3>td*3`|
|图片卡片（含图片、标题、文本）|`.card>img[src="pic.jpg"]+h3{标题}+p>lorem10`|
|表单（用户名、密码、提交）|`form>label{用户名}+input:text+br+label{密码}+input:password+br+input:submit`|
|典型页面布局|`header>nav+main+footer` 或 `div.wrapper>header+section.content+aside.sidebar+footer`|
|带编号的列表|`ol>li.item$*5>{项目$}`|
|分组加属性|`(div>p)*2[title=group]` → `<div title="group"><p></p></div>`×2|

---

## 7. 编辑器配置（以 VS Code 为例）

以下为典型设置项（`settings.json`）：

json

{
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "vue-html": "html",
    "vue": "html"
  },
  "emmet.syntaxProfiles": {
    "html": {
      "self_closing_style": "html"   // 空元素不加斜杠，可选 "xhtml" 则加 /
    }
  },
  "emmet.preferences": {
    "css.intUnit": "px"              // CSS 缩写默认单位
  }
}

---

## 8. 注意事项

1. **空元素闭合**：HTML5 规范允许空元素（`<br>`、`<img>` 等）省略尾部斜杠。若需 XHTML 风格，设置 `"self_closing_style": "xhtml"`。
    
2. **非空元素不能自闭合**：不要对 `<div>`、`<p>` 等容器使用 `/>`，否则解析异常。
    
3. **CSS 缩写仅在样式文件或样式块中生效**：Emmet 根据文件类型判断是否启用 CSS 规则。
    
4. **隐式标签并非在所有上下文中可靠**：建议新手显式写出标签名，避免歧义。
    
5. **缩写的扩展键**：默认 `Tab`，部分编辑器可能为 `Enter`，可自定义。
    

---

_本手册基于 Emmet v2.x 规范编写，适用于现代代码编辑器。_