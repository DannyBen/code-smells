# Special Case

Wake addresses the complex conditional situation as a _Special Case_ code smell with two symptoms - a complex `if` statement and/or value checking [before doing the actual work](./required-setup-or-teardown-code.md) [[1](#sources)].

## Causation

There was a need for a special case to handle. A hotfix that was never adequately fixed could also be the reason for the smell.

## Problems

### **Comprehensibility**

The method is doing a specific task, but there is "one special case" to consider.

### **Increased Test Complexity**

Special case has to have an extra special test.

## Example



### Smelly

```py
def parse_foo(foo: Foo) -> Goo:
    if 'zoo' in foo.sample_attribute:
        ...
        ...
        ...

    ...
    ...
    ...
    ...
```



## Refactoring

- Consolidate Conditional Expression
- Replace Conditional with Polymorphism
- Introduce Null Object
- Replace Exception with Test

## Exceptions

Recursive methods always have to have a base case to stop the recursion.

---

#### Sources

- [[1](#sources)], [Origin] - William C. Wake, _"Refactoring Workbook"_ (2004)
