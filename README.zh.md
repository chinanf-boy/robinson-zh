
# 罗宾逊

由Rust语言编写的玩具网络渲染引擎,由Matt Brubeck (mbrubeck@limpet.net) 撰写. 

我写的这段代码纯粹是出于教育目的. 我的目标是创建一个不完整但非常简单的引擎,作为了解更多基本实现技术的方法,*无*担心并发症如: 

-   <s>现实世界的可用性</s>
-   <s>符合标准</s>
-   <s>性能和效率</s>
-   <s>互通性</s>

这些都是重要的目标,但还有其他项目在研究它们. 通过完全忽略它们,该项目可以专注于尽可能简单易懂. 

为什么要创建一个简单但无用的玩具渲染引擎?主要是因为我个人想学习如何做到这一点. 如果我成功了,我也希望其他人可以通过阅读或修改代码来学习我的代码,或者在他们开始构建自己的玩具浏览器引擎时学习我的经验. 

有关详细信息,请参阅[让我们构建一个浏览器引擎!][blog],基于这个项目的一系列how-to文章. 

[blog]: http://limpet.net/mbrubeck/2014/08/08/toy-layout-engine-1.html

## 状态

目前实施: 

-   解析一小部分HTML并构建DOM树. 
-   解析一小部分CSS. 
-   执行选择器匹配以将样式应用于元素. 
-   基本块布局. 

很快,我希望: 

-   内联布局. 
-   绘制文本和框. 
-   从网络或文件系统加载资源. 

## 说明

1.  [安装Rust 1.0 beta或更新版本. ](http://www.rust-lang.org/install.html)

2.  克隆robinson源代码<https://github.com/mbrubeck/robinson>

3.  跑`cargo build`建立鲁宾逊,和`cargo run`运行它. 

要在启用优化的情况下构建和运行,请使用`cargo build --release`和`cargo run --release`. 

默认情况下,robinson将从中加载test.html和test.css`examples`目录. 你可以使用`--html`和`--css`robinson可执行文件的参数更改输入文件: 

    ./target/debug/robinson --html examples/test.html --css examples/test.css

渲染的页面将保存到名为的文件中`output.png`. 要更改输出文件名,请使用`-o`选项. 要切换到PDF输出,请使用add`--format pdf`. 
