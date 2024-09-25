
# Factory Pattern

The Factory Pattern is a creational design pattern that provides an interface for creating objects in a super class but allows subclasses to alter the type of objects that will be created.

## UML Diagram

```
                    +----------------------------+
                    |       Creator (Factory)     |
                    +----------------------------+
                    |  + factoryMethod(): Product |
                    +----------------------------+
                               ▲
                               |
               +----------------------------+
               |                            |
   +---------------------+       +---------------------+
   |  ConcreteFactory1    |       |  ConcreteFactory2    |
   +---------------------+       +---------------------+
   | + factoryMethod()    |       | + factoryMethod()    |
   +---------------------+       +---------------------+
            |                            |
   +-----------------+          +------------------+
   | ConcreteProduct1 |          | ConcreteProduct2 |
   +-----------------+          +------------------+

```

## Key Components

1. **Product**:  
   The interface or abstract class that defines the structure of objects the factory will produce.

2. **Concrete Products**:  
   These are implementations of the `Product` interface. For example:
   - `ConcreteProduct1`
   - `ConcreteProduct2`

3. **Creator (Factory)**:  
   This declares the `factoryMethod()` for creating `Product` objects.

4. **Concrete Factories**:  
   These classes override the `factoryMethod()` and create specific `ConcreteProduct` instances:
   - `ConcreteFactory1`
   - `ConcreteFactory2`

## How It Works

- The client calls the `factoryMethod()` on the factory, and the concrete factory decides which product to instantiate.
- This pattern promotes flexibility by allowing different products to be created without changing the client code.

<hr>



# Abstract Factory Pattern

The Abstract Factory Pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes. This pattern allows you to produce various kinds of objects while keeping their concrete implementations hidden from the client.

## UML Diagram

```plaintext
                    +-----------------------------------+
                    |        AbstractFactory           |
                    +-----------------------------------+
                    | + createProductA(): AbstractA     |
                    | + createProductB(): AbstractB     |
                    +-----------------------------------+
                               ▲
                               |
               +-------------------------------+
               |                               |
   +--------------------------+    +--------------------------+
   | ConcreteFactory1          |    | ConcreteFactory2          |
   +--------------------------+    +--------------------------+
   | + createProductA(): A1    |    | + createProductA(): A2    |
   | + createProductB(): B1    |    | + createProductB(): B2    |
   +--------------------------+    +--------------------------+
            |                              |
   +------------------+           +-------------------+
   | ProductA1 (A1)   |           | ProductA2 (A2)    |
   +------------------+           +-------------------+
   | ProductB1 (B1)   |           | ProductB2 (B2)    |
   +------------------+           +-------------------+
```

## Key Concepts

- **AbstractFactory**: Declares an interface for creating abstract product families (`AbstractA`, `AbstractB`).
- **ConcreteFactory**: Implements the operations to create concrete product objects (`A1`, `A2`, `B1`, `B2`).
- **AbstractProduct**: Declares interfaces for a set of products (`ProductA`, `ProductB`).
- **ConcreteProduct**: Implements the abstract product interfaces (`ProductA1`, `ProductA2`, `ProductB1`, `ProductB2`).

## Benefits

- Ensures that products from a particular family are used together.
- Avoids tight coupling between concrete products and client code.

## Usage

Use the Abstract Factory Pattern when:
- A system should be independent of how its products are created, composed, and represented.
- You want to provide a family of products that are designed to be used together.


