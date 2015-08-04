<h1 style="padding-top:150px" class="text-center">The Scala</h1>
<p class="text-center"><strong>Andy Ai</strong></p>

---

# 目标

- 认识 Scala
- Scala 基础
- 运行一个简单程序

---

# Scala 是什么

- A Scalable language
- Object Oriented
- Functional
- Seamless Java Interop
- Functions are Objects

---

# 为什么选择 Scala

- 表达能力
  - 函数是一等公民
  - 闭包
- 类型推断
- 模式匹配
- Java 互操作性
  - 可重用 Java 库 / 工具
  - 没有性能惩罚

---

# 如何工作

## Scala ---编译---> Java 字节码(.class) ---JVM---> 运行

---

# 表达式和值

- 表达式

```scala
1 to 2
```

- 不可变量(常量)

```scala
val two = 1 + 1
```

- 变量

```scala
var name = "Jobs"

name = "Andy"
```

---

# 函数是一等公民

- 定义函数

```scala
def addOne(n: Int) = n + 1

def addOne(n: Int): Int = {
  n + 1
}
```

- 调用函数

```scala
addOne(1)
```

- 将函数作为参数传递

```scala
def addOne(func: Int => Int, n: Int) = func(n) + 1

addOne((a: Int) => a + 1, 2)

val list = List(1, 2, 3)

list.reduce(_ + _)
```

- 在函数里返回函数

```scala
def add(n: Int) = (a: Int) => a + n

add(10)(1)
```

- 按名称传递参数

```scala
val debug = false

def log(msg: => String) = {
  if(debug){
    println(msg)
  }
}

log("excption" + 1 / 0)
```

---

# 类

```scala
class Person {
  def sayHi() = println("Hi")
}

val person = new Person

person.sayHi
```

---

# 单例对象

```scala
object Math {
  def plus(m: Int, n: Int) = m + n
}

Math.plus(2, 3)
```

---

# 模式匹配

```scala
def level(num: Int): String = num match {
  case n if n > 0 && n < 10 => "Small"
  case n if n > 100 && n < 1000 => "Middle"
  case n if n > 1000 => "Big"
  case _ => "Balala"
}

println(level(500)) //Middle
```

---

# 与 Java 集成

```scala
import java.util.UUID

UUID.randomUUID.toString
```

---

# 脚本化运行

```
#!/bin/sh
exec scala "$0" "$@"
!#
object HelloWorld extends App {
  println("Hello, world!")
}
HelloWorld.main(args)
```

```
./script.sh
```

---

# 学习资源

- [http://zh.scala-tour.com/](http://zh.scala-tour.com/)
- [https://twitter.github.io/scala_school/zh_cn/index.html](https://twitter.github.io/scala_school/zh_cn/index.html)

---

<h1 style="padding-top:150px" class="text-center">Thanks</h1>

<div class="text-center">
  <img style="width:400px; height:400px" src="http://api.qrserver.com/v1/create-qr-code/?color=000000&amp;bgcolor=FFFFFF&amp;data=http%3A%2F%2Fweibo.com%2Faiyboo&amp;qzone=1&amp;margin=0&amp;size=400x400&amp;ecc=L" alt="qr code" />
<div>