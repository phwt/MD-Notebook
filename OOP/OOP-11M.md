# Object Oriented Programming

## Scanner
### Import
```java
import java.util.*;
import java.util.Scanner;
```
### Usage
```java
Scanner scanner = new Scanner(System.in);

String str = scanner.nextLine();
int num = scanner.nextInt();
float real = scanner.nextFloat();
double morereal = scanner.nextDouble();
```
### Notice
```java
Scanner scanner = new Scanner();
int num = scanner.nextInt();
String str = scanner.nextLine(); // Skips because nextInt() does not read newline character
```

## Naming

- Class `PascalCase`
- Variable `lowercase`
- Method `camelCase`
- Constant `UPPER_CASE`

## Typecasting

### `=` Operator
```java
int a = 10;
double b = a;
```
### Operation
```java
int a = 10;
double b = 15.0;
System.out.println("1: " + (a+b));
```
### Casting
```java
double b = 12.7;
int a = (int) b;
```
### Wrapper Class
```java
String str = "1945";
int num = Integer.parseInt(str);
```
## Encapsulation

### Access Modifier
- `public` (+) | Accessible by every class.
- `private` (-) | Internal access only. - User `getter` `setter`
- `protected` (#) | Accessibly by subclass.
- `default` | Package-level access.

| Modifier | Same class | Same package | Subclass | Any Class |
|:--------:|:----------:|:------------:|:--------:|:---------:|
|  + public  |      Y     |       Y      |     Y    |     Y     |
|  # protected |      Y     |       Y      |     Y    |     N     |
|  default  |      Y     |       Y      |     N    |     N     |
|  - private |      Y     |       N      |     N    |     N     |

### Inheritance
- **Superclass** | To be inherit by subclass.
- **Subclass** | Extends superclass.

```java
class SuperClass{
    private type field1;
    private type field2;
    
    private void method1(){...};
}
```
```java
class SubClass extends SuperClass{
    private type field3;
}
```
Every class extends `Object` by default
```java
class SomeClass extends Object{}
```
### `super`
```java
class SuperClass{
    protected void printMe(String s){
        System.out.println(s);
    }
}
```
```java
class SubClass extends SuperClass{
    super.printMe("wowdude");
}
```

## Polymorphism

### Dynamic Binding
```java
class SuperClass{}
class SubClass extends SuperClass{}
class RealSubClass extends SubClass{}
```
```java
SuperClass superclass = new SuperClass();
SuperClass subclass = new SubClass();
SuperClass realsubclass = new RealSubClass();

SubClass superclass = new SuperClass(); // Illegal
RealSubClass subclass = new SubClass(); // Can't declare subclass and new superclass
```
### Overload
```java
class Overload{
    @Overload
    public void printMe(){
        System.out.println("Hello there");
    }
    @Overload
    public void printMe(String name){
        System.out.println("Hello there, General " + name);
    }
}
```
### Override
```java
class SuperClass{
    public void greeting(){
        System.out.println("Hello from superclass");
    }
}
```
```java
class SubClass extends SuperClass{
    @Override
    public void greeting(){
        System.out.println("Hello from subclass");
    }
}
```

### Virtual Method Invocation

**Method present in both superclass and subclass**
```java
Student s1 = new GradStudent();
s1.showDetails(); // showDetails() of GradStudent
```
**Method present only in subclass**
```java
Student s1 = new GradStudent();
s1.getSupervisor(); // Illegal, getSupervisor() does not present in Student
```
```java
Student s1 = new GradStudent();
((GradStudent)s1).getSupervisor(); // Temporary cast to GradStudent
```

## Constructor
```java
class Rifle{
    public String model;
    public double caliber;
    
    public Rifle(){ // Default constructor
        model = "HK 416";
        caliber = 5.56;
    }
    
    public Rifle(String model, double caliber){
        this.model = model;
        this.caliber = caliber;
    }
}
```
```java
Rifle rifle1 = new Rifle();
rifle1.model; // HK 416
rifle1.caliber; // 5.56

Rifle rifle2 = new Rifle("AK-47", 5.45);
rifle1.model; // AK-47
rifle1.caliber; // 5.45
```

## `this` `super`
- `super`| Superclass attribute, method
- `super()` | Superclass constructor
- `this`| Current class attribute, method
- `this()` | Current class constructor

## `final`
- `Class` | Unable to inherit
- `Method` | Unable to override
- `Variable` | Making constant

## `static` attribute, method
`static` belongs to class not an object!
`static` method cannot be overrided but overloaded.
```java
Math.sqrt(112); // No object creation required
```
---
```java
class MyNumber{
    static int pi = 3.14;
    public static int sum(int a, int b){
        return a + b;
    }
}
```
```java
MyNumber.pi; // 3.14
MyNumber.sum(1, 2) // 3

MyNumber num1 = new MyNumber();
MyNumber num2 = new MyNumber();
num1.pi = 41.3;
num2.pi; //41.3
```

## Abstract class
To be extends by another class. Require at least one abstract method (method with no body).
```java
abstract class ToBeExtend{
    public int sum(int a, int b);
}
```
```java
class ToExtend extends ToBeExtend{
    public int sum(int a, int b){
        return a+b;
    }
}
```

## Interface
To be implemented. Interface != Multiple extend. Enforcing a good design.
```java
abstract class ToBeImplement{
    public int sum(int a, int b);
    public int product(int a, int b);
}
```
```java
class ToImplement implements ToBeImplement{
    public int sum(int a, int b){
        return a+b;
    }
    public int product(int a, int b){
        return a*b;
    }
}
```
