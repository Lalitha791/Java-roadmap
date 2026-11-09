### **1. Classes vs. Objects**
* **Class (Blueprint):** A logical construct and user-defined data type that outlines shared properties and behaviors; it does not occupy physical memory space.
* **Object (Instance):** A physical entity instantiated from a class template that occupies memory during program execution.

### **2. Memory Management**
* **Stack Memory:** Holds reference variables (e.g., `Student s1`) and local execution frames.
* **Heap Memory:** Stores actual object instances allocated dynamically at runtime via the **`new`** operator.
* **Garbage Collection:** Java automatically reclaims memory occupied by unreferenced heap objects.

### **3. Constructors & `this` Keyword**
* **Constructor:** A specialized class function called automatically during instantiation to allocate memory and initialize object state.
* **`this` Keyword:** Refers to the current object instance; it resolves variable shadowing between fields and parameters and enables constructor chaining.

### **4. The `static` Keyword**
* **Class Ownership:** Static fields and methods belong to the **class itself** rather than any specific object instance.
* **Shared Memory:** A single shared copy of a static variable exists in memory across all instances of a class.
* **No Instance Needed:** Static methods (such as `main()`) run without requiring an object to be instantiated first.
* **Access Rules:** Static contexts **cannot** directly access non-static instance fields or use the **`this`** keyword, as non-static members require an instance reference.

### **5. Static Blocks & Nested Classes**
* **Static Initialization Block:** Executes **exactly once** when the class is first loaded into memory, making it ideal for static variable initialization.
* **Static Inner Classes:** Top-level outer classes cannot be `static`, but nested inner classes can be marked `static` so they don't depend on an instance of the outer enclosing class.

### **6. Singleton Design Pattern**
* **Single Instance Restriction:** Enforces a strict constraint ensuring only **one object instance** of a class is created in the entire application.
* **Implementation Mechanism:** Implemented using a `private` constructor to block external instantiation and a `public static` method to deliver the single cached instance.

### **7. Immutability (`final` Keyword)**
* **Primitive Fields:** Prevents value modification once initialized.
* **Reference Fields:** Prevents reassigning the reference variable to point to a new object, though internal fields of the referenced object may still remain mutable.

