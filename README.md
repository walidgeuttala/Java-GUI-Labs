# Java-GUI-Labs

# Object Oriented Programming Notes - Last Minute Revision :white_check_mark:

Here are some last-minute revision notes on object-oriented programming (OOP). These questions cover essential OOP concepts and can help you prepare for job interviews.

---

## Most Asked OOP Interview Questions

### 1: What is OBJECT-ORIENTED PROGRAMMING?

**Answer**: Object-oriented programming is a programming paradigm based on the concept of "objects". It focuses on data and functions bundled together in the form of objects.

---

### 2: Class and Object

**Answer**:

**Class**: A class is the blueprint from which individual objects are created. It defines a datatype by bundling data and methods that operate on the data.

**Object**: An object is an instance of a class. When a class is defined, no memory is allocated, but memory is allocated when an object of that class is instantiated.

```java
class Person {
    // Data Members
    String name;

    // Member Function
    void printName() {
        System.out.println("Person's name is: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an object of class Person
        Person person = new Person();
        
        // Access data member
        person.name = "Thanos";

        // Call member function
        person.printName();
    }
}
```

**Output**
> Person's name is: Thanos

---

### 3: Constructor

**Answer**: 

- Constructors are special methods invoked when an object is created. They initialize the object.

- Constructors have the same name as the class and may be defined inside or outside the class definition.

There are 3 types of constructors:

1. **Default Constructor**: Does not take any arguments.
2. **Parameterized Constructor**: Accepts parameters.
3. **Copy Constructor**: Initializes an object using another object of the same class.

#### Characteristics of the constructor:
- Constructors have no return type.
- They are automatically called when an object is created.
- If no constructor is defined, a default constructor is provided by the compiler.
- Constructors can be overloaded but cannot be virtual.

```java
class Student {
    String name;
    int age;
    boolean gender;

    // Default Constructor
    Student() {
        System.out.println("Default Constructor");
    }

    // Parameterized Constructor
    Student(String name, int age, boolean gender) {
        this.name = name;
        this.age = age;
        this.gender = gender;
        System.out.println("Parameterized Constructor");
    }

    // Copy Constructor
    Student(Student student) {
        this.name = student.name;
        this.age = student.age;
        this.gender = student.gender;
        System.out.println("Copy Constructor");
    }

    void printInfo() {
        System.out.println("Name = " + name);
        System.out.println("Age = " + age);
        System.out.println("Gender = " + gender);
    }
}

public class Main {
    public static void main(String[] args) {
        // Default Constructor
        Student s1 = new Student();
        s1.printInfo();

        // Parameterized Constructor
        Student s2 = new Student("Sumeet", 20, true);
        s2.printInfo();

        // Copy Constructor
        Student s3 = new Student(s2);
        s3.printInfo();
    }
}
```

**Output**
> Default Constructor\
> Name = null\
> Age = 0\
> Gender = false

> Parameterized Constructor\
> Name = Sumeet\
> Age = 20\
> Gender = true

> Copy Constructor\
> Name = Sumeet\
> Age = 20\
> Gender = true

---

### 4: Destructor

**Answer**: 

- In Java, destructors do not exist explicitly like in C++. Java has automatic garbage collection to handle object destruction.

---

### 5: The main features of OOPs?

**Answer**: The four main pillars of OOP are:

1. Encapsulation
2. Inheritance
3. Abstraction
4. Polymorphism

---

### 6: Inheritance

**Answer**: Inheritance allows a new class to inherit properties and methods from an existing class.
Multilevel Inheritance
Hierarchical Inheritance
Hybrid Inheritance

Java avoids multiple inheritance of classes to prevent conflicts like the diamond problem, but interfaces provide flexibility in achieving similar outcomes.

1. **Single Inheritance**: When a subclass inherits from one base class.

```java
class A {
    void displayA() {
        System.out.println("Base Class");
    }
}

class B extends A {
    void displayB() {
        System.out.println("Inherited from Class A");
    }
}

public class Main {
    public static void main(String[] args) {
        B obj = new B();
        obj.displayA();
        obj.displayB();
    }
}
```

**Output**
> Base Class \
> Inherited from Class A

---

### 7: Encapsulation

**Answer**: 

Encapsulation is the process of wrapping code and data together into a single unit, for example, a class. It restricts access to data to ensure integrity.

```java
class EncapsulationExample {
    private int data;

    public void setData(int data) {
        this.data = data;
    }

    public int getData() {
        return data;
    }
}

public class Main {
    public static void main(String[] args) {
        EncapsulationExample obj = new EncapsulationExample();
        obj.setData(10);
        System.out.println("Data = " + obj.getData());
    }
}
```

**Output**
> Data = 10

---

### 8: Abstraction

**Answer**: 

Abstraction focuses on hiding the internal details and showing only essential information.

```java
abstract class Animal {
    abstract void sound();
}

class Dog extends Animal {
    void sound() {
        System.out.println("Barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
    }
}
```

**Output**
> Barks

---

### 9: Polymorphism

**Answer**: 

Polymorphism allows one interface to be used for multiple implementations.

1. **Method Overloading (Compile-time Polymorphism)**:

```java
class OverloadExample {
    void display() {
        System.out.println("No arguments");
    }

    void display(int a) {
        System.out.println("One argument: " + a);
    }
}

public class Main {
    public static void main(String[] args) {
        OverloadExample obj = new OverloadExample();
        obj.display();
        obj.display(10);
    }
}
```

**Output**
> No arguments \
> One argument: 10

2. **Method Overriding (Runtime Polymorphism)**:

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog();
        animal.sound();
    }
}
```

**Output**
> Dog barks

---

### 10: Abstract Class

**Answer**: 

An abstract class cannot be instantiated and may contain abstract methods that must be implemented by subclasses.

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing Circle");
    }
}
```

---

### 11: Pure Virtual Function (in C++ called Abstract Method in Java)

**Answer**: 

A method declared as abstract without implementation in a class, forcing subclasses to implement it.

---

### 12: Friend Class & Friend Function (Java does not have a direct equivalent to C++ Friend Classes/Functions)

In Java, you control access using `private`, `protected`, `public`, and package-private access levels.

---

### 13: Access Modifiers

- **Private** – Accessible only within the class.
- **Protected** – Accessible within the same package or subclasses.
- **Public** – Accessible from anywhere.

---

This concludes the OOP concepts in Java.
