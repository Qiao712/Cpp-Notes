#### 多文件const
默认状态下，const对象仅在文件内有效。多个文件中出现了同名的const变量时，其实等同于在不同文件中分别定义了独立的变量。  
* 共享const变量：不管是声明还是定义都添加extern关键字，这样只需定义一次

### 指向常量的指针（pointer to const）底层const
```
const int ci = 0;
const int *p = &ci;
```
&emsp;存放常量的地址只能用指向常量的指针。指向常量的指针可以指向一个*非常量对象*，但不能通过其更改其指向的非常量对象。（没有规定被指向的常量对象不能通过其他途径更改。）
### 常量指针（const pointer）顶层const
```
int i;
int* const cp = &i;
```
可以通过常量指针更改对象。

#### constexpr
将变量声明为constexpr以便由编译器检查是不是一个常量表达式。 
constexpr变量必须由**常量表达式(const expression)**或**constexpr**函数初始化。  
只有“字面值类型”（literal type）：算数类型、指针、引用，可以被声明为constexpr
#### const对象的初始值不一定在编译时被确定，constexpr变量的值必须在编译时确定。