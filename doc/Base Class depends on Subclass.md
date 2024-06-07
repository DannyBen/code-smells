# Base Class depends on Subclass

The rule is that the child classes should be deployable independently from the parent class. That allows us to deploy the system in discrete and independent components.

When one of these subclasses is modified, the base class does not need to be redeployed as well. In this way, the impact of change is much smaller, proportionally to the maintenance effort [[1](#sources)]. This smell is closely related to the [Shotgun Surgery](./shotgun-surgery.md) code smell.

## Problems

### **Liskov Substitution Principle Violation**

Base class and Subclass should be interchangeable without breaking the logic of the program.

---

#### Sources

- [[1](#sources)], [Origin] - Robert Martin, "Clean Code: A Handbook of Agile Software Craftsmanship" (2008)
