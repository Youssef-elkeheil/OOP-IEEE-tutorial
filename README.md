## Tabel Of Content

- [What is OOP?](#heading)
- [What are Classes and Objects?](#heading)
- [Classes and Objects](#heading)
  * [Create a Class](#sub-heading-1)
  * [Create an Object](#sub-heading-1)
  * [Multiple Objects](#sub-heading-1)
- [Class Methods](#sub-heading-1)
  * [Class Methods](#sub-heading-1)
  * [Parameters](#sub-heading-1)
- [Constructors](#heading)
  * [What is Constructor?](#sub-heading-1)
  * [Defualt Constructor](#sub-heading-1)
  * [Parameterized Constructor](#sub-heading-1)
  * [Constructor Overloading](#sub-heading-1)
  * [Copy Constructor](#sub-heading-1)
- [Destructors](#heading)
- [Encapsulation](#heading)
  * [Access Private Members](#sub-heading-1)
- [Inheritance](#heading)
 * [What is Inheritance?](#sub-heading-1) 
 * [Multilevel Inheritance](#sub-heading-1) 
 * [Multiple Inheritance](#sub-heading-1)
 * [Protected Members](#sub-heading-1)

# What is OOP?

OOP stands for Object-Oriented Programming.

>Procedural programming is about writing procedures or functions that perform operations on the data, while object-oriented programming is about creating objects that contain both data and functions.

**Object-oriented programming has several advantages over procedural programming:**

* OOP is faster and easier to execute
* OOP provides a clear structure for the programs
* OOP helps to keep the C++ code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
OOP makes it possible to create full reusable applications with less code and shorter development time

>**Tip:** The "Don't Repeat Yourself" (DRY) principle is about reducing the repetition of code. You should extract out the codes that are common for the application, and place them at a single place and reuse them instead of repeating it.


# What are Classes and Objects?

Classes and objects are the two main aspects of object-oriented programming.

**Look at the following illustration to see the difference between class and objects:**

![fruit example](fruit.png)

**Another example:**

![car example](car.png)


So, a class is a template for objects, and an object is an instance of a class.

When the individual objects are created, they inherit all the variables and functions from the class.

You will learn much more about classes and objects in the next chapter.

# Classes and Objects

C++ is an object-oriented programming language.

Everything in C++ is associated with classes and objects, along with its attributes and methods.

 For example: in real life, a car is an **object**. The car has **attributes**, such as weight and color, and **methods**, such as drive and brake.

Attributes and methods are basically variables and functions that belongs to the class. These are often referred to as "class members".

>A class is a user-defined data type that we can use in our program, and it works as an object constructor, or a "blueprint" for creating objects.


## Create a Class

To create a class, use the class keyword:

Create a class called "**MyClass**":
```c++
class MyClass {       // The class
  public:             // Access specifier
    int myNum;        // Attribute (int variable)
    string myString;  // Attribute (string variable)
};
```
> ### Example explained
>- The `class` keyword is used to create a class called ``MyClass``.
>- The `public` keyword is an **access specifier**, which specifies that members (attributes and methods) of the class are accessible from outside the class. You will learn more about access specifiers later.
>- Inside the class, there is an integer variable `myNum` and a string variable `myString`. When variables are declared within a class, they are called **attributes**.
>- At last, end the class definition with a **semicolon** ; .

## Create an Object 

In C++, an object is created from a class. We have already created the class named `MyClass`, so now we can use this to create objects.

To create an object of `MyClass`, specify the class name, followed by the object name.

To access the class attributes (`myNum` and `myString`), use the dot syntax (.) on the object:
### **Example**
Create an object called "`myObj`" and access the attributes:

```c++
class MyClass {       // The class
  public:             // Access specifier
    int myNum;        // Attribute (int variable)
    string myString;  // Attribute (string variable)
};

int main() {
  MyClass myObj;  // Create an object of MyClass

  // Access attributes and set values
  myObj.myNum = 15; 
  myObj.myString = "Some text";

  // Print attribute values
  cout << myObj.myNum << "\n";
  cout << myObj.myString;
  return 0;
}
```
## Multiple Objects
You can create multiple objects of one class:
### **Example**

```c++
// Create a Car class with some attributes
class Car {
  public:
    string brand;   
    string model;
    int year;
};

int main() {
  // Create an object of Car
  Car carObj1;
  carObj1.brand = "BMW";
  carObj1.model = "X5";
  carObj1.year = 1999;

  // Create another object of Car
  Car carObj2;
  carObj2.brand = "Ford";
  carObj2.model = "Mustang";
  carObj2.year = 1969;

  // Print attribute values
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";
  return 0;
}
```


# Class Methods
## Class Methods
Methods are functions that belongs to the class.

There are two ways to define functions that belongs to a class:

- Inside class definition
- Outside class definition

In the following example, we define a function inside the class, and we name it "`myMethod`".

>**Note:** You access methods just like you access attributes; by creating an object of the class and by using the dot syntax (`.`):

###  **Inside Example**
```c++
class MyClass {        // The class
  public:              // Access specifier
    void myMethod() {  // Method/function defined inside the class
      cout << "Hello World!";
    }
};

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}
```
To define a function outside the class definition, you have to declare it inside the class and then define it outside of the class. This is done by specifiying the name of the class, followed the scope resolution `::` operator, followed by the name of the function:

### **Outside Example**
```c++
class MyClass {        // The class
  public:              // Access specifier
    void myMethod();   // Method/function declaration
};

// Method/function definition outside the class
void MyClass::myMethod() {
  cout << "Hello World!";
}

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}
```
## Parameters
You can also add parameters:
### **Example**
```c++
#include <iostream>
using namespace std;

class Car {
  public:
    int speed(int maxSpeed);
};

int Car::speed(int maxSpeed) {
  return maxSpeed;
}

int main() {
  Car myObj; // Create an object of Car
  cout << myObj.speed(200); // Call the method with an argument
  return 0;
}
```
>## Access Specifiers
>there are three access specifiers:
>- public - members are accessible from outside the class
>- private - members cannot be accessed (or viewed) from outside the class
>- protected - members cannot be accessed from outside the class, however, they can be accessed in inherited classes. You will learn more about Inheritance later.

# Constructors
## What is constructor?

A constructor is a member function of a class which initializes objects of a class. In C++, Constructor is automatically called when object(instance of class) create. It is special member function of the class.

**How constructors are different from a normal member function?**

A constructor is different from normal functions in following ways:

- Constructor has same name as the class itself
- Constructors don’t have return type
- A constructor is automatically called when an object is created.

**Types of Constructors**
- Empty (Default) Constructor
- Parameeterized Constructor
- Copy Constructor
## Empty Constructor
Empty constructor is the constructor which doesn’t take any argument. It has no parameters.

To create a Empty constructor, use the same name as the class, followed by parentheses `()`:
### **Example**
```c++
class Rectangle {     // The class
  public:   // Access specifier
  int Length,Width;      //Variables     
  MyClass() {     // Constructor
    Length = 0;
    Width = 0;
    }
};

int main() {
  MyClass MyRec;    // Create an object of Rectangle (this will call the constructor)
  return 0;
}
```
>**Constructors** main use is to set initial values for attributes.

## Parameterized Constructor
It is possible to pass arguments to constructors. Typically, these arguments help initialize an object when it is created. To create a parameterized constructor, simply add parameters to it the way you would to any other function. When you define the constructor’s body, use the parameters to initialize the object.
### **Example**
```c++
class Car {        // The class
  public:          // Access specifier
    string brand;  // Attribute
    string model;  // Attribute
    int year;      // Attribute
    Car(string x, string y, int z) { // Constructor with parameters
      brand = x;
      model = y;
      year = z;
    }
};

int main() {
  // Create Car objects and call the constructor with different values
  Car carObj1("BMW", "X5", 1999);
  Car carObj2("Ford", "Mustang", 1969);

  // Print values
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";
  return 0;
}
```
>**Note:** The constructor has the same name as the class, it is always public, and it does not have any return value.

Just like functions, constructors can also be defined outside the class. First, declare the constructor inside the class, and then define it outside of the class by specifying the name of the class, followed by the scope resolution `::` operator, followed by the name of the constructor (which is the same as the class):
### **Example**
```c++
class Car {        // The class
  public:          // Access specifier
    string brand;  // Attribute
    string model;  // Attribute
    int year;      // Attribute
    Car(string x, string y, int z); // Constructor declaration
};

// Constructor definition outside the class
Car::Car(string x, string y, int z) {
  brand = x;
  model = y;
  year = z;
}

int main() {
  // Create Car objects and call the constructor with different values
  Car carObj1("BMW", "X5", 1999);
  Car carObj2("Ford", "Mustang", 1969);

  // Print values
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";
  return 0;
}
```
## Constructor Overloading

Constructors can be overloaded in a similar way as function overloading.

Overloaded constructors have the same name (name of the class) but the different number of arguments. Depending upon the number and type of arguments passed, the corresponding constructor is called.

### **Example**
```c++
#include <iostream>
using namespace std;

class Person {
   private:
    int age;

   public:
    // 1. Constructor with no arguments
    Person() {
        age = 20;
    }

    // 2. Constructor with an argument
    Person(int a) {
        age = a;
    }

    int getAge() {
        return age;
    }
};

int main() {
    Person person1, person2(45);

    cout << "Person1 Age = " << person1.getAge() << endl;
    cout << "Person2 Age = " << person2.getAge() << endl;

    return 0;
}
```
## Copy Constructor
A copy constructor is a member function which initializes an object using another object of the same class. A copy constructor has the following general function prototype:
```c++
  ClassName (const ClassName &old_obj); 
```
### **Example**
```c++
#include<iostream> 
using namespace std;

class Point
{
public:
    int x, y;
    Point(int x1, int y1) { x = x1, y = y1; } //Parameterized Constructor
    
    Point(const Point& p2) { x = p2.x; y = p2.y; } // Copy constructor
};

int main()
{
    Point p1(5, 6);
    Point p2 = p1; // Copy constructor is called here 
    //  also can be written p2(p1)
    // Let us access values assigned by constructors 
    cout << "p1.x = " << p1.x << ", p1.y = " << p1.y;
    cout << "\np2.x = " << p2.x << ", p2.y = " << p2.y;

    return 0;
}
 ```
# Destructors
**What is destructor?**

Destructor is a member function which destructs or deletes an object.

**When is destructor called?**

A destructor function is called automatically when the object goes out of scope:
- the function ends
- the program ends
- a block containing local variables ends
- a delete operator is called 

**How destructors are different from a normal member function?**

Destructors have same name as the class preceded by a tilde (`~`)
Destructors don’t take any argument and don’t return anything.

**Can there be more than one destructor in a class?**

No, there can only one destructor in a class with classname preceded by ~, no parameters and no return type.

**When do we need to write a user-defined destructor?**

If we do not write our own destructor in class, compiler creates a default destructor for us. The default destructor works fine unless we have dynamically allocated memory or pointer in class. When a class contains a pointer to memory allocated in class, we should write a destructor to release memory before the class instance is destroyed. This must be done to avoid memory leak.
### **Example**
```c++
#include <iostream>
using namespace std;
class HelloWorld{
public:
  //Constructor
  HelloWorld(){
    cout<<"Constructor is called"<<endl;
  }
  //Destructor
  ~HelloWorld(){
    cout<<"Destructor is called"<<endl;
   }
   //Member function
   void display(){
     cout<<"Hello World!"<<endl;
   }
};
int main(){
   //Object created
   HelloWorld obj;
   //Member function called
   obj.display();
   return 0;
}
```
# Encapsulation
The meaning of Encapsulation, is to make sure that "`sensitive`" data is hidden from users. To achieve this, you must declare class variables/attributes as `private` (cannot be accessed from outside the class). If you want others to read or modify the value of a `private` member, you can provide `public` `get` and `set` methods.

## Access Private Members

To access a private attribute, use public "get" and "set" methods:
### **Example**
```c++
#include <iostream>
using namespace std;

class Employee {
  private:
    // Private attribute
    int salary;

  public:
    // Setter
    void setSalary(int s) {
      salary = s;
    }
    // Getter
    int getSalary() {
      return salary;
    }
};

int main() {
  Employee myObj;
  myObj.setSalary(50000);
  cout << myObj.getSalary();
  return 0;
}
```
> ### **Example explained:** 
>- The `salary` attribute is `private`, which have restricted access.
>- The public `setSalary()` method takes a parameter (`s`) and assigns it to the `salary` attribute (salary = s).
>- The public `getSalary()` method returns the value of the private salary attribute.
>- Inside `main()`, we create an object of the `Employee` class. Now we can use the `setSalary()` method to set the value of the `private` attribute to `50000`. Then we call the `getSalary()` method on the object to return the value.

**Why Encapsulation?**

- It is considered good practice to declare your class attributes as private (as often as you can). Encapsulation ensures better control of your data, because you (or others) can change one part of the code without affecting other parts
- Increased security of data
# Inheritance
## What is Inheritance?
In C++, it is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" into two categories:

- derived class (child) - the class that inherits from another class
- base class (parent) - the class being inherited from
To inherit from a class, use the `:` symbol.

In the example below, the  `Car` class (child) inherits the attributes and methods from the `Vehicle` class (parent):
### **Example**
```c++
// Base class
class Vehicle {
  public:
    string brand = "Ford";
    void honk() {
      cout << "Tuut, tuut! \n" ;
    }
};

// Derived class
class Car: public Vehicle {
  public:
    string model = "Mustang";
};

int main() {
  Car myCar;
  myCar.honk();
  cout << myCar.brand + " " + myCar.model;
  return 0;
}
```
>### Why And When To Use "Inheritance"?
> It is useful for code reusability: reuse attributes and methods of an existing class when you create a new class.
## Multilevel Inheritance
A class can also be derived from one class, which is already derived from another class.

In the following example, `MyGrandChild` is derived from class `MyChild` (which is derived from `MyClass`).
### **Example**
```c++
// Base class (parent)
class MyClass {
  public:
    void myFunction() {
      cout << "Some content in parent class." ;
    }
};

// Derived class (child)
class MyChild: public MyClass {
};

// Derived class (grandchild)
class MyGrandChild: public MyChild {
};

int main() {
  MyGrandChild myObj;
  myObj.myFunction();
  return 0;
}
```
## Multiple Inheritance
A class can also be derived from more than one base class, using a **comma-separated list** (`,`):
## **Example**
```c++
// Base class
class MyClass {
  public:
    void myFunction() {
      cout << "Some content in parent class." ;
    }
};

// Another base class
class MyOtherClass {
  public:
    void myOtherFunction() {
      cout << "Some content in another class." ;
    }
};

// Derived class
class MyChildClass: public MyClass, public MyOtherClass {
};

int main() {
  MyChildClass myObj;
  myObj.myFunction();
  myObj.myOtherFunction();
  return 0;
}
```
## Protected Members
Until now, we have only used `public` (members of a class are accessible from outside the class) and `private` (members can only be accessed within the class). The third specifier, `protected`, is similar to `private`, but it can also be accessed in the inherited class:
### **Example**
```c++
// Base class
class Employee {
  protected: // Protected access specifier
    int salary;
};

// Derived class
class Programmer: public Employee {
  public:
    int bonus;
    void setSalary(int s) {
      salary = s;
    }
    int getSalary() {
      return salary;
    }
};

int main() {
  Programmer myObj;
  myObj.setSalary(50000);
  myObj.bonus = 15000;
  cout << "Salary: " << myObj.getSalary() << "\n";
  cout << "Bonus: " << myObj.bonus << "\n";
  return 0;
}
```
