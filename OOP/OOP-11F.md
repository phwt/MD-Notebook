# Object Oriented Programming

## Naming

- **Class**: `PascalCase`
- **Variable**: `lowercase`
- **Method**: `camelCase`
- **Constant**: `UPPER_CASE`

## Access Modifier
- `public` (+) | Accessible by every class.
- `private` (-) | Internal access only. - User `getter` `setter`
- `protected` (#) | Accessibly by subclass.
- `default` | Package-level access.

| Modifier | Same class | Same package | Subclass | Any Class |
|:--------:|:----------:|:------------:|:--------:|:---------:|
|  public  |      Y     |       Y      |     Y    |     Y     |
|  private |      Y     |       Y      |     Y    |     N     |
|  public  |      Y     |       Y      |     N    |     N     |
|  default |      Y     |       N      |     N    |     N     |

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
