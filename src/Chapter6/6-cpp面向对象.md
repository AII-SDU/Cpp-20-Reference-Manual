# C++中的类和面向对象编程
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

1. #include <iostream>
2. class Student
3. {
4. public:
5. `    `std::string name;
6. `    `int age;
7. `    `void introduce()
8. {
9. `        `std::cout << "Hello, I'm " << name << " and I'm " << age << " years old." << std::endl;
10. `    `}
11. };
12. int main()
13. {
14. `    `Student student;
15. `    `student.name = "Alice";
16. `    `student.age = 20;
17. `    `student.introduce();
18. `    `return 0;
19. }

## **5.2 类和面向对象编程**

### **5.2.1 定义类和对象**

- **类**：可以看作是一个模板，定义了某一类事物的共同特征和行为。比如，一个“汽车”类可以定义所有汽车的属性（如颜色、品牌、速度）和行为（如启动、刹车、加速）。
- **对象**：是类的实例，表示具体的事物。比如，你可以用“我的车”来表示“汽车”类的一个具体对象。

### **5.2.2 类的基本结构**

一个类通常由以下几个部分组成：

- **成员变量**：描述对象的特征（属性）。
- **成员函数**：描述对象的行为（方法）。

### **5.2.3 示例：创建一个“汽车”类**

1. #include <iostream>
2. class Car
3. {
4. public:
5. `    `*// 成员变量*
6. `    `std::string brand;
7. `    `std::string color;
8. `    `int speed;
9. `    `*// 成员函数：启动汽车*
10. `    `void start()
11. {
12. `        `std::cout << "The " << color << " " << brand << " is starting." << std::endl;
13. `    `}
14. `    `*// 成员函数：加速*
15. `    `void accelerate(int increase)
16. {
17. `        `speed += increase;
18. `        `std::cout << "The " << brand << " accelerates to " << speed << " km/h." << std::endl;
19. `    `}
20. };
21. int main()
22. {
23. `    `Car myCar;  *// 创建一个Car类的对象*
24. `    `myCar.brand = "Toyota";  *// 设置属性*
25. `    `myCar.color = "red";
26. `    `myCar.speed = 0;
27. `    `myCar.start();  *// 调用成员函数*
28. `    `myCar.accelerate(50);  *// 加速*
29. `    `return 0;
30. }

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

1. class DerivedClass : public BaseClass
2. {
3. `    `*// 派生类的内容*
4. };

## **5.3.3 示例：创建一个“动物”类和派生类“狗”**

1. #include <iostream>
2. class Animal
3. {  *// 基类*
4. public:
5. `    `void eat()
6. `    `{
7. `        `std::cout << "This animal is eating." << std::endl;
8. `    `}
9. };
10. class Dog : public Animal
11. {  *// 派生类*
12. public:
13. `    `void bark()
14. `    `{
15. `        `std::cout << "The dog barks." << std::endl;
16. `    `}
17. };
18. int main()
19. {
20. `    `Dog myDog;  *// 创建Dog类的对象*
21. `    `myDog.eat();  *// 调用基类的方法*
22. `    `myDog.bark();  *// 调用派生类的方法*
23. `    `return 0;
24. }

#### **代码解析：**

- 在这个例子中，Animal 是基类，定义了一个 eat 方法。
- Dog 是派生类，继承了 Animal 的所有特性，并增加了一个 bark 方法。

### **5.3.4 使用继承的好处**

- **代码复用**：可以在多个派生类中共享基类的代码，减少重复。
- **逻辑清晰**：通过继承，可以建立类之间的层次结构，使代码结构更加清晰。

### **5.3.5 示例：创建一个“交通工具”类和派生类“汽车”和“自行车”**

1. #include <iostream>
2. class Vehicle
3. {  *// 基类*
4. public:
5. `    `void start()
6. `    `{
7. `        `std::cout << "The vehicle is starting." << std::endl;
8. `    `}
9. };
10. class Car : public Vehicle
11. {  *// 派生类*
12. public:
13. `    `void honk()
14. `    `{
15. `        `std::cout << "The car honks." << std::endl;
16. `    `}
17. };
18. class Bicycle : public Vehicle
19. {  *// 另一个派生类*
20. public:
21. `    `void ringBell()
22. `    `{
23. `        `std::cout << "The bicycle rings its bell." << std::endl;
24. `    `}
25. };
26. int main()
27. {
28. `    `Car myCar;
29. `    `myCar.start();  *// 调用基类方法*
30. `    `myCar.honk();   *// 调用派生类方法*
31. `    `Bicycle myBike;
32. `    `myBike.start();  *// 调用基类方法*
33. `    `myBike.ringBell();  *// 调用派生类方法*
34. `    `return 0;
35. }

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

