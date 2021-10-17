## Swift教学

> 2021.10.17
>
> 王可

[TOC]

### 简单介绍

- 苹果公司于2014年在[苹果开发者年会](https://zh.wikipedia.org/wiki/WWDC)（WWDC）发布了Swift编程语言。经过7年的发展，swift日趋成熟，同时作为苹果目前主推的编程语言（之前是Object-C），官方和社区提供的库也十分丰富。

- swift兼具了许多现代编程语言的优点，容易编写且易于阅读和维护，学习起来很容易上手。

### 基础

#### 常量与变量、强类型、类型推断

```var```和```let```

```swift
let a = 1
a = 5
var b = 4 //编译器会自动推断为Int类型
b = 4.5 //如果强行赋值Double\Float类型会报错
```

#### 可选类型

```swift
var x = "321"
let y = Int(x)
print(y)
print(y!)
```

#### 元组(tuples)

```swift
let tuple = ("hello", "world",2021)
print(tuple.1)
print(tuple.2)
print(tuple.3)
let (string1, string2, int1) = tuple
print("\(string1) \(string2) \(int1)")
```

#### 区间运算符

##### 闭区间

```swift
for i in 1...5 {
  print(i)
}
```

##### 半开区间

```swift
for i in 1..<5 {
  print(i)
}
```

#### 集合类型

- 数组

  - 和```python``` 的```list```类似

  ```swift
  a = [1,2,3,4,5,"str"]
  for i in a {
    print(i)
  }
  
  print(a.contains(6))
  a.append(6)
  print(a.contains(6))
  
  for i in a[1...] {
    print(i)
  }
  ```

- 集合

  - 储存同种元素
  - 每个哈希值相同的元素只出现一次
  - 无顺序

  ```swift
  var set: Set<Int> = [1,2,3,4]
  for i in set {
      print(i)
  }
  set.insert(4.5)
  ```

- 字典:

  - 使用键来访问数据

  ```swift
  var int2str: [Int: String] = [1: "Joker", 2: "Queen", 3: "King"]
  print(int2str[1])
  
  for (int,str) in int2str {
    print("\(int):\(str)")
  }
  ```

### 函数与闭包

#### 函数

```swift
func greet(person: String) -> String {
  return "Hello " + person + "!"
}

print(greet(person: "Swift"))
```

```swift```函数又一个很符合自然语言的特性，变量在函数内和函数外可以有两个名字，这比较符合英语介词的使用习惯。

```swift
func greet(with person: String) -> String {
  return "Hello " + person + "!"
}

print(greet(with: "Swift"))
```

使用元组承载多重返回值

```swift
func firstLast(of array: [Int]) -> (first: Int, last: Int) {
    return (array[0], array.last!)
}

var a = [1,2,3,4,5]

let (f, l) = firstLast(of: a)
print("\(f),\(l)")

```

#### 闭包

```闭包```是自包含的函数代码块，可以在代码中被传递和使用。Swift 中的闭包与 C 和 Objective-C 中的代码块（blocks）以及其他一些编程语言中的匿名函数（Lambdas）比较相似。

```swift
var numbers = [2,1,4,3]

var sortedNumber = numbers.sorted(by: { (s1: Int, s2: Int) -> Bool in return s1 < s2})

for i in sortedNumber {
    print(i)
}
```

属于非初级的内容，有兴趣可以深入研究。

### 类和结构体

类和结构体有许多相同之处，比如都定义属性、方法和协议等，它们的主要区别在于类有继承和引用计数等。

```swift
struct Student {
    public var name: String
    public var sex: String
    private let ID: UUID
    
    init() {
        self.name = "Joker"
        self.sex = "Man"
        self.ID = UUID.init()
    }
    
    init(name: String, sex: String) {
        self.name = name
        self.sex = sex
        self.ID = UUID.init()
    }
    
    func getName() -> String {
      return self.name
    }
    
    func getID() -> UUID {
      return self.ID
    }
}

var joker = Student()
var queen = Student(name: "Queen", sex: "Woman")

print("\(joker.name) + \(joker.sex) + \(joker.getID())")
print("\(queen.name) + \(queen.sex) + \(queen.getID())")
 
```

```swift
class School {
    var name: String
    var address: String
    init(name: String, address: String) {
        self.name = name
        self.address = address
    }
}

class University: School {
    var QSRanking: Int
    init(name: String, address: String, QSRanking:Int) {
        self.QSRanking = QSRanking
        super.init(name: name, address: address)
    }
    
    
}

var THU = University(name: "Tsinghua", address: "Beijing Haidian", QSRanking: 17)

print("\(THU.name) + \(THU.address) + \(THU.QSRanking)")
```

### 授人以渔

- 推荐学习网站：https://swiftgg.gitbook.io/swift/

- 如果你想开始学习开发App，推荐使用b站（Youtube）搜索CS193p开始学习。

  [b站CS193p](https://www.bilibili.com/video/BV19N411Z7Qx?from=search&seid=12181501869049735587&spm_id_from=333.337.0.0)

  [ YouTube CS193p](https://www.youtube.com/watch?v=bqu6BquVi2M&list=PLpGHT1n4-mAsxuRxVPv7kj4-dQYoC3VVu&ab_channel=Stanford)

- THU iOS Club的教程仓库：https://thu-ios.github.io/tutorials

- 本次为大家准备了作业在：[Swift homework - Tutorial (thu-ios.github.io)](https://thu-ios.github.io/tutorials/lecture/swift-hw.html#统计各个专业的人数)