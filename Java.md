# <span style="color:red">Java</span>



- **Java** is a general-purpose computer-programming language that is concurrent, class-base, object-oriented.
- It is intended to let application developers "write once, run anywhere" 
  Compiled Java code can run on all platforms that support Java without the need for recompilation. 
- Java applications are typically **compiled** to **bytecode** that can run on any **Java virtual machine** (**JVM**) regardless of computer architecture. 
- **JDK** (Java Development Kit)
  - Provides the environment to develop and execute Java program. 
  - Includes: development tools and JRE to execute the program.
- **JRE** Java Runtime Environment (or Java RTE)
  - Provides the minimum requirements for executing or run a Java program or application.
  - Consists of: Java Virtual Machine (JVM), library classes, and supporting files. 
- **JVM** (Java Virtual Machine)
  - Virtual machine that provides runtime environment to drive the Java Code or applications. 
  - It converts Java bytecode into machines language.
  - Java code is complied into bytecode. This bytecode gets interpreted on different machines

![difference](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/JDK_JRE_JVM_x.jpg)

- **Compiler**: Program which converts a program from one level of language to another. 
  Example: conversion of Java code into byte code
- **Interpreter**: Program which converts a program at one level to another programming language at the **same level.** 
  Example: conversion of Java byte code into native machine code

**Java is both compiled and interpreted language**



#### Software Code Compilation & Execution process

In order to write and execute a software program, you need the following

**1) Editor** – To type your program into, a notepad could be used for this

**2) Compiler** – To convert your high language program into native machine code

**3) Linker** (java doesn't have linker) – To combine different program files reference in your main program together.

**4) Loader** – To load the files from your secondary storage device like Hard Disk, Flash Drive, CD into RAM for execution. The loading is automatically done when you execute your code.

**5) Execution** – Actual execution of the code which is handled by your OS & processor.

#### Java is *slow*

1. **Dynamic Linking:** Unlike C, linking is done at run-time, every time the program is run in Java.
2. **Run-time Interpreter:** The conversion of byte code into native machine code is done at run-time in Java which furthers slows down the speed

**JIT** or **Just-in-time compiler** is the part of the JVM. It is used to speed up the execution time

## Reflection ([source](https://www.geeksforgeeks.org/reflection-in-java/))

- Java API that allows us to inspect or/and modify runtime attributes of classes, interfaces, fields and methods. 
- Comes in handy when we don’t know their names at compile time.
- Allows for java “introspection”
- Used in debuggers & frameworks

## Memory Management

- Java is **passed by value**
- To run an application in an optimal way, JVM divides memory into stack and heap memory. **Whenever we declare new variables and objects, call new method, declare a String or perform similar operations, JVM designates memory to these operations from either Stack Memory or Heap Space.**

- **Stack**
  - used for static memory allocation and execution of a thread. 
  - Contains primitive values that are specific to a method and references to objects in a heap
  - Can't be accessed by another thread. 
  - Short lived. 
  - LIFO. 
  - Memory size is very less compare to heap. 
  - Much faster than Heap.
  - `StackOverflowError`

- **Heap**: 
  - used to hold Objects and Classes. 
  - Global accessible. 
  - Run for the entire execution of the application.
  - `OutOfMemoryError`

### Conditional Statements

1. `if`
2. ##### if… else
3. `switch`

### Loops

1. `for`

2. `while`

3. `do… while`

## Keywords

1. `this` **reference variable** that refers to the current object.

   - `this` can be used to refer current class instance variable.
   - `this` can be used to invoke current class method (implicitly)
   - `this` can be passed as an argument in the method call.
   - `this` can be passed as argument in the constructor call.
   - `this` can be used to return the current class instance from the method.
   - `this()` can be used to invoke current class constructor.

2. `new` instantiate a class by dynamically allocating memory for a new object and return a reference to that memory.

   `new` then follow by a call to a class constructor

   `Student a = new Student();`

3. `super` **reference variable** that refers to the parent class object.

   - An instance of parent class is created implicitly every time its subclass instance is created.
   - Can be used to refer immediate parent class instance variable
   - Can be used to invoke parent class method
   - `super()` invoke parent class constructor

4. `static` variable

   - Used to define a class member that can be used independently of any object of that class.

   - Can be used to refer to the common property of all objects
     <u>Example:</u> company name of employees, college name of students…
   - `static` variable gets memory only once in the class area at the time of class loading.
     => **Memory efficient**

