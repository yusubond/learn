

## CPP复习

C++对字符（char）使用单引号，对字符串（string）使用双引号。



## const关键字

如果const出现在星号左边，表示被指物是常量；如果出现在星号右边，表示指针自身是常量。

如果出现在星号的两边，表示被指物和指针都是常量



### 指针

如果结构标识符是结构名，则使用句点运算符；如果标识符是指向结构的指针，则使用箭头运算符。

```c++
struct person {
  string name;
  int    age;
};
person man = {"subond", 18};
person *woman = new person;
man.age;
woman->age;
```

## &引用

```c++
int main() {
    int val1 = 7, val2 = 999;
    std::cout << val1 << ", " << val2 << std::endl;
    int &rf1 = val1, &rf2 = val2;
    std::cout << &rf1 << ", " << rf2 << std::endl;
    int *p1 = &val1;
    std::cout << p1 << std::endl;
    rf1 = 100;
    std::cout << rf1 << ", " << rf2 << std::endl;
    rf1 = rf2;
    std::cout << rf1 << ", " << rf2 << std::endl;
    return 0;
}
// 如果将int &rf1 = val1;改为const int& rf1 = val1;
// 则 rf1= 100会报错，因为rf1为const, 不能被修改。
```

## static



![image-20210806124651124](/Users/subond/Library/Application Support/typora-user-images/image-20210806124651124.png)

## 好代码片段

#### member initialization list

![image-20210805131645810](/Users/subond/Library/Application Support/typora-user-images/image-20210805131645810.png)

**构造函数初始化成员**。



