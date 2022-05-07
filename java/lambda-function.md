## Definition
- an anonymous function that we can handle as a first-class language citizen
-  we can pass it to or return it from a method

## java.util.function package
- all functional interfaces have an informative `@FunctionalInterface` annotation
- any interface with a SAM(Single Abstract Method) is a functional interface
- Java 8's default methods are not abstract and do not count
- a functional interface may still have multiple *default methods*
- This function of a single argument is represented by the Function interface, which is parameterized by the types of its argument and a return value:
```java
public interface Function<T, R> { … }
```

## Primitive Function Specializations
- IntFunction, LongFunction, DoubleFunction: arguments are of specified type, return type is parameterized
- ToIntFunction, ToLongFunction, ToDoubleFunction: return type is of specified type, arguments are parameterized
DoubleToIntFunction, DoubleToLongFunction, IntToDoubleFunction, IntToLongFunction, LongToIntFunction, LongToDoubleFunction: having both argument and return type defined as primitive types, as specified by their names
```java
@FunctionalInterface
public interface ShortToByteFunction {
    byte applyAsByte(short s);
}
```

## Two-Arity Function Specializations
- To define lambdas with two arguments, we have to use additional interfaces that contain “Bi” keyword in their names: BiFunction, ToDoubleBiFunction, ToIntBiFunction, and ToLongBiFunction.
- BiFunction has both arguments and a return type generified, while ToDoubleBiFunction and others allow us to return a primitive value.
```java
map.replaceAll((name, oldValue) -> 
  name.equals("Freddy") ? oldValue : oldValue + 10000);
}
```

## Suppliers
- The Supplier functional interface is yet another Function specialization that does not take any arguments
- We typically use it for lazy generation of values
- Another use case for the Supplier is defining logic for sequence generation
- Other specializations of the Supplier functional interface include BooleanSupplier, DoubleSupplier, LongSupplier and IntSupplier, whose return types are corresponding primitives

## Consumers
- As opposed to the Supplier, the Consumer accepts a generified argument and returns nothing. It is a function that is representing side effects.
- There are also specialized versions of the Consumer — DoubleConsumer, IntConsumer and LongConsumer — that receive primitive values as arguments. More interesting is the BiConsumer interface. One of its use cases is iterating through the entries of a map
- Another set of specialized BiConsumer versions is comprised of ObjDoubleConsumer, ObjIntConsumer, and ObjLongConsumer, which receive two arguments; one of the arguments is generified, and the other is a primitive type

## Predicates
- a function that receives a value and returns a boolean value
- receives a generified value and returns a boolean. A typical use case of the Predicate lambda is to filter a collection of values
- there are IntPredicate, DoublePredicate and LongPredicate versions of this function that receive primitive values
  
## Operators
- Operator interfaces are special cases of a function that receive and return the same value type
- The UnaryOperator interface receives a single argument. One of its use cases in the Collections API is to replace all values in a list with some computed values of the same type