1. #include <iostream>
2. class Example
3. {
4. public:
5. `    `int publicVar;  *// 公共变量*
6. protected:
7. `    `int protectedVar;  *// 保护变量*
8. private:
9. `    `int privateVar;  *// 私有变量*
10. public:
11. `    `*// 构造函数*
12. `    `Example()
13. `   `{
14. `        `publicVar = 1;
15. `        `protectedVar = 2;
16. `        `privateVar = 3;
17. `    `}
18. `    `void display()
19. `   `{
20. `        `std::cout << "Public: " << publicVar << std::endl;
21. `        `std::cout << "Protected: " << protectedVar << std::endl;
22. `        `std::cout << "Private: " << privateVar << std::endl;
23. `    `}
24. };
25. int main()
26. {
27. `    `Example obj;
28. `    `obj.publicVar = 10;  *// 可以访问公共变量*
29. `    `*// obj.protectedVar = 20;  // 错误：无法访问保护变量*
30. `    `*// obj.privateVar = 30;  // 错误：无法访问私有变量*
31. `    `obj.display();  *// 调用显示函数*
32. `    `return 0;
33. }

#### **代码解析：**

- 在这个例子中，Example 类有三个变量：publicVar、protectedVar 和 privateVar，分别对应不同的访问级别。
- main 函数可以访问 publicVar，但无法访问 protectedVar 和 privateVar。

### **5.4.3 访问修饰符的意义**

- **public**：允许外部代码访问，适合需要公开的属性和方法。
- **protected**：允许派生类访问，适合在继承中需要的属性。
- **private**：保护内部数据，防止外部直接访问，增强封装性。

### **5.4.4 示例：使用访问修饰符的好处**

1. #include <iostream>
2. class BankAccount
3. {
4. private:
5. `    `double balance;  *// 余额是私有的*
6. public:
7. `    `BankAccount() : balance(0) {}  *// 构造函数初始化余额为0*
8. `    `void deposit(double amount)
9. `   `{
10. `        `if (amount > 0)
11. `        `{
12. `            `balance += amount;  *// 只允许正数存款*
13. `            `std::cout << "Deposited: " << amount << std::endl;
14. `        `}
15. `    `}
16. `    `void displayBalance()
17. `    `{
18. `        `std::cout << "Current Balance: " << balance << std::endl;
19. `    `}
20. };
21. int main()
22. {
23. `    `BankAccount account;
24. `    `account.deposit(100);  *// 存款*
25. `    `account.displayBalance();  *// 显示余额*
26. `    `*// account.balance = 1000;  // 错误：无法直接访问私有变量*
27. `    `return 0;
28. }

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

1. #include <iostream>
2. class Animal
3. {  *// 基类*
4. public:
5. `    `Animal()
6. `    `{
7. `        `std::cout << "Animal created." << std::endl;
8. `    `}
9. };
10. class Dog : public Animal
11. {  *// 派生类*
12. public:
13. `    `Dog()
14. `    `{
15. `        `std::cout << "Dog created." << std::endl;
16. `    `}
17. };
18. int main()
19. {
20. `    `Dog myDog;  *// 创建Dog对象*
21. `    `return 0;
22. }

#### **代码解析：**

在这个例子中，创建 Dog 对象时，首先会调用 Animal 的构造函数，然后才会调用 Dog 的构造函数。输出为：

Animal created.

Dog created.

### **5.5.4 使用构造函数初始化成员变量**

- 可以在构造函数中初始化成员变量，确保在创建对象时赋予合适的初始值。

### **5.5.5 示例：带参数的构造函数**

