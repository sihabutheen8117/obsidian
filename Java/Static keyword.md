## **1. What Does `static` Mean?**

- **Class-Level Association**: A `static` member is associated with the class rather than any object of the class. It is shared among all instances of the class.
- **Shared Memory**: Static members use a single memory allocation for the class and are initialized only once, regardless of how many objects are created.

## **2. `static` with Variables**

### **Static Variables (Class Variables):**

- Declared using the `static` keyword.
- Shared by all objects of the class.
- Memory is allocated only once at the time of class loading.

### **Example:**

java

CopyEdit

`public class Example {     static int count = 0; // Static variable      public Example() {         count++; // Increment static variable     }      public static void main(String[] args) {         Example obj1 = new Example();         Example obj2 = new Example();          System.out.println("Count: " + Example.count); // Output: Count: 2     } }
`

#### **Explanation:**

- `count` is a static variable, shared by both `obj1` and `obj2`.
- Changes made to `count` in one instance are reflected in the others.

## **3. `static` with Methods**

### **Static Methods:**

- Can be called without creating an object of the class.
- Cannot access non-static members directly (as non-static members are tied to an instance, while static methods belong to the class).
- Often used for utility or helper methods (e.g., `Math.sqrt()`).

### **Example:**

java

CopyEdit

`public class Calculator {     public static int add(int a, int b) {         return a + b; // Static method     }      public static void main(String[] args) {         int result = Calculator.add(5, 3); // Call without creating an object         System.out.println("Sum: " + result); // Output: Sum: 8     } }`

#### **Key Points:**

- You can call `add()` directly without creating an object of `Calculator`.
- Static methods cannot use `this` or `super`.## **3. `static` with Methods**


## **4. `static` with Blocks**

### **Static Blocks:**

- Used to initialize static variables or run code during class loading.
- Executed once, when the class is loaded into memory.

### **Example:**

java

CopyEdit

`public class StaticBlockExample {     static int value;      static {         value = 10; // Initialize static variable         System.out.println("Static block executed.");     }      public static void main(String[] args) {         System.out.println("Value: " + value); // Output: Static block executed. Value: 10     } }`

#### **Explanation:**

- The static block is executed before the `main()` method, when the class is loaded.