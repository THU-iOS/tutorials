

## Stanford CS193p L1-L6 观前引导


### Lecture1 Getting started with SwiftUI

> 介绍Xcode、SwiftUI的最基础界面编写。

#### 重点：

- 弄清楚下列代码中每个关键字的含义与作用

  ``` swift
  import SwiftUI
  
  struct ContentView: View {
      var body: some View {
          Text("Hello, world!")
              .padding()
      }
  }
  
  struct ContentView_Previews: PreviewProvider {
      static var previews: some View {
          ContentView()
      }
  }
  ```

- 弄清楚文件界面中每个文件的作用

#### 作业：

1.为什么要body的类型为some View？

答案：因为body得到的可能不是严格的View类型。

2.使用SwiftUI编写App时，整个程序的入口是哪个文件(类似于C中main函数)？

答案：文件名为：``` AppName+App.swift```

代码为

``` swift
import SwiftUI

@main
struct lecture1App: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

### Lecture2 Learning more about SwiftUI

> 本节课将更进一步地介绍一些SwiftUI的设计模式，包括View、ZStack等组件的互相嵌套，还讲了数组、Foreach、按钮的用法。

#### 重点：

##### 函数相关

- 函数的最后一个参量可写在括号外：

  ``` swift
  Button(action: {
    
  },label:{Text("s")})
  
  Button(action: {}) {
    Text("s")
  }
  ```

  两者等价，这在实际使用时会更加简洁。

##### 界面相关

- LazyGrid的用法
- ScrollView的用法

##### Spcaer()

- 一种设计样式，能尽可能的扩充空间

##### @State

- 变量修饰符，能在该值改变时同步对页面进行更新

#### 作业：

照着课上的代码自己写一遍，做一些修改，最好能写到手机上体验一下

### Lecture3 MVVM and the swift type system

> 本节课介绍在SwiftUI设计理念中极为重要的MVVM(Model-View-ViewModel)模式，同时介绍除VIew界面外，其他两个界面：Model，ViewModel的写法。

#### 重点：

##### MVVM设计范例

- Model->ViewModel->View，有点类似于C++设计中，底层+界面控制+界面的逻辑。

##### ```struct```与```class```的区别与联系

- 前者是面向过程的结构体，后者是面向对象的结构体
- 其他区别见课程

#### 作业：

1. 跟着老师把代码敲一遍，理清MVVM之间的关系。

2. View界面是面向过程的还是面向对象的？

   答：面向过程。

### Lecture 4 More MVVM enum Optionals

> 在这一讲中， 前面提到的 MVVM 模型将被完整地应用到游戏 Memorize 的编写中。enums 和 Optionals 这两个 Swift 编程中的关键概念将被介绍并用于完善游戏 Memorize 的逻辑部分。

##### enum

* Another variety of data structure in addition to `struct` and `class`

* Associated Data

* Setting the value of an enum

* Checking an enum's state

* `break` statement & `default` statement

* Methods yes, (stored) Properties no

* Getting all the cases of an enumeration

##### Optionals

* An Optimal is just an enum

* We use Optional at any time we have a value that can sometimes be 'not set' or 'unspecified' or 'undetermined'

#### Lecture 5 Properties Layout @ViewBuilder

> 在这一讲中，将介绍 property observers，computed properties，@State 和 @ViewBuilder。我们也将继续完善游戏 Memorize，并通过一个在给定空间中为卡片选取合适字体大小的例子揭示 Views 在屏幕上的布局方式的背后机制。在这一过程中，我们对游戏 Memorize 内部 API 实现了更好的访问控制。

##### Swift Demo Warmup

* Access Control

##### @ViewBuilder

* What exactly is that argument to `ZStack`, `Foreach`, `GeometryReader`, etc?

##### Shape

* What if I want to draw my own View rather than constract it from other Views?

##### Animation

* Mobile app UIs look pretty bad without animation.

* Luckily, in SwiftUI, animation (almost) comes for free!

##### ViewModifier

* What exactly are functions like `foregroundColor`, `font`, `padding`, etc. doing?

#### Lecture 6 Protocols Shapes

> 在这一讲中，我们将讨论 Swift 编程中最重要的类型 —— protocol。为了使游戏 Memorize 中的卡片可以更好地使用屏幕上的给定空间，我们将结合使用 generic 和 protocol 两种概念。最后，我们使用名为 Shape 的 protocol 将一个饼状计时器加到游戏 Memorize 中。

##### Property Observers

* "Watching" a var and reacting to changes

##### @State

* State that is entirely localized inside a View

* Only used for temporary state like presentation of alerts or editing things or animation

##### Animation

* Implicit vs. Explicit Animation

* Animation Views (via their ViewModifiers which can implement the Animatable protocol)

* Transitions (animating the appearance/dissppearance of Views by specifying ViewModifiers)

* Animating Shapes (via the Animatable protocol)

