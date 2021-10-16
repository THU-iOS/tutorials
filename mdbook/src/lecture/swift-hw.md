# Swift教学课后作业

> 2021.10.17
>
> 作业：[杨希杰](https://github.com/Yang-Xijie)

- [Swift教学课后作业](#swift教学课后作业)
  - [作业提交方式](#作业提交方式)
  - [基础](#基础)
    - [查文档](#查文档)
    - [强类型](#强类型)
    - [可选类型](#可选类型)
    - [函数](#函数)
    - [统计各个专业的人数](#统计各个专业的人数)
  - [进阶](#进阶)
    - [Error Handling](#error-handling)
    - [Log()](#log)
  - [其他](#其他)

## 作业提交方式

* 基础部分为基本要求，进阶部分可自选；题目前有`Optional`也是选做。
* 复制下面对应部分的作业，在括号或空白处中**填空**。
* 提交作业需要将填好空的所有文本（包括题目）以**邮件正文**的形式发送到`564197835@qq.com`，邮件标题为`Swift作业 <姓名> <学号>`。

## 基础

### 查文档

〇 Swift官网的网址是（）。我们一般会在官网上查找Swift的文档，即Language Guide，网址为（）。

〇 在Xcode中打开开发者文档的方法是：在菜单栏（）中点击（），或使用快捷键（）。

### 强类型

观察下面的代码：（提示：观察不出来可以实际运行）

```swift
let a = 1
a = 5
var b = 4
b = 4.5
```

〇 代码第二行报错的原因是（）。

〇 代码第四行报错的原因是（）。

### 可选类型

〇 如果变量`a`是一个可选类型，我们可以通过方式（）实现：如果其不为空，则取出真实值赋给`b`；若其为空，则令`b`为`0`：

A. `let b = a!`

B. `let b = (a != nil) ? a : 0`

C. `if let b = a { ... } else { let b = 0  ... }`

D. `if a != nil { b = a!  ... } else { b = 0  ... }`

### 函数

〇 一个函数可以通过（）返回多个参数。

〇 编写程序，计算10的阶乘并输出结果。要求：使用`...`运算符。【循环 区间生成运算符】
（

）

〇 回顾函数闭包的相关知识，补全下列代码：

```swift
let fruits: [String] = ["apple", "orange", "pear", "pineapple"]
// 希望打印出 ["pineapple", "orange", "apple", "pear"]
// 即Array中的所有字符串按照长度从大到小排序

// TODO
```

提示：

阅读函数`sorted(by:)`的[文档](https://developer.apple.com/documentation/swift/sequence/2907222-sorted)（`func sorted(by areInIncreasingOrder: (Self.Element, Self.Element) -> Bool) -> [Self.Element]`）

如果你想直接在大括号中写函数的话，`$0`和`$1`可以分别指代第1个和第2个参数。

### 统计各个专业的人数

```swift
import Foundation

enum Major {
    case A
    case B
    case C
    case D
}

struct Student {
    var name: String
    var major: Major
}

let studentList: [Student] = [
    Student(name: "Alice", major: .A),
    Student(name: "Bob", major: .B),
    Student(name: "Carl", major: .C),
    Student(name: "David", major: .D),
    Student(name: "Eric", major: .A),
    Student(name: "Fred", major: .D),
    Student(name: "Gavin", major: .C),
    Student(name: "Henry", major: .D),
    Student(name: "Ivy", major: .B),
    Student(name: "Janet", major: .D),
    Student(name: "Kathy", major: .A)
]

// 题目：
// 统计studentList中各个专业的同学名字和总数目，并按照你倾向的方式打印。

// TODO
```

## 进阶

### Error Handling

执行如下程序，结果为（

）（共两行），简要解释输出结果：（）。

```swift
import Foundation

struct Printer {
    var paper: Int // 0 - 400
    var ink: Float // 0 - 100 percentage
    let inkPerPage: Float = 0.1

    enum error: Error {
        case outOfPaper
        case noInk
    }
}

struct File {
    var name: String
    var page: Int
}

func printFile(_ file: File, with printer: inout Printer) throws {
    if printer.paper <= file.page {
        throw Printer.error.outOfPaper
    } else if printer.ink <= Float(file.page) * printer.inkPerPage {
        throw Printer.error.noInk
    } else {
        printer.paper -= file.page
        printer.ink -= Float(file.page) * printer.inkPerPage
        print("File \"\(file.name)\" was successfully printed! (paper: \(printer.paper), ink: \(String(format: "%2.1f", printer.ink))%)")
    }
}

var myHomework = File(name: "my homework", page: 4)
var myReport = File(name: "my report", page: 5)
var myPrinter = Printer(paper: 7, ink: 80)
do {
    try printFile(myHomework, with: &myPrinter)
    try printFile(myReport, with: &myPrinter)
} catch {
    print(error)
}
```

### Log()

新建`Project - macOS - Command Line Tool`，复制运行如下代码：

```swift
import Foundation // 1

struct Log: CustomStringConvertible { // 3
    public var time: String // 4
    public var log: String // 5

    init(filePath: String = #file, line: Int = #line, column: Int = #column, funcName: String = #function) { // 7
        let fileName = (filePath as NSString).lastPathComponent // 8

        let formatter = DateFormatter() // 10
        formatter.dateStyle = .none // 11
        formatter.timeStyle = .medium // 12
        time = formatter.string(from: Date()) // 13

        log = "\(fileName)(\(line),\(column)) \(funcName)" // 15
    }

    public var description: String { // 18
        return "[\(time) \(log)]\n\t" // 19
    }

    public var string: String { // 22
        description // 23
    } // 24

    public var error: String { // 26
        "[ERROR] " + description // 27
    }
}

func MyPrint() { // 31
    print(Log().string + "Hello, world!") // 32
    print(Log().error + "Bye, world.") // 33
}

MyPrint() // 36

// Literal        Type     Value
//
// #file          String   The name of the file in which it appears.
// #line          Int      The line number on which it appears.
// #column        Int      The column number in which it begins.
// #function      String   The name of the declaration in which it appears.
```

〇 该程序的运行结果是（

）。

〇 第3行新建了一个结构体名为Log，后面冒号跟着的`CustomStringConvertible`是（），在结构体内部的变量（）完成了`CustomStringConvertible`。

〇 （Optional）可以去掉第4行的`public`关键字吗？（）

〇 第7行中，`filePath: String = #file`中`filePath`是参数名称，冒号后面的`String`是这个参数的（），`=`后面跟的是这个参数的（）。

〇 （Optional）第8行中，`(filePath as NSString)`是在做（）。

〇 第12行中出现了`.medium`，它们是（）的一种。

〇（Optional）第12行如果要补全`.`前面的内容可以添加（）。提示：查看`.medium`的文档。

〇 第13行中的`formatter.string(from: )`，这里string是一个（），看到`from`这一个介词可以推测`from`是参数的（）。

〇 第19行的`\n`和`\t`是（）字符。

〇 第22行定义了变量string，我们将其称作（计算属性）。将22 23 24这三行代码补充完整：（

）。

〇 第32行的`Log()`（）了一个结构体实例。

〇 第32行的`+`表示（）。

〇 第36行调用了函数`MyPrint`，该函数有（）个参数，（）个返回值。

〇 （Optional）尝试如下步骤在`Xcode`中添加`code snippet`：

To create a `code snippet`:
1. Select: print(Log().string + "<\hashinfo\hash>")
2. Go to `Xcode -> Editor -> Create Code Snippet`.
3. Change `\hash` to `#`.
4. Set title as `Log()` and `completion` as `print`.

Try typing `print` and select the code snippet.

## 其他

〇 （Optional）如果我们想导入并使用一个开源的第三方`Swift Package`，需要点击`Xcode`菜单栏（）（写出层级关系），然后添加该`Swift Package`的地址。之后在需要用到该包的代码文件最开始写上`import`语句就可以了。

〇 `Swift`有一个非常好用的格式化工具[GitHub | SwiftFormat](https://github.com/nicklockwood/SwiftFormat)，阅读其README说明，在自己的Xcode中添加该格式化工具并尝试使用。你在你的`Mac`上安装了吗？（）（安装了/还没/下次一定）。

〇 （Optional）`Swift`目前的最新版本是`5.5`，这一个版本引入的一个重要更新是Concurrency WWDC链接[WWDC21 | Meet async/await in Swift](https://developer.apple.com/wwdc21/10132)，感兴趣的同学可以自行查看。

〇 （Optional）如果你还没有学习过Git，可以花时间掌握一下这个合作开发的必备工具。社团往期培训课程传送门 [Git基础与进阶](https://www.bilibili.com/video/BV1eh411v7gt)
