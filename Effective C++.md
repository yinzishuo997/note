# Effective C++
## chp1
### item 01 : View C++ as a federation of languages

#### multiparadigm programming language

* procedural
* object-oriented
* functional
* generic
* metaprogramming

#### federation

* C
* Object-Oriented C++
* Template C++
* STL

### item 02 : Prefer consts, enums, and inlines to #define

* 如果你不想别人获得一个 pointer 或 reference 指向你的某个整数常量, eunum 可以帮助你实现这个约束.
* 宏看起来像函数, 但不会导致函数调用 (function call) 带来的额外开销.

#### remember
* 对于单纯常量, 最好以 const 对象或 enums 替换 #defines.
* 对于形似函数的宏, 最好用 inline 函数替换 #defines.

### item 03 : Use const whenever possible.

* 如果函数的返回类型是个内置类型, 那么改动函数返回值从来就不合法.
* mutable
* casting away constness
* const 成员函数调用 non-const 成员函数是一种错误.

### item 04 : Make sure that objects are initialized before they're uesd

* 如果成员变量是 const 或 reference, 它们就一定需要初值, 不能被赋值.
* 将每个 non-local static 对象搬到自己的专属函数内(该对象在次函数内被声明为 static).

##chp2 

### item 05 : Know what functions C++ silently writes and calls.

* 成员有 reference 或 const \ base classes 将 copy assignment 操作符声明为private, 编译器拒绝为其 derived classes 生成一个 copy assignment 操作符.

### imten 06 : Explicitly disallow the use of compiler-generated functions you do not want

* 并非所有 base classes 的设计目的都是为了多态用途.