# <a name="_hlk179466321"></a>**第五章 C++中的类和面向对象编程**

## **5.1 引言**

### **5.1.1 什么是面向对象编程（OOP）？**

面向对象编程是一种程序设计范式，它将程序视为对象的集合。每个对象都可以包含数据和操作这些数据的方法，从而使程序结构更接近现实世界。

### **5.1.2 OOP的四大基本特征**

- **封装**：将数据和方法封装在一起，限制外部访问，增强数据安全性。
- **继承**：允许一个类从另一个类派生，复用代码并扩展功能。
- **多态**：同一操作作用于不同对象时，表现出不同的行为。
- **抽象**：只关注对象的必要特征，忽略不相关的细节。

### **5.1.3 OOP的优势**

- **可重用性**：通过继承，可以重用已有的代码，减少重复劳动。
- **可维护性**：清晰的结构使得代码更易于理解和维护。
- **灵活性**：通过多态性，可以根据需要动态改变对象的行为。

### **5.1.4 类的基本概念**

- **类**：是对象的蓝图或模板，定义了对象的属性（数据）和行为（方法）。
- **对象**：是类的实例，代表实际存在的事物。

### **5.1.5 示例：简单的“学生”类**
```
#include <iostream>  
#include <string>  // 添加此行以支持 std::string  

class Student {  
public:  
    std::string name;  
    int age;  

    void introduce() {  
        std::cout << "Hello, I'm " << name << " and I'm " << age << " years old." << std::endl;  
    }  
};  

int main() {  
    Student student;  
    student.name = "Alice";  
    student.age = 20;  
    student.introduce();  
    return 0;  
}
```
## **5.2 类和面向对象编程**

### **5.2.1 定义类和对象**

- **类**：可以看作是一个模板，定义了某一类事物的共同特征和行为。比如，一个“汽车”类可以定义所有汽车的属性（如颜色、品牌、速度）和行为（如启动、刹车、加速）。
- **对象**：是类的实例，表示具体的事物。比如，你可以用“我的车”来表示“汽车”类的一个具体对象。

### **5.2.2 类的基本结构**

一个类通常由以下几个部分组成：

- **成员变量**：描述对象的特征（属性）。
- **成员函数**：描述对象的行为（方法）。

### **5.2.3 示例：创建一个“汽车”类**
```
#include <iostream>   

class Car 
{  
public:  
    // 成员变量  
    std::string brand;  
    std::string color;  
    int speed;  

    // 成员函数：启动汽车  
    void start() 
    {  
        std::cout << "The " << color << " " << brand << " is starting." << std::endl;  
    }  

    // 成员函数：加速  
    void accelerate(int increase) 
    {  
        speed += increase;  
        std::cout << "The " << brand << " accelerates to " << speed << " km/h." << std::endl;  
    }  
};  

int main() 
{  
    Car myCar;  // 创建一个Car类的对象  
    myCar.brand = "Toyota";  // 设置属性  
    myCar.color = "red";  
    myCar.speed = 0;  
    myCar.start();  // 调用成员函数  
    myCar.accelerate(50);  // 加速  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，Car类定义了三个成员变量：brand（品牌）、color（颜色）和speed（速度）。
- start和accelerate是这个类的成员函数，分别用于启动汽车和加速。

### **5.2.4 如何使用类**

- **创建对象**：使用类的构造函数创建对象（如 Car myCar;）。
- **访问成员**：通过点运算符（.）访问对象的属性和方法（如 myCar.start();）。

### **5.2.5 类的作用**

- **组织代码**：类将相关的数据和操作组合在一起，使代码更清晰易懂。
- **提高可重用性**：可以创建多个对象而不需要重复代码，例如，可以创建多个汽车对象，每个对象都有不同的属性。

## **5.3 类的继承**

### **5.3.1 继承和聚合**

- **继承**：允许一个类（派生类）从另一个类（基类）获取属性和方法。这样，派生类可以复用基类的代码，同时可以添加或修改自己的特性。
- **聚合**：表示一种“拥有”的关系，一个类可以包含另一个类的对象，但并不是通过继承关系。

### **5.3.2 继承的基本语法**

DerivedClass 是派生类，BaseClass 是基类，使用 public 表示公共继承。
```
class DerivedClass : public BaseClass
{
// 派生类的内容
};
```
## **5.3.3 示例：创建一个“动物”类和派生类“狗”**
```
#include <iostream>  

