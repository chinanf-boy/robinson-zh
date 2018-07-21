# [robinson][commit] [![explain]][source] [![translate-svg]][translate-list]

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list

「 使用 `rust` 构建自己的网络渲染引擎 **robinson-罗宾逊** 」

[commit]: https://github.com/mbrubeck/robinson/tree/dfd5c3b3f88ebe10c5286414e87dea9bda60f611

欢迎 `Issue` 和 `Pull` ❤️, 最好 `Pull` 👏

[更多其他中文翻译](https://github.com/chinanf-boy/chinese-translate-list)

---

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---


## 校对🀄️

- ⏰ 2018 7.13 开始

-   [x] [robinson/readme.md](README.zh.md)
-   [x] [第1部分: 入门](0.zh.md)
-   [x] [第2部分: HTML](1.zh.md)
-   [x] [第3部分: CSS](2.zh.md)
-   [x] [第4部分: style](3.zh.md)
-   [x] [第5部分: 盒子](4.zh.md)
-   [x] [第6部分: 块布局](5.zh.md)
-   [x] [第7部分: 绘画101](6.zh.md)

## 目录

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [罗宾逊](#%E7%BD%97%E5%AE%BE%E9%80%8A)
  - [状态](#%E7%8A%B6%E6%80%81)
  - [说明](#%E8%AF%B4%E6%98%8E)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---


# 罗宾逊

由Rust语言编写的玩具 - 网络渲染引擎,由 Matt Brubeck (mbrubeck@limpet.net) 撰写. 

我写的这段代码纯粹是出于教育目的. 我的目标是创建一个不完整但非常简单的引擎,作为了解更多基本实现技术的方法,*无需*担心的并发症如: 

-   <s>现实世界的可用性</s>
-   <s>符合标准</s>
-   <s>性能和效率</s>
-   <s>互通性</s>

这些都是重要的目标,但还有其他项目在研究它们. 通过完全忽略它们,该项目可以专注于尽可能简单易懂. 

为什么要创建一个简单但无用的玩具渲染引擎? 主要是因为我个人想学习如何做到这一点. 如果我成功了,我也希望其他人可以通过 阅读或修改代码 来学习我的代码,或者在他们开始构建自己的玩具浏览器引擎时 学习我的经验. 

有关详细信息,请参阅[ Let's build a browser engine!, `en`][blog],基于这个项目的一系列`how-to`文章. 

[blog]: http://limpet.net0.zh.md

或者 [让我们构建一个浏览器引擎! 中文 - ./0.zh.md](./0.zh.md)

## 状态

目前实现: 

-   解析一小部分HTML,并构建DOM树. 
-   解析一小部分CSS. 
-   执行 选择器-selector匹配 将样式应用于元素. 
-   基本块布局. 

很快,我希望: 

-   内联布局. 
-   绘制文本和框. 
-   从网络或文件系统加载资源. 

## 说明

1.  [安装Rust 1.0 beta 或 更新版本. ](http://www.rust-lang.org/install.html)

2.  克隆robinson源代码<https://github.com/mbrubeck/robinson>

3.  用`cargo build`建立鲁宾逊,和`cargo run`运行它. 

要在启用优化的情况下构建和运行,请使用`cargo build --release`和`cargo run --release`. 

默认情况下,robinson将从`examples`目录中加载test.html和test.css. 你可以使用`--html`和`--css`robinson可执行文件的参数 更改输入文件: 

    ./target/debug/robinson --html examples/test.html --css examples/test.css

渲染的页面将保存到名为`output.png`的文件中. 要更改输出文件名,请使用`-o`选项. 要切换到PDF输出,请使用`--format pdf`. 
