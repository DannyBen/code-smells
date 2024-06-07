# Large Class

When one combines the smell of [Long Method](./long-method.md) and [Long Parameter List](./long-parameter-list.md), but on a higher abstraction level, then he would get the _Large Class_ code smell. Many long-form methods and an abundant number of parameters that can be passed to a class cause Large Class problems. The point is that the class has too many responsibilities and is doing too much.

## Causation

This problem occurs because, under time constraints, it is much easier to place a new code in an existing class than to create a whole new class for the feature.

## Problems

### **Hard to Read and Understand**

Large components are hard to comprehend, which amplifies if the element is not purely functional and stateless.

### **Hard to Change**

It is tough to assess where the change has to be made, and even after it is done, the developer has to verify whether that was the only one in the class that had to be changed to implement his new desired functionality. There is also the risk of breaking the functionalities of all the other responsibilities that the class has and breaking by making unexpected side effects.

### **Hard to Test**

The larger the class, the more potential scenarios (all the methods and state variations) have to be covered via tests.

## Refactoring

- Extract Class
- Extract Subclass
- Extract Interface
- Extract Domain Object
- Replace Data Value with Object

---

#### Sources

- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