1. #include <iostream>
2. class Car
3. {  *// 基类*
4. public:
5. `    `std::string brand;
6. `    `int year;
7. `    `*// 带参数的构造函数*
8. `    `Car(std::string b, int y)
9. `    `{
10. `        `brand = b;
11. `        `year = y;
12. `        `std::cout << "Car created: " << brand << ", Year: " << year << std::endl;
13. `    `}
14. };
15. class ElectricCar : public Car
16. {  *// 派生类*
17. public:
18. `    `ElectricCar(std::string b, int y) : Car(b, y)
19. `    `{  *// 调用基类构造函数*
20. `        `std::cout << "ElectricCar created." << std::endl;
21. `    `}
22. };
23. int main()
24. {
25. `    `ElectricCar myCar("Tesla", 2022);  *// 创建ElectricCar对象*
26. `    `return 0;
27. }

#### **代码解析：**

- 在这个例子中，Car 类有一个带参数的构造函数，可以初始化品牌和年份。
- ElectricCar 类在其构造函数中使用初始化列表调用基类构造函数，确保 Car 的成员变量被正确初始化。

## **5.6 多重继承**

### **5.6.1 什么是多重继承？**

- **多重继承**是指一个类可以继承多个基类。这使得派生类可以同时拥有多个基类的特性和行为。

### **5.6.2 多重继承的基本语法**

1. class DerivedClass : public BaseClass1, public BaseClass2 {
2. `    `*// 派生类的内容*
3. };

- DerivedClass 是派生类，BaseClass1 和 BaseClass2 是基类。

**5.6.3 示例：使用多重继承**

1. #include <iostream>
2. class Animal
3. {  *// 第一个基类*
4. public:
5. `    `void eat()
6. `    `{
7. `        `std::cout << "Animal is eating." << std::endl;
8. `    `}
9. };
10. class Pet
11. {  *// 第二个基类*
12. public:
13. `    `void play()
14. `    `{
15. `        `std::cout << "Pet is playing." << std::endl;
16. `    `}
17. };
18. class Dog : public Animal, public Pet
19. {  *// 派生类*
20. public:
21. `    `void bark()
22. `    `{
23. `        `std::cout << "Dog barks." << std::endl;
24. `    `}
25. };
26. int main()
27. {
28. `    `Dog myDog;
29. `    `myDog.eat();  *// 调用Animal的方法*
30. `    `myDog.play(); *// 调用Pet的方法*
31. `    `myDog.bark(); *// 调用Dog的方法*
32. `    `return 0;
33. }

#### **代码解析：**

- 在这个例子中，Dog 类同时继承了 Animal 和 Pet 两个基类，可以访问这两个基类的方法。

### **5.6.4 多重继承的优势**

- **灵活性**：通过多重继承，可以组合不同类的特性，创建功能更强大的类。
- **代码复用**：可以复用多个基类的功能，减少代码冗余。

### **5.6.5 多重继承中的问题：继承成员的模糊性**

- 当多个基类中有相同名称的方法时，会导致模糊性，这时编译器无法判断调用哪个方法。

### **5.6.6 示例：解决模糊性**

1. #include <iostream>
2. class A
3. {
4. public:
5. `    `void show()
6. `    `{
7. `        `std::cout << "A's show()" << std::endl;
8. `    `}
9. };
10. class B
11. {
12. public:
13. `    `void show()
14. `    `{
15. `        `std::cout << "B's show()" << std::endl;
16. `    `}
17. };
18. class C : public A, public B
19. {
20. public:
21. `    `void show()
22. `    `{
23. `        `A::show(); *// 明确调用A的show()*
24. `        `B::show(); *// 明确调用B的show()*
25. `    `}
26. };
27. int main()
28. {
29. `    `C obj;
30. `    `obj.show(); *// 调用C的show()，同时调用A和B的show()*
31. `    `return 0;
32. }

#### **代码解析：**

- 在这个例子中，C 类通过 A::show() 和 B::show() 明确指定了调用哪个基类的方法，从而解决了模糊性问题。

## **5.7 多态性**

### **5.7.1 什么是多态性？**

- **多态性**是指同一操作作用于不同对象时，表现出不同的行为。简单来说，多态允许使用基类的指针或引用来调用派生类的方法。

### **5.7.2 多态性的类型**

