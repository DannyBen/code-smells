# Tramp Data

This is very similar to the [Message Chains](./message-chain.md) code smell, but with the difference that there, the pizza supplier was ordered to go through a long chain of method calls. Here, the pizzeria supplier additionally delivers _"pizza"_ through that long chain of method calls, with _"pizza"_ present in each of the method parameters. This is an indicator of [Dubious Abstraction](./dubious-abstraction.md) code smell - the data that pass through long chains of calls, most likely at least one of the levels, are not consistent with the abstraction presented by each of the routine interfaces. [[1](#sources)]

## Causation

This can happen due to a cheap way of [Global Data](./global-data.md) code smell refactorization.

## Problems

### **Law of Demeter Principle Violation**

The functionality should be as close to the data it uses as possible. This doesn't seem to be the case when _Tramp Data_ is present.

## Examples



### Smelly

```py

class Game:
    timer: int
    match: Match

    def start_turn():
        match(timer).field(timer).players(timer).troops(timer)

```



## Refactoring

- Extract Method
- Hide Delegate
- Move Method

## Exceptions

In the context of the system as a whole, some communication between modules must take place. All possibilities should be properly balanced so that none of the smells dominate ([Global Data](./global-data.md), [Tramp Data](./tramp-data.md), [Message Chain](./message-chain.md), [Middle Man](./middle-man.md)) to make the entire codebase as straightforward as possible.

---

#### Sources

- [[1](#sources)] - Steve McConnell, _"Code Complete"_ (2004)
- [Origin] - Steve Smith, _"Refactoring Fundamentals"_ (2013)
- [Parentage] - Steve McConnell, _"Code Complete"_ (1993)
