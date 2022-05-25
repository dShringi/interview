1. Singleton class: How it will break and how to prevent, ways to create singleton class
 - Class Singleton
   - private constructor
   - static field containing its only instance
   - static factory method for obtaining the instance
 - Enum Singleton
   ```java
   public enum EnumSingleton {
       INSTANCE("Init info");
       private String info;
       private EnumSingleton(String info) {
           this.info = info;
       }
       private EnumSingleton getInstance() {
           return INSTANCE;
       }
   }
   ```
 - Double Check Locking for Multithreading
2. Program to read updated five record from file (Design pattern)
3. In spring bean outer class bean is singleton and inner class bean is prototype how to solve
   - @Lookup annotation on `getPrototypeean()` method
   - use Provider interface to inject the prototype bean
   ```java
   public class SingletonProviderBean {

        @Autowired
        private Provider<PrototypeBean> myPrototypeBeanProvider;

        public PrototypeBean getPrototypeInstance() {
            return myPrototypeBeanProvider.get();
        }
    }
    ```
    - Scoped Proxy: we create a proxy object to wire the real object with the dependent one
        - Each time the method on the proxy object is called, the proxy decides itself whether to create a new instance of the real object or reuse the existing one
        - To set up this, we modify the Appconfig class to add a new @Scope annotation
        ```java
        @Scope(
            value = ConfigurableBeanFactory.SCOPE_PROTOTYPE, 
            proxyMode = ScopedProxyMode.TARGET_CLASS) 
        ```
    - ObjectFactory Interface: use ObjectFactory<T> interface to produce on demand objects of the given type
    ```java
    public class SingletonObjectFactoryBean {

        @Autowired
        private ObjectFactory<PrototypeBean> prototypeBeanObjectFactory;

        public PrototypeBean getPrototypeInstance() {
            return prototypeBeanObjectFactory.getObject();
        }
    }
    ```
4. Garbage collection in JVM a-b and b-a a holding b object and b holding a then is it eligible for garbage collection
5.  How to create functional interface
6.  What is predicate, consumer, function and supplier
7.  What is method reference
8.  What stream and filter