class Animal {  // 基类  
public:  
    void eat() {  
        std::cout << "This animal is eating." << std::endl;  
    }  
};  

class Dog : public Animal {  // 派生类  
public:  
    void bark() {  
        std::cout << "The dog barks." << std::endl;  
    }  
};  

int main() {  
    Dog myDog;  // 创建Dog类的对象  
    myDog.eat();  // 调用基类的方法  
    myDog.bark();  // 调用派生类的方法  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，Animal 是基类，定义了一个 eat 方法。
- Dog 是派生类，继承了 Animal 的所有特性，并增加了一个 bark 方法。

### **5.3.4 使用继承的好处**

- **代码复用**：可以在多个派生类中共享基类的代码，减少重复。
- **逻辑清晰**：通过继承，可以建立类之间的层次结构，使代码结构更加清晰。

### **5.3.5 示例：创建一个“交通工具”类和派生类“汽车”和“自行车”**
```
#include <iostream>  

class Vehicle 
{  // 基类  
public:  
    void start() 
    {  
        std::cout << "The vehicle is starting." << std::endl;  
    }  
};  

class Car : public Vehicle {  // 派生类  
public:  
    void honk() 
    {  
        std::cout << "The car honks." << std::endl;  
    }  
};  

class Bicycle : public Vehicle {  // 另一个派生类  
public:  
    void ringBell() 
    {  
        std::cout << "The bicycle rings its bell." << std::endl;  
    }  
};  

int main() 
{  
    Car myCar;  
    myCar.start();  // 调用基类方法  
    myCar.honk();   // 调用派生类方法  
    
    Bicycle myBike;  
    myBike.start();  // 调用基类方法  
    myBike.ringBell();  // 调用派生类方法  
    
    return 0;  
}
```
#### **代码解析：**

- Vehicle 类是基类，定义了 start 方法。
- Car 和 Bicycle 类都是派生类，分别添加了自己的特定行为（如 honk 和 ringBell）。

## **5.4 类成员的访问级别**

### **5.4.1 访问修饰符**

在C++中，类成员（变量和方法）的访问级别由访问修饰符控制。主要有三种访问修饰符：

- **public（公共）**：公共成员可以被类的外部访问。
- **protected（保护）**：保护成员只能在基类和派生类中访问，不能被类的外部访问。
- **private（私有）**：私有成员只能在类的内部访问，外部无法访问。

### **5.4.2 示例：访问修饰符的用法**
```
#include <iostream>  

class Example 
{  
public:  
    int publicVar;  // 公共变量  

protected:  
    int protectedVar;  // 保护变量  

private:  
    int privateVar;  // 私有变量  

public:  
    // 构造函数  
    Example() 
    {  
        publicVar = 1;  
        protectedVar = 2;  
        privateVar = 3;  
    }  

    void display() 
    {  
        std::cout << "Public: " << publicVar << std::endl;  
        std::cout << "Protected: " << protectedVar << std::endl;  
        std::cout << "Private: " << privateVar << std::endl;  
    }  
};  

int main() 
{  
    Example obj;  
    obj.publicVar = 10;  // 可以访问公共变量  
    // obj.protectedVar = 20;  // 错误：无法访问保护变量  
    // obj.privateVar = 30;  // 错误：无法访问私有变量  
    obj.display();  // 调用显示函数  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，Example 类有三个变量：publicVar、protectedVar 和 privateVar，分别对应不同的访问级别。
- main 函数可以访问 publicVar，但无法访问 protectedVar 和 privateVar。

### **5.4.3 访问修饰符的意义**

- **public**：允许外部代码访问，适合需要公开的属性和方法。
- **protected**：允许派生类访问，适合在继承中需要的属性。
- **private**：保护内部数据，防止外部直接访问，增强封装性。

### **5.4.4 示例：使用访问修饰符的好处**
```
#include <iostream>  

class BankAccount 
{  
private:  
    double balance;  // 余额是私有的  
public:  
    BankAccount() : balance(0) {}  // 构造函数初始化余额为0  

    void deposit(double amount) 
    {  
        if (amount > 0) 
        {  
            balance += amount;  // 只允许正数存款  
            std::cout << "Deposited: " << amount << std::endl;  
        }  
    }  

    void displayBalance() 
    {  
        std::cout << "Current Balance: " << balance << std::endl;  
    }  
};  

int main() 
{  
    BankAccount account;  
    account.deposit(100);  // 存款  
    account.displayBalance();  // 显示余额  
    // account.balance = 1000;  // 错误：无法直接访问私有变量  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，BankAccount 类的 balance 变量是私有的，外部无法直接修改。
- 通过公共方法 deposit 和 displayBalance，可以安全地管理余额。

## **5.5 派生类中的构造函数**

### **5.5.1 构造函数的概念**

- **构造函数**是一个特殊的成员函数，用于初始化对象。当创建对象时，构造函数会自动调用。
- 构造函数的名称与类名相同，并且没有返回值。

### **5.5.2 基类构造函数的调用**

- 当创建派生类对象时，基类的构造函数会首先被调用。这是因为派生类依赖于基类的初始化。

### **5.5.3 示例：基类和派生类的构造函数**
```
#include <iostream>  

class Animal {  // 基类  
public:  
    Animal() {  
        std::cout << "Animal created." << std::endl;  
    }  
};  

class Dog : public Animal {  // 派生类  
public:  
    Dog() {  
        std::cout << "Dog created." << std::endl;  
    }  
};  

int main() {  
    Dog myDog;  // 创建Dog对象  
    return 0;  
}
```
#### **代码解析：**

在这个例子中，创建 Dog 对象时，首先会调用 Animal 的构造函数，然后才会调用 Dog 的构造函数。输出为：

Animal created.

Dog created.

### **5.5.4 使用构造函数初始化成员变量**

- 可以在构造函数中初始化成员变量，确保在创建对象时赋予合适的初始值。

### **5.5.5 示例：带参数的构造函数**
```
#include <iostream>  

class Car  
{  // 基类  
public:  
    std::string brand;  
    int year;  
    // 带参数的构造函数  
    Car(std::string b, int y)  
    {  
        brand = b;  
        year = y;  
        std::cout << "Car created: " << brand << ", Year: " << year << std::endl;  
    }  
};  

class ElectricCar : public Car  
{  // 派生类  
public:  
    ElectricCar(std::string b, int y) : Car(b, y)  
    {  // 调用基类构造函数  
        std::cout << "ElectricCar created." << std::endl;  
    }  
};  

int main()  
{  
    ElectricCar myCar("Tesla", 2022);  // 创建ElectricCar对象  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，Car 类有一个带参数的构造函数，可以初始化品牌和年份。
- ElectricCar 类在其构造函数中使用初始化列表调用基类构造函数，确保 Car 的成员变量被正确初始化。

## **5.6 多重继承**

### **5.6.1 什么是多重继承？**

- **多重继承**是指一个类可以继承多个基类。这使得派生类可以同时拥有多个基类的特性和行为。

### **5.6.2 多重继承的基本语法**
```
class DerivedClass : public BaseClass1, public BaseClass2 
{
*// 派生类的内容*
 };
```
- DerivedClass 是派生类，BaseClass1 和 BaseClass2 是基类。

**5.6.3 示例：使用多重继承**
```
#include <iostream>  

class Animal {  // 第一个基类  
public:  
    void eat() {  
        std::cout << "Animal is eating." << std::endl;  
    }  
};  

class Pet {  // 第二个基类  
public:  
    void play() {  
        std::cout << "Pet is playing." << std::endl;  
    }  
};  

class Dog : public Animal, public Pet {  // 派生类  
public:  
    void bark() {  
        std::cout << "Dog barks." << std::endl;  
    }  
};  

int main() {  
    Dog myDog;  
    myDog.eat();  // 调用Animal的方法  
    myDog.play(); // 调用Pet的方法  
    myDog.bark(); // 调用Dog的方法  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，Dog 类同时继承了 Animal 和 Pet 两个基类，可以访问这两个基类的方法。

### **5.6.4 多重继承的优势**

- **灵活性**：通过多重继承，可以组合不同类的特性，创建功能更强大的类。
- **代码复用**：可以复用多个基类的功能，减少代码冗余。

### **5.6.5 多重继承中的问题：继承成员的模糊性**

- 当多个基类中有相同名称的方法时，会导致模糊性，这时编译器无法判断调用哪个方法。

### **5.6.6 示例：解决模糊性**
```
#include <iostream>  

class A {  
public:  
    void show() {  
        std::cout << "A's show()" << std::endl;  
    }  
};  

class B {  
public:  
    void show() {  
        std::cout << "B's show()" << std::endl;  
    }  
};  

class C : public A, public B {  
public:  
    void show() {  
        A::show(); // 明确调用A的show()  
        B::show(); // 明确调用B的show()  
    }  
};  

int main() {  
    C obj;  
    obj.show(); // 调用C的show()，同时调用A和B的show()  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，C 类通过 A::show() 和 B::show() 明确指定了调用哪个基类的方法，从而解决了模糊性问题。

## **5.7 多态性**

### **5.7.1 什么是多态性？**

- **多态性**是指同一操作作用于不同对象时，表现出不同的行为。简单来说，多态允许使用基类的指针或引用来调用派生类的方法。

### **5.7.2 多态性的类型**

1. **编译时多态性**（静态多态性）：通过函数重载和运算符重载实现。
2. **运行时多态性**（动态多态性）：通过虚函数实现。

### **5.7.3 示例：编译时多态性**

**通过函数重载实现多态性。**
```
#include <iostream>  
#include <string> // 添加此行以确保 std::string 可以使用  

class Print {  
public:  
    void show(int i) {  
        std::cout << "Integer: " << i << std::endl;  
    }  

    void show(double d) {  
        std::cout << "Double: " << d << std::endl;  
    }  

    void show(std::string s) {  
        std::cout << "String: " << s << std::endl;  
    }  
};  

int main() {  
    Print print;  
    print.show(5);         // 调用整数版本  
    print.show(5.5);       // 调用双精度版本  
    print.show("Hello");   // 调用字符串版本  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，show 方法被重载以接受不同类型的参数，实现了编译时的多态性。

### **5.7.4 运行时多态性的实现：虚函数**

- **虚函数**是基类中声明为 virtual 的成员函数，用于实现运行时多态性。

### **5.7.5 示例：使用虚函数实现运行时多态性**
```
#include <iostream>  

class Animal 
{  // 基类  
public:  
    virtual void sound() 
    {  // 声明为虚函数  
        std::cout << "Animal makes a sound." << std::endl;  
    }  
};  

class Dog : public Animal 
{  // 派生类  
public:  
    void sound() override 
    {  // 重写虚函数  
        std::cout << "Dog barks." << std::endl;  
    }  
};  

class Cat : public Animal 
{  // 另一个派生类  
public:  
    void sound() override 
    {  // 重写虚函数  
        std::cout << "Cat meows." << std::endl;  
    }  
};  

void makeSound(Animal* animal) 
{  
    animal->sound();  // 通过基类指针调用  
}  

int main() 
{  
    Animal* myDog = new Dog();  // 基类指针指向派生类对象  
    Animal* myCat = new Cat();  
    makeSound(myDog);  // 输出：Dog barks.  
    makeSound(myCat);  // 输出：Cat meows.  
    delete myDog;  // 释放内存  
    delete myCat;  
    return 0;  
}
```
#### **代码解析：**

- 在这个例子中，sound 函数在基类 Animal 中声明为虚函数。在派生类 Dog 和 Cat 中重写了该方法。
- 通过基类指针 Animal\* 调用 sound 方法时，实际调用的是派生类的版本，这就是运行时多态性。

### **5.7.6 虚函数中的默认实参值**

- 虚函数的默认实参值在编译时就会确定，无法在运行时进行动态绑定。

## **5.. C++17与C++20的对比**

### **5.8.1 C++17与C++20的变化**

C++20在类和面向对象编程方面引入了一些重要的变化和新特性，提升了代码的可读性和可维护性。以下是几个主要的变化：

**概念（Concepts）**：

C++20引入了概念，用于约束模板参数，使得代码更易于理解和使用。概念提供了一种方法来指定类型的要求，增强了模板编程的可读性。

**示例**：
```
#include <iostream>  
#include <concepts>  

template<typename T>  
concept Incrementable = requires(T a) {  
    { ++a } -> std::same_as<T&>; // 检查自增操作  
};  

template<Incrementable T>  
void increment(T& value) {  
    ++value;  
}  

int main() {  
    int x = 5;  
    increment(x); // 合法  
    std::cout << x << std::endl; // 输出6  
    return 0;  
}
```
**范围for循环（Ranges）**：

C++20引入了范围for循环，允许更方便地遍历容器，增强了对集合的操作能力。

**示例**：
```
#include <iostream>  
#include <vector>  

int main() {  
    std::vector<int> numbers = {1, 2, 3, 4, 5};  

    // 更简洁的遍历  
    for (int n : numbers) {  
        std::cout << n << " ";  
    }  

    std::cout << std::endl;  
    return 0;  
}
```
**三方运算符（Spaceship Operator）**：

C++20引入了“太空船运算符”<=>，简化了比较操作的实现，自动生成比较函数。

**示例**：
```
#include <iostream>  

class Point 
{  
public:  
    int x, y;  

    // 自动生成比较运算符  
    auto operator<=>(const Point&) const = default;  
};  

int main() 
{  
    Point p1{1, 2};  
    Point p2{2, 3};  

    if (p1 < p2) 
    {  
        std::cout << "p1 is less than p2" << std::endl;  
    }  
    return 0;  
}
```
### **5.8.2 C++20的优势**

- **更强的类型安全**：通过概念，编译器可以在编译时检查模板参数，减少运行时错误。
- **更简洁的代码**：使用范围for循环和太空船运算符可以使代码更加简洁易读，减少样板代码的量。
- **提升了可维护性**：新特性让代码逻辑更清晰，便于维护和扩展。

## **5.9 总结**

### **5.9.1 总结**

在本章节中，我们学习了C++的面向对象编程（OOP）基础，包括类的定义、继承、访问控制、构造函数的使用、多重继承以及多态性。接着，我们还对比了C++17与C++20的主要特性和变化，重点介绍了C++20的新特性，如概念、范围和太空船运算符。以下是主要内容的回顾：

- **类与对象**：类是描述对象的蓝图，对象是类的实例。我们可以定义类的成员变量和成员函数，以描述对象的属性和行为。
- **继承**：通过继承，派生类可以获取基类的属性和方法，实现代码复用。访问修饰符（public、protected、private）控制了成员的可见性。
- **构造函数**：用于初始化对象的特殊成员函数。构造函数可以带参数，使用初始化列表来设置成员变量的初值。
- **多重继承**：允许一个类继承多个基类，增加了灵活性和功能。需要注意处理潜在的模糊性。
- **多态性**：同一操作对不同对象表现出不同的行为。通过虚函数实现运行时多态性，使得基类指针可以调用派生类的方法。
- **C++20的新特性**：包括概念、范围、太空船运算符等，使得C++编程更加灵活和简洁，增强了代码的可读性和安全性。

### **5.9.2 习题**

为了加深理解和实践所学的知识，下面是一些练习题：

- **类的定义**：

定义一个 Student 类，包含学生姓名、年龄和学号作为成员变量，添加一个方法来显示学生的信息。

- **继承**：

创建一个 Animal 基类，包含 speak() 方法。然后定义一个 Cat 和一个 Dog 派生类，分别实现不同的叫声。

- **访问控制**：

在上面的 Animal 类中，使用访问修饰符保护成员变量，确保只有通过方法才能访问它们。

- **多重继承**：

创建两个基类 Person 和 Employee，分别包含 name 和 employeeID。定义一个 Manager 类，从这两个基类继承，并添加一个方法显示所有信息。

- **多态性**：

定义一个基类 Shape，包含一个虚函数 area()。创建 Circle 和 Rectangle 类，分别实现 area() 方法，并展示多态性。

- **C++20新特性**：

尝试使用C++20的概念定义一个模板函数，限制只能接受浮点类型作为参数。