5. `final` is used to declare:

   - **Constant Variable**
   - **Method** that can not be overridden
   - **Class** that can not be inherited

### Key Differences Between Static and Final in Java

1. The static keyword is applicable to a nested static class, variables, methods and blocks. On the other hand, final keyword is applicable to class methods and variables.
2. Static variable can be initialized any time whereas, a final variable must be initialized at the time of declaration.
3. A static variable can be reinitialized whereas, once initialized a final variable can never be reinitialized.
4. A static method can access the static member of the class and can only be invoked by other static methods. On the other hand, the final method can never be inherited by any class.
5. Static block is used to initialize the static variables whereas, final keyword does not support any block.



## <span style="color:red">String</span>

- Strings are sequence of characters. 
  In Java, strings are treated as **objects**.
- Create and manipulate strings with the provided **String class**
- **[Immutable](https://www.programcreek.com/2009/02/diagram-to-show-java-strings-immutability/)**: once created, string objects can't be changed.
- **String pool**: pool of Strings stored in **Java Heap Memory**
  - When we use `""` to create a String, it first looks for String with the same value in the String pool, if found it just returns the reference else it creates a new String in the pool and then returns the reference.
  - Use `new` operator to forcefully create a new String in heap space outside of the String pool.
  - Use `intern()` method to put it into the pool or to refer to another String object from the String pool having the same value.

#### StringBuffer vs StringBuilder

- **Buffer**
  - Provide **Synchronization**
  - **Thread SAFETY** 
  - That's why it's **SLOW** 
- **Builder**
  - **NO** synchronization
  - **NOT** thread safe
  - That's why it's **FAST**

- **Methods**: `append()`, `insert()`, `delete()` and `substring()`



## <span style="color:red">User inputs</span>

### Scanner

- Newer
- Scanner is **more powerful**. 
- Can parse the user input and read an int, short, byte, float, long and double apart from String
- Non-synchronized. **Can not** be shared between thread
- Slower because of parsing input

### BufferedReader

- Older
- Can only read String.
- Has large buffer (8KB). Should use if reading long string
- Synchronized. Can be shared between thread
- Faster because of simply reading sequence of characters



## <span style="color:red">Primitive Types</span>

- int			32bit
- short        16bit
- long          64bit
- float         32bit
- double     64bit
- byte          8bit
- char          16bit
- boolean    true/false

**Auto-boxing**: implicit conversion from primitives to an object of corresponding wrapper class

**Auto-unboxing**: converting an object of wrapper class into corresponding primitive type

`Integer i = new Integer(10); `

```java
// Unboxing
int x = i;
```

```java
// Auto-boxing
Character c = 'a'; 
  
// Auto-unboxing of Character 
char ch = c; 
```

### Wrapper Class

class whose object wraps or contain primitive data types.

**WHY?**

- To convert primitives to Objects
- Some class in `java.util` package only handle Object
- Data Structure in `Collection` framework like `ArrayList` stores only objects not primitives
- Object is needed to support synchronization in multithreading

## Package

Group of similar types of classes, interfaces and sub-packages. 
Two types: 

- **Built-in** package: java, lang, awt, javax, swing, net, io, util, sql etc.
- **User-defined** package.
- **Why?**
  - Categorize the classes and interfaces so that they can be easily maintained.
  - Provides access protection.
  - Removes naming collision.

## Exceptions

- Events that occur during the execution of programs that disrupt the normal flow of instructions 
  <u>Example</u>: divide by zero, array access out of bound, etc...
- In Java, an exception is an **object** that wraps an error event that occurred within a method and contains: 
  - Information about the error including its type 
  - The state of the program when the error occurred 
  - Optionally, other custom information 

- **Categories**: 
  - Checked Exceptions
  - Unchecked Exceptions
  - Errors

![ExceptionHierarchyJava](https://cdn2.howtodoinjava.com/wp-content/uploads/ExceptionHierarchyJava.png)

### Check Exceptions

- Exceptions that are checked at compile time.
- The compiler enforces to handle them explicitly. 
- Catching Exceptions:
  - `try ... catch` keywords 
  - `throw ... throws` keywords
  - `finally` block

- Example: `FileNotFoundException`

### Unchecked Exceptions

- Exceptions that are **NOT** checked at compile time
- The compiler **does not** enforce that you handle them explicitly. 
  <u>Example</u>: **Errors** and **RuntimeExceptions** are **unchecked** `ArrayIndexOutOfBoundsException`
- Methods do not have to declare that they `throws` them (in the method signatures). 
- It is assumed that the application cannot do anything to recover from these exceptions (at runtime). 

### Errors

These are not exceptions at all, but problems that arise beyond the control of the user or the programmer. Errors are typically ignored in your code because you can rarely do anything about an error. 

<u>Example</u>: `StackOverflow` or `OutOfMemoryError` occurs, an error will arise. They are also ignored at the time of compilation. 



## Data Structure



![data-structure](https://i.stack.imgur.com/XhKOu.jpg)



`Collections framework` has 2 interface: `Collection` and `Map`

`Collections` is a Utiliy Class

- Dynamic size

- Can't store premitive

  

### Array:

- An object which contains elements of a similar data type. It is a data structure where we store similar elements. We can store only a fixed set of elements in a Java array.
- Type can be primitive or Object
- Size is **not** dynamic



## <span style="color:red">OOP</span>

**Object-Oriented Programming** is a methodology or paradigm to design a program using classes and objects. It simplifies the software development and maintenance through some concepts: 

- Object
- Classes
- Inheritance
- Polymorphism
- Abstraction
- Encapsulation

### **Object**

- Any entity that has state and behavior is known as an object. It can be physical or logical.
  Example: a chair, pen, table, keyboard, bike, etc.
- Can be defined as an instance of a class. An object contains an address and takes up some space in memory. Objects can communicate without knowing the details of each other's data or code. The only necessary thing is the type of message accepted and the type of response returned by the objects.

**Example:** A dog is an object because it has states like color, name, breed, etc. as well as behaviors like wagging the tail, barking, eating, etc. 

### **Class**

A **class**, in the context of **Java**, is a template that are used to create objects, and to **define** object data types and methods. Core properties include the data types and methods that may be used by the object 
A class can also be defined as a blueprint from which you can create an individual object. Class doesn't consume any space.

Holds attributes/properties, methods/functions, classes, variables

- Static member: shared between objects of the same class
- Instance member: unique to an object

#### Variables Scope

- Static/class: accessible in the whole class0
- Instance: accessible in the object
- Local/method: assessible within a method
- Loop/Block: accessible within a block/loop of code

**Variable shadowing**: `this.id = id`

### **OOP vs POP (Procedure Oriented Programming)**

- OOPs makes development and maintenance easier whereas in a procedure-oriented programming language it is not easy to manage if code grows as project size increases. 
- OOPs provides data hiding whereas in a procedure-oriented programming language a global data can be accessed from anywhere. 

### **Constructor**

- A special type of method which is used to initialize an object.
- It is called when an instance of the object is created. 
  and memory is allocated for the object. 
- Has no return type.
- `super()` will implicitly be the first line of every constructor unless `this()` is used.

2 types of constructors:

1. **Default**
2. **Parameterized**

Rules for creating constructor:

- name must be the same as its class name
- must have **no** explicit return type
- can't be abstract, static, final and synchronized



## <span style="color:red"> **Pillars of OOP**</span>

### **1. Inheritance**

- Mechanism in which one object acquires all the properties and behaviors of a parent object. 

- Why? 

  - Create new classes that are built upon existing classes.
  - Re-use methods and fields of the parent class. Add new methods and fields in the current class.
  - Represent **IS-A** relationship (parent-child relationship).

- Advantages:

  - `Method overriding` (runtime polymorphism can be achieved)
  - Code reusability.

- Terms:

  - Super class/parent class
  - Sub class/child class

- Syntax:

  ```java
  class Subclass-name extends Superclass-name  
  {  
     //methods and fields added here 
  }
  ```

- **Does not support** multiple inheritance to reduce the complexity and simplify the language.

### **2. Polymorphism**

- An ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object. 

  Any Java object that can pass more than one IS-A test is considered to be polymorphic. In Java, all Java objects are polymorphic since any object will pass the IS-A test for their own type and for the class Object.

- **Method Overloading** a class that has multiple methods having same name but different parameters. Increase readability of the program if we use the same name for one kind of operation.

  - 2 ways to overloads:
    - Changing number of arguments
    - Changing data types

- **Method Overriding**

  - Used to provide specific implementation of a method which is already provided by its superclass.
  - Used for runtime polymorphism.
  - Rules to create method:
    - Must have same name as in parent class
    - Must have same parameter as in parent class
    - Must have inheritance relationship
    - `Can not` override `Static method` 
  
- **Covariance**: ability to refer a subclass as its super class

#### **Overloading vs Overriding**

- **Overloading**:
  - Used to increase the readability of the program
  - Performed within class
  - Parameter must be different
  - Example of compile time polymorphism
- **Overriding**:
  - Used to provide specific implementation of the method that is already provided by its super class
  - Occurs in two classes that have inheritance relationship
  - Parameter must be the same
  - Example of run time polymorphism

### **3. Encapsulation**

- Process of wrapping code and data together into a single unit
  <u>Example</u>: a capsule which is mixed of several medicines. 
  
- Fully encapsulated class: all the data members of the class private
  Use **setter** and **getter** methods to set and get the data in it. 
  
- The **Java Bean** class is the example of a fully encapsulated class. 

- **Advantages**
  
  - Make the class read-only or write-only.
  - Provide control over the data.
  - Achieve **Data hiding** because other classes won't be able to access private data members.
  - Easy to test -> Better for unit testing.
  
- **Modifiers**
  
  2 types:
  
  1. **Access modifiers**: specifies accessibility of a data member, method, constructor or class. 4 types
     
     - Private
     - Default
     - Protected
     - Public
     
     ![](https://i.stack.imgur.com/niONO.png)
  2. **Non-Access modifiers**:
  
     - Static : shared between objects of the same class
     - Abstract
     - Synchornized
     - Native
     - Volatile
     - Transient ect...

### **4. Abstraction**

- A process of hiding the implementation details and showing only functionality to the user.
  <u>Example:</u> sending SMS where you type the text and send the message. You don't know the internal processing about the message delivery.
- Lets us focus on what the object does instead of how it does it. 

#### Generalization:

- A process of extracting shared characteristics from two or more classes, and combining them into a generalized superclass. 
  Shared characteristics can be attributes, associations, or methods. 
- <u>Example</u>: 
  **Piece of Luggage** and **Piece of Cargo** partially share the same attributes. From a domain perspective, the two classes are also very similar. During generalization, the shared characteristics  are combined and used to create a new superclass **Freight** . **Piece of Luggage** and **Piece of Cargo** become subclasses of the class **Freight**. Therefore the properties that are common to the classes **Piece of Luggage** and **Piece of Cargo** are placed in the superclass **Freight** - Identification, Weight and ID-Number are those properties. 

#### Specialization:

- Means creating new subclasses from an existing class. 
- if certain attributes, associations, or methods only apply to some of the objects of the class, a subclass can be created. 
- <u>Example</u>:
  **Piece of Luggage** and **Piece of Cargo** shared similar properties that were placed in a superclass called **Freight**. When it comes to **Specialization**, if there is a property that is only applicable to a specific subclass, such as **Degree of  Hazardousness**, that property is placed in the class **Piece of Cargo** where-in this class also has all the properties of the **Freight** class with the concept of **Generalization**. 

#### How to achieve abstraction

2 ways:

- **Abstract class** (0 - 100%)
- **Interface** (100%)

#### 1. Abstract Class

- A class that is declared as `abstract` using `abstract keyword`
- Can have abstract and non-abstract methods
- Must be extended and implement all the methods
- Can't be instantiated.

#### 2. Interface

- A reference type in Java. It is similar to class. It is a collection of abstract methods. A class implements an interface, thereby inheriting the abstract methods of the interface.
- Interface may also contain constants, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods.
- Writing an interface is similar to writing a class. But a class describes the attributes and behaviors of an object. And an interface contains behaviors that a class implements.
- Unless the class that implements the interface is abstract, all the methods of the interface need to be defined in the class.

#### Interface vs Class

- Can't be instantiated
- Doesn't contain any constructor
- All methods are abstract
- Can't contain instance fields. Fields can only be declared as both `static` and `final`
- `implements` by a class, **not** `extends`
- Can `extends` **multiple interfaces**



## Generic types

Generic class or interface that is parameterized over types.

Allow to write a general, generic class (or method) that works with different types, allowing for code re-use.

#### [Variance](https://dzone.com/articles/covariance-and-contravariance)

Refers to how subtyping between more complex types relates to subtyping between their components ([source](https://en.wikipedia.org/wiki/Covariance_and_contravariance_(computer_science))).

- **Covariance**: accept subtypes
- **Contravariance**: accept supertypes

#### Wildcard

```java
ArrayList<Integer> intArrList = new ArrayList<>();
ArrayList<? super Integer> numArrList = intArrList; // Ok
```

- Lower bound: `? super Integer` translates to “any type that is an Integer type or its supertype”.
- Upper bound: `? extends Integer` restricts the unknown type to be a specific type or its subtype.

#### Read-only and write-only

- **Covariance**: read only
- **Contravariance**: write only

Remember that covariant types accept subtypes, so `ArrayList<? extends Numb`er> can contain any object that is either` of a `Number type or its subtype.

In this example, line 9 works, because we can be certain that whatever we get from the ArrayList can be upcasted to a `Number` type (because if it extends `Number`, by definition, it *is a* `Number`).

But `nums.add()` doesn’t work, because we cannot be sure of the “actual type” of the object. All we know is that it must be a `Number` or its subtypes (e.g. Integer, Double, Long, etc.).

With contravariance, the converse is true.

Line 9 works, because we can be certain that whatever the “actual type” of the object is, it must be `Integer` or its supertype, and thus accept an `Integer` object.

But line 10 doesn’t work, because we cannot be sure that we will get an `Integer`. For instance, `nums` could be referencing an ArrayList of `Objects`.

#### Applications

Therefore, since covariant types are read-only and contravariant types are write-only (loosely speaking), we can derive the following rule of thumb: **“Producer extends, consumer super”**.

A producer-like object that produces objects of type `T` can be of type parameter `<? extends` T>, while a consumer-like object that consumes objects of` `type T can be of type para`meter <?` super T>.





## Threads

A path of execution in a program, a sub-process

Multi-threading: use of more than once **concurrent** thread

2 types:

##### 1. User

- Created by application or user
- High priority
- Fore-ground thread
- JVM wait and exit only after every threads finish execution

##### 2. Daemon

- Mostly created by JVM
- Low priority
- Background thread
- JVM doesn't wait, will exit after user threads finish.
- Do house-keeping task like Garbage Collector

#####Garbage Collector

- Handles the allocation of memory
- Automatically ran. Can be request using `System.gc()`



### Creating Threads

- 1. Extend the Thread class

  - Override the Thread class’ run() method.
  - create an instance of the newly created child class
  - invoke that child’s start() method.

- 2. Create a class which implements the Runable interface

- **Runable**: a functional interface
  - note: a functional interface has one unimplemented method
  - implement run() method
  - this class is our “job”
  - Provide the “job” to a “worker”of a thread object
  - invoke start on the worker

### Methods

- set/getPriority():
- set/getName():
- isAlive():
- join():
- getState():
- isDaemon():
- run():
- start():

### Class

- - wait():
- - current thread pauses execution until notified, time elapses (if provided)
  - notify():
- - notifies a waiting thread to continue execution
    - if no threads are waiting, then nothing occurs
  - if multiple threads are waiting, selects one thread
  - notifyAll():
  - - similar to notify() but notifies all waiting threads to execute
  - synchronized:
- - keyword placed on a method to specify that a method will only be accessed by one thread at a time
    - e.g. StringBuffer & Vector methods

### Thread states

- NEW: Occurs when thread has been instantiated but run() or start() method has not yet been invoked
- RUNABLE: Occurs when run() has been called
- BLOCKED: Occurs when a thread is waiting for a synchronized resource
- WAITING: Occurs when wait() has been invoked or join() has been invoked
- TIMED_WAITING: Occurs when sleep(), join(), or wait() with a specified time has been invoked
- TERMINATED: Occurs when an unhandled error or exception occurs or when the thread has completed execution
- WARNING: 
  - Deadlock - two threads are waiting on each other
  - Starvation – Low priority thread cannot access resources due to a higher priority thread already accessing the resource

### Lambda Expression

- Express instances of functional interface
- **Functional interface**: An interface with single abstract method
- **Why?**
  - Enable to treat functionality as a method argument, or code as data.
  - A function that can be created without belonging to any class.
  - A lambda expression can be passed around as if it was an object and executed on demand.

- e.g. Runnable interface, Comparator
- Utilizes arrow notation
  - Runnable myJob = () -> { method body }
  - Comparator myComparator = (myObj obj1, myObj obj2) {method body }



### Design Pattern

- Solutions to general problems that software developers faced during software development.

- Factory Design Pattern:

  - relying on a factory Object to manage the instantiation of Objects for us.
  - Helpful when creating an object requires a lot of configuration or overhead

- Singleton: used when only an object is required for an application

  - Assure that there is only ever one instance of a particular object
    e.g. a connection pool
  - **How?**
    - a single static instance of the object
    - create a private constructor
    - use a getter to access the object

  - Two types of Singletons
    - Eager Singleton – pre-initialized
    - Lazy Singleton – initialized when called upon
  - Override the clone() method to do nothing