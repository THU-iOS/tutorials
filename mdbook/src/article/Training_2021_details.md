# Training Details 2021, July

- [Training Details 2021, July](#training-details-2021-july)
  - [WWDC](#wwdc)
  - [Stanford CS193p - Developing Apps for iOS](#stanford-cs193p---developing-apps-for-ios)
    - [Basic](#basic)
    - [Advanced](#advanced)
  - [浙江大学 - Swift创新导论](#浙江大学---swift创新导论)
    - [第一周](#第一周)
    - [第二周](#第二周)
    - [第三周](#第三周)
  - [Aimls - Swift编程基础](#aimls---swift编程基础)
  - [designcode - SwiftUI iOS](#designcode---swiftui-ios)
  - [iOS Club - Markdown & Git](#ios-club---markdown--git)
- [附](#附)

## WWDC

〇 `WWDC`可以说是每年`Apple`发布新技术的盛会。作为开发者，我们不仅可以在其中找到`Apple`关于新技术的介绍，也可以看到很多`Apple`为初学者准备的教程。大家只需要在`Mac`或其他设备上下载`Developer.app`，就可以看到每年`WWDC`的全部内容。我们这次主要关注与`SwiftUI`相关的内容

〇 推荐大家先查看`WWDC20`的`Introduction to SwiftUI`，通过官方的`三明治App`的例子对`SwiftUI`有一个简单的了解。

✡ WWDC20 Introduction to SwiftUI <https://developer.apple.com/wwdc20/10119>

〇 在学习`Stanford课程`的过程中，可以参考下面两个`WWDC20`的session，对SwiftUI里面的`App Scene View`和`@State @ObservedObject`有更深入的了解，从而更好的管理自己的`App层次`和`App中的数据流动`。

✡ WWDC20 App essentials in SwiftUI <https://developer.apple.com/wwdc20/10037>

✡ WWDC20 Data Essentials in SwiftUI <https://developer.apple.com/wwdc20/10040>

〇 通过下面这几个session，你可以看到每年苹果对`Swift`和`SwiftUI`的更新。`2019`年是Swift大版本`Swift5.0`推出的第一年，也是`SwiftUI`元年，再往前的WWDC和Swift与SwiftUI关系不大。

注：`WWDC21`的内容，在今年秋季、各平台新系统发布才能正式运用。感兴趣的同学可以
提前了解，但请注意没有办法在这个暑假使用。

WWDC21 What's new in Swift <https://developer.apple.com/wwdc21/10192>

WWDC20 What's new in Swift <https://developer.apple.com/wwdc20/10170>

WWDC19 What's new in Swift <https://developer.apple.com/wwdc19/402>

WWDC21 What's new in SwiftUI <https://developer.apple.com/wwdc21/10018>

WWDC20 What's new in SwiftUI <https://developer.apple.com/wwdc20/10041>

点进去之后，看完这些视频，可能会发现这些视频下面都会有一些相关的推荐，大家感兴趣也可以对`WWDC`推出的新内容做进一步的了解。

〇 还有一些`WWDC19`的session，但这些视频已经**过时**，而且苹果在`WWDC20`上对这些视频进行了更新，也就是在上面列出来的那些；所以虽然`WWDC19`对于`Swift`和`SwiftUI`来说很重要，但我们现在只需要看新的session就好。

大家如果想感受一下`SwiftUI`刚刚发布的时候大家的热情，可以看：

WWDC19 Keynote <https://developer.apple.com/wwdc19/101> 的2h6min34s - 2h14min22s

还有下面的视频，前二十分钟对新推出的`SwiftUI`也有详细的介绍，感兴趣的同学也可以看一下：

WWDC19 Platforms State of the Union <https://developer.apple.com/wwdc19/103>

〇 另外，如果想跟进苹果最新发布的技术，每年`WWDC`的`Keynote`和`Platforms State of the Union`都可以关注一下，对设计和App开发感兴趣，每年的`Apple Design Awards`也可以进行关注；感兴趣的相关session也可以自己抽时间查看。

## Stanford CS193p - Developing Apps for iOS

英文课程 Swift SwiftUI App设计思维

课程网址：<https://cs193p.sites.stanford.edu>

课程视频（YouTube English）：<https://youtube.com/playlist?list=PLpGHT1n4-mAsxuRxVPv7kj4-dQYoC3VVu>

课程视频 中英字幕：<https://www.bilibili.com/video/BV1fy4y1u7hX>

课程清华云盘链接（包含 YouTube视频英文字幕 和 B站中英硬字幕搬运）：<https://cloud.tsinghua.edu.cn/d/bd289554fd0b4f9eb920/>

非常系统性的`Swift+SwiftUI`教程！老师已经开了很多年的iOS开发课程了。暑期我们希望大家能完成前六课的学习（六节课的内容还是蛮多的哦，希望大家认真对待），更希望大家看完前六课之后也继续学习后面的课程。希望这门课程能让你入门iOS开发！

### Basic

**Lecture 1 Getting Started with SwiftUI**

The first lecture jumps right into building the first application of the quarter: a card-matching game called Memorize.  It will be the foundation for the first few weeks of course material.

**Lecture 2 Learning More about SwiftUI**

Development on Memorize continues.  Creating reusable components (a Card in the game) and combining them to make more complex user-interfaces.

**Lecture 3 MVVM**

Conceptual overview of the architectural paradigm underlying the development of applications for iOS using SwiftUI (known as MVVM) and an explanation of a fundamental component of understanding the Swift programming language: its type system.  Then both of these are applied to the Memorize application started in the first two lectures.

**Lecture 4 More MVVM enum Optionals**

The MVVM architecture is fully applied to Memorize.  The important Swift concepts of enums and Optionals are covered and used to finish off the game logic of the Memorize game.

**Lecture 5 Properties Layout @ViewBuilder**

Explore property observers, computed properties, @State and @ViewBuilder.  The mechanisms behind how Views are layed out on screen are examined followed by a demo which chooses a better font for each card in Memorize depending on the space available.  Along the way, apply better access control to Memorize's internal API.

**Lecture 6 Protocols Shapes**

Discussion of what is perhaps the most important type in Swift: a protocol.  The demo combines the concepts of generics and protocols to make the cards better use the space available on screen.  Finally the Shape protocol is explained and the pie-shaped countdown timer is added to Memorize (but not yet animated).

### Advanced

Lecture 7 ViewModifier Animation

Lecture 8 Animation Demo

Lecture 9 EmojiArt Drag/Drop

Lecture 10 Gestures

Lecture 11 Persistence Error Handling

Lecture 12 Binding Sheet Navigation EditMode

Lecture 13 Publisher More Persistence

Lecture 14 Document Architecture

## 浙江大学 - Swift创新导论

中文课程 Swift语法 UIKit 项目实战

链接：<https://www.icourse163.org/course/ZJU-1450024180>

前三周课程清华云盘链接：<https://cloud.tsinghua.edu.cn/d/2ddcf31a51cf4a48b690/>

**前三周的教程**可以让没有编程经验的同学对`Swift`这门编程语言、**编程思维**和`iOS应用开发`有一个简单的了解。

后面的课程**并不推荐**大家学习，因为并没有使用Apple最新的SwiftUI框架进行教学；但是有一些很好的例子能够培养大家的创新思维，感兴趣的同学也可以看看后面几周中一些实际的案例。

### 第一周

第1讲：课程概述

第2讲：Swift浅析

第3讲：Swift编程基础知识

第4讲：移动应用设计流程

第5讲：iOS 人机交互基础

第6讲：iOS交互设计实践（一）

第7讲：iOS交互设计实践（二）

第8讲：常量、变量、函数

第9讲：数组与字典

第10讲：控制流（Control Flow）（一）

第11讲：控制流（Control Flow）（二）

### 第二周

第12讲：函数（Functions）和闭包（Closures）（一）

第13讲：函数（Functions）和闭包（Closures）（二）

第14讲：Playground 实践应用（一）

第15讲：Playground 实践应用（二）

第16讲：对象（Objects）和类（Classes）（一）

### 第三周

第17讲：对象（Objects）和类（Classes）（二）

第18讲：枚举（Enumeration）和结构（Structures）（一）

第19讲：枚举（Enumeration）和结构（Structures）（二）

第20讲：协议（Protocols）和拓展（Extensions）（一）

第21讲：协议（Protocols）和拓展（Extensions）（二）

第22讲：错误处理（Error handling）（一）

第23讲：错误处理（Error handling）（二）

## Aimls - Swift编程基础

中文教程 Swift语法

Swift5.0语法讲解 链接：<https://www.bilibili.com/video/BV144411C7Gg>

Swift5.1新特性 SwiftUI初步了解：<https://www.bilibili.com/video/BV1gJ411M72p>

全部课程知识点整理总结：<https://www.bilibili.com/video/BV1jE411y7cw>

教程云盘链接：<https://cloud.tsinghua.edu.cn/d/bba8530022af47de9e0b/>

学习Swift编程语法的教程。Stanford的教程中也会教你如何使用Swift，但其中主要是靠你自学，可能会有些累。**有编程基础的同学**可以二倍速观看上面的Swift教程，**对Swift有一个简单的理解**。为什么要用二倍速呢？只要学过一门编程语言，学习其他编程语言就会特别快。推荐大家在学习过程中**做好笔记**。

## designcode - SwiftUI iOS

英文教程 较高质量的付费教程 不做要求 想提升的同学可以看（教程看得越多学到的东西越多）

教程清华云盘链接：<https://cloud.tsinghua.edu.cn/d/65cd3bfc68844bd68356/>

[designcode.io](https://designcode.io)

* [designcode | SwiftUI 2 iOS14](https://designcode.io/swiftui-ios14)
    * [Bilibili搬运｜中文字幕](https://www.bilibili.com/video/BV1fT4y157zK)
* [designcode | SwiftUI iOS13 Part1](https://designcode.io/swiftui)
    * [Bilibili搬运｜中文字幕](https://www.bilibili.com/video/BV1X7411R73g)
* [designcode | SwiftUI iOS13 Part2](https://designcode.io/swiftui2)
    * [Bilibili搬运｜中文字幕](https://www.bilibili.com/video/BV1X7411R73g)
* [designcode | SwiftUI iOS13 Part3](https://designcode.io/swiftui3)
    * [Acfun搬运｜中文字幕](https://www.acfun.cn/v/ac15856717)

## iOS Club - Markdown & Git

大家在学习的过程中可以使用Markdown来整理笔记。社团之前有Markdown的培训，已经上传至B站，不了解Markdown的同学可以进行查看。[【教程】面向开发的Markdown学习](https://www.bilibili.com/video/BV1jV411j7mz)

在之后的开发过程中，一件重要的事情是团队成员间的代码协作，社团之前也有过版本控制工具Git的相关培训，以后打算进行团队开发、还不了解版本控制的同学可以进行查看。[【教程】Git基础与进阶](https://www.bilibili.com/video/BV1eh411v7gt)

# 附

全部课程的清华云盘链接：<https://cloud.tsinghua.edu.cn/d/01f70b980e8946c3a8b7/>