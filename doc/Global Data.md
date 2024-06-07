# Global Data

The _Global Data_ is quite similar to the [Middle Man](Middle%20Man.md) code
smell, but here rather than a class, the broker is the _global scope_ in which
the data is freely available to everyone. These global scope variables are
undesirable because it directly causes the
[Hidden Dependencies](Hidden%20Dependencies.md) code smell and a highly nasty
[Mutable Data](Mutable%20Data.md) code smell.
Global data can be read from anywhere, and there is no easy way to discover
which bit of code touches it. If the variable in the global scope is
additionally mutable, then this becomes an extremally bad case of
_[Mutable](Mutable%20Data.md) [Fate over Action](Fate%20over%20Action.md) (data class)_.
Fowler, in 1999 recalled that in the early days of programming, back when there
were no objects, even causing the
[Long Parameter List](Long%20Parameter%20List.md) code smell was preferable to
the Global Data [[1](#sources)]. For the same reasons, a Singleton Pattern can
also be problematic[[2](#sources)].

## Problems

### **Hard to Test**

Each Global Variable is a hidden dependency that a tester has to mock.

### **Hard to Reason About**

Global Variables exponentially fuzz the clarity of the codebase.

### **Inter Component Coupling**

### **Encapsulation Violation**

## Refactoring

- Encapsulate Variable

## Exceptions

In the context of the system as a whole, some communication between modules must
take place. All possibilities should be appropriately balanced so that none of
the smells dominate ([Global Data](Global%20Data.md),
[Tramp Data](Tramp%20Data.md), [Message Chain](Message%20Chain.md),
[Middle Man](Middle%20Man.md)) to make the entire codebase as clear as possible.

---

#### Sources

- [[1](#sources)] - Martin Fowler, "Refactoring: Improving the Design of Existing Code" (1999)
- [[2](#sources)] - Martin Fowler, "Refactoring: Improving the Design of Existing Code (3rd Edition)" (2018)