1. **编译时多态性**（静态多态性）：通过函数重载和运算符重载实现。
2. **运行时多态性**（动态多态性）：通过虚函数实现。

### **5.7.3 示例：编译时多态性**

- 通过函数重载实现多态性。

1. #include <iostream>
2. class Print
3. {
4. public:
5. `    `void show(int i)
6. `    `{
7. `        `std::cout << "Integer: " << i << std::endl;
8. `    `}
9. `    `void show(double d)
10. `    `{
11. `        `std::cout << "Double: " << d << std::endl;
12. `    `}
13. `    `void show(std::string s)
14. `    `{
15. `        `std::cout << "String: " << s << std::endl;
16. `    `}
17. };
18. int main()
19. {
20. `    `Print print;
21. `    `print.show(5);         *// 调用整数版本*
22. `    `print.show(5.5);       *// 调用双精度版本*
23. `    `print.show("Hello");   *// 调用字符串版本*
24. `    `return 0;
25. }

#### **代码解析：**

- 在这个例子中，show 方法被重载以接受不同类型的参数，实现了编译时的多态性。

### **5.7.4 运行时多态性的实现：虚函数**

- **虚函数**是基类中声明为 virtual 的成员函数，用于实现运行时多态性。

### **5.7.5 示例：使用虚函数实现运行时多态性**

1. #include <iostream>
2. class Animal
3. {  *// 基类*
4. public:
5. `    `virtual void sound()
6. `    `{  *// 声明为虚函数*
7. `        `std::cout << "Animal makes a sound." << std::endl;
8. `    `}
9. };
10. class Dog : public Animal
11. {  *// 派生类*
12. public:
13. `    `void sound() override
14. `    `{  *// 重写虚函数*
15. `        `std::cout << "Dog barks." << std::endl;
16. `    `}
17. };
18. class Cat : public Animal
19. {  *// 另一个派生类*
20. public:
21. `    `void sound() override
22. `    `{  *// 重写虚函数*
23. `        `std::cout << "Cat meows." << std::endl;
24. `    `}
25. };
26. void makeSound(Animal\* animal)
27. {
28. `    `animal->sound();  *// 通过基类指针调用*
29. }
30. int main()
31. {
32. `    `Animal\* myDog = new Dog();  *// 基类指针指向派生类对象*
33. `    `Animal\* myCat = new Cat();
34. `    `makeSound(myDog);  *// 输出：Dog barks.*
35. `    `makeSound(myCat);  *// 输出：Cat meows.*
36. `    `delete myDog;  *// 释放内存*
37. `    `delete myCat;
38. `    `return 0;
39. }

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

1. #include <iostream>
2. #include <concepts>
3. template<typename T>
4. concept Incrementable = requires(T a)
5. {
6. `    `{ ++a } -> std::same\_as<T&>; *// 检查自增操作*
7. };
8. template<Incrementable T>
9. void increment(T& value)
10. {
11. `    `++value;
12. }
13. int main()
14. {
15. `    `int x = 5;
16. `    `increment(x); *// 合法*
17. `    `std::cout << x << std::endl; *// 输出6*
18. `    `return 0;
19. }

**范围for循环（Ranges）**：

- C++20引入了范围for循环，允许更方便地遍历容器，增强了对集合的操作能力。

**示例**：

1. #include <iostream>
2. #include <vector>
3. int main() {
4. `    `std::vector<int> numbers = {1, 2, 3, 4, 5};
5. `    `for (int n : numbers) {
6. `        `std::cout << n << " "; *// 更简洁的遍历*
7. `    `}
8. `    `std::cout << std::endl;
9. `    `return 0;
10. }

**三方运算符（Spaceship Operator）**：

- C++20引入了“太空船运算符”<=>，简化了比较操作的实现，自动生成比较函数。

**示例**：

1. #include <iostream>
2. class Point
3. {
4. public:
5. `    `int x, y;
6. `    `auto operator<=>(const Point&) const = default;
7. *// 自动生成比较*
8. };
9. int main()
10. {
11. `    `Point p1{1, 2};
12. `    `Point p2{2, 3};
13. `    `if (p1 < p2) {
14. `        `std::cout << "p1 is less than p2" << std::endl;
15. `    `}
16. `    `return 0;
17. }

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

