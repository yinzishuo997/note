### 派生类向基类转换的可访问性

* 只有当 D 共有地继承 B 时, ``用户代码``才能使用派生类向基类的转换;
* 不论 D 以什么方式继承 B, D 的``成员函数和友元``都能使用派生类向基类的转换;派生类向基类的类型转换对于派生类的成员和友元来说永远都是可访问的;
* 如果 D 继承 B 的方式是公有的或者受保护的,则 D 的派生类的成员和友元可以使用 D 向 B 的类型转换; 反之, 如果 D 继承 B 的方式是私有的,则不能使用

tip : 对于代码中的某个节点来说, 如果基类的共有成员是可访问的, 则派生类向基类的类型转换也是可访问的; 反之则不行.

### 友元和继承

* 就像友元不能传递一样, 友元关系同样不能继承.
* 友元可访问性包括了``Base``对象内嵌在其派生类对象中的情况.
* 当一个类将另一个类声明为友元时, 这种友元关系只对做出声明的类有效. 对于原来那个类来说, 其友元的基类或者派生类不具有特殊的访问能力.

### Exercise 15.19:
> Assume that each of the classes from page 612 and page 613 has a member function of the form:

> `void memfcn(Base &b) { b = *this; }`

> For each class, determine whether this function would be legal.

Member functions and friends of D can use the conversion to B regardless of how D inherits from B. The derived-to-base conversion to a direct base class is always accessible to members and friends of a derived class.

Hence, the 3 below are all legal:

* Pub_Derv
* Priv_Derv
* Prot_Derv

Member functions and friends of classes derived from D may use the derived-to-base conversion if D inherits from B using either public or protected. Such code may not use the conversion if D inherits privately from B.Hence:

* Derived_from_Public **legal**
* Derived_from_Private **illegal**
* Derived_from_Protected **legal**

### 继承中的类作用域

* 一个对象, 引用或指针的``静态类型``决定了该对象的哪些成员是可见的.

### 名字查找先于类型查找

* 不会重载, 派生类在其作用域内隐藏基类成员 (即使形参列表不一样).

### 派生类中删除的拷贝控制与基类的关系

* 如果基类的默认构造函数, 拷贝构造函数, 拷贝赋值运算符或析构函数是被删除的函数或者不可访问, 则派生类中对应的成员将是被删除的.
* 如果在基类中有一个不可访问或删除的析构函数, 则派生类中合成的默认和拷贝构造函数将是被删除的.
* 和过去一样, 编译器将不会合成一个删除掉的移动操作.

### 继承构造函数的特点

* 和普通的 using 声明不一样, 一个构造函数的 using 声明不会改变构造函数的访问级别.
* 一个 using 声明语句不能指定 explicit 或 constexpr. 如果基类的构造函数是 explicit 或者 constexpr, 则继承的构造函数也有相同的属性.
* 当一个基类的构造函数含有默认实参时, 这些实参并不会被继承. 相反, 派生类将获得多个继承的构造函数, 其中每个构造函数分别省略掉一个含有默认实参的形参.
* 如果派生类定义的构造函数与基类的构造函数具有相同的参数列表, 则该构造函数将不会被继承.
* 默认, 拷贝, 移动构造函数不会被继承.