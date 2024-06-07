# Fallacious Method Name

When I started to think of Code Smells from the comprehensibility perspective (of its lack of) as one of the critical factors, I was pretty intrigued that it was not yet thoroughly researched, or at least not when researching with a focus on _"Code Smell"_ as a keyword. There is a grounded idea about code that is obfuscated from the point of [Obscured Intentions](./obscured-intent.md) or code without any explanation ([Magic Number](./magic-number.md), [Uncommunicative Name](./uncommunicative-name.md)). I felt like there was a missing hole in the code that was intentionally too clever ([Clever Code](./clever-code.md)) or the code that contradicts itself. Fortunately, I have found a fantastic article that supports my thoughts and addresses some of what I had in mind under the name _Linguistic Antipatterns_ [[1](#sources)]. I have included their subset of antipatterns under one code smell because listing them one by one would be too granular from a code perspective. The idea behind them can be summarized by one name: _Fallacious Method Name_.

This smell is caused by creating conflicting methods or functions regarding  their functionality and naming. Over the years, programmers have developed connections between certain words and functionality that programmers should tie together. Going against logical expectations by, for example, creating a `getSomething` function that does not return is confusing and wrong.

## Causation

When we create methods, their name may not entirely represent what they will be doing after we finish working on them. Except that one should then go back and correct its name accordingly to what has been done.

## Problems

### **Decreased Readability**

Developers need to inspect the function or methods to determine what they do.

### **Reduced Reliability**

If someone would like to use a method with a given name, he should also expect the name's effect.

## Example



### Smelly

```py
def getFoos() -> Foo:
    ...
    foo: Foo = ...
    return foo

def isGoo() -> str:
    ...
    return 'yes'

def setValue(self, value) -> Any:
    ...
    return new_value
```

### Solution

```py
def getFoos() -> list[Foo]:
    ...
    foos: list[Foo] = ...
    return foos

def isGoo() -> bool:
    ...
    return True

def setValue(self, value) -> None:
    ...
```



## Refactoring

- Rename Method (to remove contradictions)

---

#### Sources

- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
- [Parentage1] - Venera Arnaoudova, Massimiliano Di Penta, Giuliano Antoniol _"Linguistic Antipatterns: What they are and how developers perceive them"_ (2015)
- [Parentage2] - Robert Martin, _"Clean Code: A Handbook of Agile Software Craftsmanship"_ (2008)
