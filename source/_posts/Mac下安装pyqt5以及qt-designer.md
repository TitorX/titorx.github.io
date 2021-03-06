---
id: 6
title: Mac下安装pyqt5以及qt-designer
author: Titor
date: 2018-04-14
tags:
    - Mac
    - qt
    - python
---

突然有想法写几个GUI的应用给自己用，因为平时win mac linux都在用，所以需要能很方便的跨平台。因此选择python以及qt5来做开发。这样子只需要一份代码就可以在所有平台上使用了。在mac上开发的时候，配置环境这里折腾了挺久，特此写篇文章记录下，避免再走弯路。

<!--more-->

在Mac上安装pyqt5还是挺简单的。配置好你的`python`环境以及安装好`pip`。

```
pip install pyqt5
```

这一步基本不会有什么错误。

下面一个困扰了我很久的问题就是，安装`qt-designer`。如果开发过GUI程序的话，都知道给程序界面布局是一个很繁琐、困难的工作。用代码去设置每一个控件的位置、布局，想想都头疼。使用qt开发的话，官方已经开发好了`qt-designer`工具，用一个可视化的界面，用拖动的方式来设计界面布局。而后在程序里直接载入生成好的界面，只需要写代码来控制控件的逻辑就可以了。

使用`pip install qt-tools`可以安装好`qt-designer`。但是这个方法不适用于Mac平台。我在寻找了很长一段时间之后，终于发现，在Mac下是无法单独安装`qt-designer`的，或者说，没有一个很简单的安装方法。只能安装`qt-creator`。

`qt-creator`是`qt`官方推出的一套开发套件，里面集成了很多实用的工具来辅助开发，`qt-designer`就是其中之一。`qt-creator`就是一套专门为`qt`定制的`IDE`。我们使用`python`开发的话，其实这个`IDE`是很多余的。里面集成了很多工具，如果用`C++`来开发的话，那这些都是非常实用的工具，但是实际上我们用到的只有一个`designer`。对我这个强迫症来说多少有些难受，不过也没什么办法，因为我实在找不到更简单的方法了。

```
brew cask install qt-creator
```

安装好qt-creator后，打开应用，界面如下。

![](/media/15236931573516.jpg)


前面也说过，`qt-creator`是一套针对`C++`的`IDE`。所以如果只是使用`designer`来设计界面的话，就不要试图点击`New Project`来创建一个项目。因为创建的是基于`C++`的项目，需要你去设置`gcc g++`之类的一大堆环境。我们需要的只是`qt-designer`。

正确的方式是点击菜单栏的`File`，选择`New File or Project`。

![](/media/15236934159135.jpg)

在随后弹出的窗口中选择`Qt` -> `Qt Designer Form`。这样子就可以创建一个`.ui`文件了，也可以尽情的在窗口中拖拽设计界面了。

![](/media/15236935194540.jpg)

至此，环境配置完毕。可以愉快地开发了。




