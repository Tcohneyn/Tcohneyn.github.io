# 主题文档 - Hugo美化


# 【Hugo】LoveIt主题自定义修改

## 1.修改鼠标样式

* (1) 准备好鼠标样式图片(默认，指针，文本…)，图片大小建议控制在 **32px** 左右，将图片放入`static/mouse`文件夹下(文件夹自己创建)

![](.\Snipaste_2026-09-01_20-30-15.png)

- (2) 修改`assets/css/_custom.scss`(文件不存在则自己创建)，将以下代码复制进去，根据主题按实际情况填写对应的css选择器

```
// ==============================
// Custom style
// 自定义样式
// ==============================
/* ===== 自定义鼠标光标（LoveIt + 纯 PNG）===== */

// 1. 默认光标
body,
.single .content,
.home .home-profile {
  cursor: url("/mouse/default.png") 16 16, auto;
}

// 2. 指针光标（链接、按钮）
a:hover,
button:hover,
.theme-switch,
.header .menu .menu-item a:hover {
  cursor: url("/mouse/pointer.png") 16 16, pointer;
}

// 3. 文本光标（输入框、正文）
input,
textarea,
.single .content p,
.single .content li {
  cursor: url("/mouse/text.png") 16 16, text;
}
```

## 2.macOS风格的代码块

* 准备一张macOS代码块的[**红绿灯图片**](./macOS-code-header.svg)(Ctrl+S保存), 放到`static/icons`文件夹下
* 将以下代码复制进`assets/css/_custom.scss`文件中(不存在则自行创建)

```
/* ===== macOS 风格代码块 ===== */

.highlight {
  border-radius: var(--card-border-radius);
  max-width: 100% !important;
  margin: 1rem 0 !important;
  box-shadow: var(--shadow-l1) !important;
  overflow: hidden;
}

// 隐藏 LoveIt 原生的代码块头部（包含语言名称和复制按钮）
.highlight .code-header {
  display: none !important;
}
// 用伪元素生成 macOS 圆点条
.highlight:before {
  content: "";
  display: block;
  background: url(/icons/macOS-code-header.svg) no-repeat 12px center;
  background-size: 48px 12px;
  height: 28px;
  background-color: var(--code-bg, #f6f8fa);
  border-bottom: 1px solid var(--border-color, #e1e8ed);
}
```


