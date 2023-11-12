## SOLID Principles Guide

### Overview
SOLID is a mnemonic acronym representing five key principles in object-oriented programming, crucial for creating maintainable, understandable, and flexible software. These principles are [1] [2] [3]:
1. **S**ingle Responsibility Principle
2. **O**pen/Closed Principle
3. **L**iskov Substitution Principle
4. **I**nterface Segregation Principle
5. **D**ependency Inversion Principle

### 1. Single Responsibility Principle (SRP)
#### Definition
A class should have one, and only one, reason to change. This principle focuses on ensuring that a class addresses a single functionality or responsibility.

#### Benefits
- **Easier Testing**: Fewer test cases are needed for a class with a single responsibility.
- **Lower Coupling**: Reduces dependencies on other classes.
- **Better Organization**: Simplifies understanding and maintaining code.

#### Example
```java
public class Book {
    private String name;
    private String author;
    private String text;
    // Constructors, getters, setters
}

public class BookPrinter {
    void printTextToConsole(String text){
        // Print logic
    }
    void printTextToAnotherMedium(String text){
        // Other print logic
    }
}
```
Here, `Book` handles data-related functionalities, whereas `BookPrinter` is responsible for printing operations, adhering to SRP.

### 2. Open/Closed Principle (OCP)
#### Definition
Classes should be open for extension but closed for modification. This principle aims to allow classes to be extended without modifying existing code, thus preventing potential bugs.

#### Benefits
- **Enhanced Flexibility**: Easily extend class functionalities.
- **Reduced Bugs**: Minimizes issues introduced by changes in existing code.

#### Example
```java
public class Guitar {
    // Guitar-related properties and methods
}

public class ElectricGuitar extends Guitar {
    private String extraFeature;
    // Additional functionalities specific to ElectricGuitar
}
```
`ElectricGuitar` extends `Guitar` without altering the original `Guitar` class, adhering to OCP.

### 3. Liskov Substitution Principle (LSP)
#### Definition
Derived classes must be substitutable for their base classes. This principle ensures that a subclass can replace its superclass without affecting the program's correctness.

#### Benefits
- **Improved Code Reusability**: Ensures subclasses fulfill the contract of the superclass.
- **Enhanced Reliability**: Maintains consistency and correctness across subclasses.

#### Example
```java
public class Bird {
    public void fly(){}
}

public class Duck extends Bird {
    // Duck-specific implementation of fly
}
```
Here, `Duck` can replace `Bird` without altering the behavior expected from `Bird`, adhering to LSP.

### 4. Interface Segregation Principle (ISP)
#### Definition
Clients should not be forced to depend on interfaces they do not use. This principle focuses on creating specific interfaces rather than a single, general-purpose interface.

#### Benefits
- **Reduced Overhead**: Clients only use the interfaces relevant to them.
- **Increased Flexibility**: Easier to make changes without affecting clients.

#### Example
```java
public interface Printable {
    void print();
}

public interface Scannable {
    void scan();
}

public class AllInOnePrinter implements Printable, Scannable {
    public void print() {
        // Print logic
    }
    public void scan() {
        // Scan logic
    }
}
```
`AllInOnePrinter` implements `Printable` and `Scannable`, adhering to ISP.

### 5. Dependency Inversion Principle (DIP)
#### Definition
High-level modules should not depend on low-level modules. Both should depend on abstractions. This principle aims to reduce the direct dependencies among classes.

#### Benefits
- **Enhanced Modularity**: Easier to modify and test classes independently.
- **Reduced Coupling**: Decreases the dependency between high-level and low-level classes.

#### Example
```java
public interface Storage {
    void storeData(String data);
}

public class CloudStorage implements Storage {
    public void storeData(String data) {
        // Cloud storage logic
    }
}

public class DataProcessor {
    private Storage storage;
    // Use Storage abstraction
}
```
`DataProcessor` depends on the `Storage` abstraction, not on a specific implementation, adhering to DIP.

---

### Conclusion
Adhering to the SOLID principles fosters a robust, maintainable, and scalable software design. These principles guide developers in creating efficient and resilient object-oriented systems.

### References

[1] https://www.baeldung.com/solid-principles  
[2] https://stackify.com/solid-design-principles   
[3] https://www.jrebel.com/blog/solid-principles-in-java   
