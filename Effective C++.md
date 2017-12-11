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
