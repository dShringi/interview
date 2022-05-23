- String[Immutable], StringBuffer[thread-safe], StringBuilder[faster]
- final, finalize(), finally{}
- ClassNotFoundException vs NoClassDefFoundException
- equals and hashcode
- volatile[visibility], synchronized[mutual exclusion, visibility], transient[serialization]
- ConcurrentHashMap vs HashMap
- HashMap Implementation
- LinkedHashMap vs TreeMap[sorted by natural ordering of its keys,logn] vs HashMap
- Annotation vs Marker Interface
- Checked and Unchecked Exceptions
- ArrayList vs LinkedList
- How hashmap works
- ThreadLocal
- Method Reference
- Static Inner Class vs Inner Class
- Static Initialization Block vs Initialization Block
- Method Signature: Method Name + Parameter List
- Implement immutable class
    
      - The class must be declared as final (So that child classes can’t be created)
      - Data members in the class must be declared as final (So that we can’t change the value of it after object creation)
      - A parameterized constructor
      - Getter method for all the variables in it
      - No setters(To not have the option to change the value of the instance variable)
    
- Cloning in Java (Object.clone() vs Cloneable)
- Comparable vs Comparator
        
      A comparable object is capable of comparing itself with another object. The class itself must implements the java.lang.Comparable interface to compare its instances.
      Unlike Comparable, Comparator is external to the element type we are comparing. It’s a separate class. We create multiple separate classes (that implement Comparator) to compare by different members.
      
      Collections class has a second sort() method and it takes Comparator. The sort() method invokes the compare() to sort objects.
      
      - Comparable is meant for objects with natural ordering which means the object itself must know how it is to be ordered. For example Roll Numbers of students. Whereas, Comparator interface sorting is done through a separate class.
      - Logically, Comparable interface compares “this” reference with the object specified and Comparator in Java compares two different class objects provided.
      - If any class implements Comparable interface in Java then collection of that object either List or Array can be sorted automatically by using Collections.sort() or Arrays.sort() method and objects will be sorted based on there natural order defined by CompareTo method.
      
      To summarize, if sorting of objects needs to be based on natural order then use Comparable whereas if you sorting needs to be done on attributes of different objects, then use Comparator in Java.
      
- Throws vs Throw
- try-catch-finally
  - On exception in try block, rest of the code in try block isn't executed and control is passed to catch block followed by finally and then the rest of the code outside try-catch-finally block
  - If there's no exception in try, catch never runs and finally will be executed followed by rest of the program
  - If there's no catch block or exception isn't handled in catch block, finally will be executed followed by default exception handling mechanism or rest of the program

Questions Asked
- Race condition in hashmap
- Implement hashmap on paper
- Hashmap through lambda
- SpringBoot annotations 
- Various exceptions in inter-microsevices communication

Links:
- https://www.toptal.com/java/interview-questions
