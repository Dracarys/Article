## 编程小记

### 声明中的后缀 “_t”
C语言允许用户使用 `typedef` 关键字来定义自己习惯的数据类型名称，来替代系统默认的基本类型名称、数组类型名称、指针类型名称与用户自定义的结构型名称、共用型名称、枚举型名称等。一旦用户在程序中定义了自己的数据类型名称，就可以在该程序中用自己的数据类型名称来定义变量的类型、数组的类型、指针变量的类型与函数的类型等.

之所以这样做，是因为语言是讲究语境的，通过 `typedef` 给一个固有类型定义一个更符合当前语境的名字，使人在阅读时更容易理解作者的意图。而在进行定义时为了表明这是一个固有类型的“别名”，通常会在名字后面加上一个“_t”，以此表明它是 `typedef` 得来的，从而跟真正的自定义类型区分开。