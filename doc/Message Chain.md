# Message Chain

Suppose that class `A` requires data from class `D`, but to retrieve those data,
it has to make unnecessary calls to class `B` sequentially and then `C` to get
it. This function sequencing is called Message Chain code smell. Long sequences
of methods calls indicate hidden dependencies by being intermediaries. A
sequence of temporary variables could have also hidden the sequence of methods.
The problem with this smell is that any change in the intermediate relationship
causes the client to have to change. [[1](#sources)]

## Causation

Classes ask the objects to do the manipulation instead of telling the object
with which manipulation should be done.

## Problems

### Law of Demeter Principle Violation

Law of Demeter specifies that each class should have limited knowledge about
other classes and only to these classes, which are "closely" related to the
current class.

### Tell, Don’t Ask Principle Violation

The manipulation should be done by telling the object to manipulate, not by
asking for permission to manipulate.

## Examples

Note: Yes, what is smelly from the perspective of _Message Chain_, might be a
solution to [Middle Man](Middle%20Man.md).



### Smelly

```py
class Minion:
    _location: Location

    def action(self):
        ...
        if self._location.field.is_frontline():
            ...

class Location:
    field: Field

class Field:
    def is_frontline(self)
        ...
```

### Solution

```py
class Minion:
    _location: Location

    def action(self):
        ...
        if self.is_frontline():
            ...

    def is_frontline(self)
        return self._location.is_frontline()


class Location:
    _field: Field

    def is_frontline(self)
        return self._field.is_frontline()


class Field:
    def is_frontline(self)
        ...
```



## Exceptions

In the context of the system as a whole, some communication between modules must
take place. All possibilities should be properly balanced so that none of the
smells dominate ([Global Data](Global%20Data.md),
[Tramp Data](Tramp%20Data.md), [Message Chain](Message%20Chain.md),
[Middle Man](Middle%20Man.md)) to make the entire codebase as straightforward
as possible.

## Refactoring

- Hide Delegate _(note: this might create [Middle Man](Middle%20Man.md))_
- Extract Method
- Move Method

#### Sources

- [[1](#sources)] - Martin Fowler, "Refactoring: Improving the Design of Existing Code (3rd Edition)" (2018)
- [Origin] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
