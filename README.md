
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
