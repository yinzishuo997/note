## chp1 Object Lessons

### Layout Costs for Adding Encapsulation

* c++ 在布局以及存取时间上住哟啊的额外负担是由 virtual 引起的 :
    * virtual function
    * virtual base class


### Adding Polymorphism

* 一个 pointer 或一个 reference 之所以支持多态, 是以为它们并不引发内存中任何 "与类型有关的内存委托操作 (type-dependent commitment)"; 会受到改变的, 只有它们所指的内存的 "大小和内容解释方式" 而已.


## chp2 The Sematics of Constructors

### nontrivial default constructor

* 带有 default constructor 的 member class object
* 带有 default constructor 的 base class
* 带有 virtual function 的 class
* 带有一个 virtual base class 的 class

### copy constructor

* 决定一个 copy constructor 是否为 trivial 的标准在于 class 是否展现出所谓的 bitwise copy sematics

### class 不展现出 bitwise copy semantics

* 当 class 内含一个 member object 而后者的 class 声明有一个 copy constructor (不论是被 class 设计者显示声明, 或是被编译器合成)
* 当 class 继承一个 base class 而后者存在一个 copy consturctor 时
* 当 class 声明了一个或多个 virtual functions 时
* 当 class 派生自一个继承串链, 其中有一个或多个 virtual base classes






## chp4 The Semantics of Function

### Static Member Function

#### static member funtions 特性

* 没有 this 指针 (主要特性)
* 不能够直接存取 class 中的 nonstatic members
* 不能够被声明为 const, volatile, 或 virtual
* 它不需要经过 class object 才能被调用