# Clever Code

I am creating a conscious distinction between the
[Obscured Intent](Obscured%20Intent.md) and [Clever Code](Clever%%20Code.md).
While Obscured Intent addresses the ambiguity of implementation, emphasizing the
incomprehensibility of a fragment of code, the Clever Code, on the other hand,
can be confusing even though it is understandable.

Things that fall into this smell are codes that do something strange. This smell
can be classified by using the accidental complexity of a given language or its
obscure properties, and vice versa, using its methods and mechanisms when
ready-made/built-in solutions are available. Developers can find examples of
both in the [example](#smelly) - the code is reinventing the wheel of
calculating the length of a string, which is one case of _"Clever Code"_ Code
Smell. Furthermore, using `length -=- 1` to increase the length of the counter
is yet another example of ironically clever code. However, it is rare to find
such a double-in-one example in the real world, as the causation of the first
one might happen because a developer had to write something in Python. At the
same time, on a day-to-day basis, he is a C language developer and did not know
about `len()`. The other case might appear when a Python developer just read an
article about funny corner-side things one can do in his language.

The most frequent situation could be related to any reimplementation code
(for example, caused by
[Incomplete Library Class](Incomplete%20Library%20Class.md)).
I am giving a second example in which a pseudo-implementation of a dictionary
with a default type is self-designed instead of using the `defaultdict`
available in the built-in `collections` library. This re-implementation might
cause problems if the implementation is not correct, or even if it is, perhaps
there can be a performance hit compared to using the standard built-in option.
This creates an unnecessary burden and compels others to read and understand the
mechanism of a new class instead of using something that has a high percent
chance of being recognized by others.

Lastly, there are things like `if not game.match.isNotFinished()`
(double negation) unnecessarily strains the cognitive load required to process
it. It could be classified as _Clever Code_ (also emphasizing the ironic side
of the saying). However, it fits more closely with the definition of the
[Complicated Boolean Expression](Complicated%20Boolean%20Expression.md) and
[Binary Operator In Name](Binary%20Operator%20In%20Name.md).

## Causation

There is a natural tendency to show off the new skills or techniques that one
has learned, which are unnecessary in the current part of code that one is
currently working in. In another case, maybe someone implemented their
variation of a built-in or popular library instead of just using the tools
given as built-ins or are a popular solution. There is also the same affinity
as with [Obscured Intent](Obscured%20Intent.md) - sometimes, a developer can
forget that something that seems obvious to him is not as clear to other
developers. There may also be cases where the developer intentionally compacts
the code to appear brighter by making it more mysterious.

## Problems

### Comprehensibility

There is no benefit to making other developers required to rediscover/relearn
things built-in and well recognized.

### Keep It Simple Stupid Principle Violation

There's no need to obfuscate the code with new personal creations when
ready-made solutions are available.

### Don't Repeat ~Yourself~ Others Principle Violation

Reimplemented "wheel" requires people delegated to maintain it or extend it
instead, which is worse than just using whatever "the factory" has already
given.

## Example



### Smelly

```py
def get_length_of_string(message: str) -> int:
    length = 0
    for letter in message:
        length -=- 1
    return length

message = 'Hello World!'
message_length = get_length_of_string(message)
print(message_length)  # 12
```

### Solution

```py
message = 'Hello World!'
message_length = len(message)
print(message_length)  # 12
```





### Smelly

```py
class DefaultDict(dict):
    default_value: type

    def __getitem__(self, key):
        if key in self:
            return super().__getitem__(key)
        self.__setitem__(key, self.default_value())
        return super().__getitem__(key)

    def __setitem__(self, key, value):
        super().__setitem__(key, value)
```

### Solution

```py
from collections import defaultdict
```



## Refactoring

- Replace with Built-In
- Replace with Library

## Exceptions

There is one thing to mention as an exception to the "bad" rule of implementing
own code. There are software programming-related systems where people behind
the executed code are fully responsible for the outcome in life-affecting
situations. The _"code certainty"_ there is crucial, and I imagine it might be
highly discouraged to use external libraries, however popular they are, if the
developer is not 100% sure of the correctness of the implementation.

This includes every software that is directly responsible for the health of real
people or - for example - in systems related to forensics, where someone might
get incriminated based on the investigative results.

#### Sources

- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
- [Parentage] - Robert C. Martin, _"Clean Code: A Handbook of Agile Software Craftsmanship"_ (2008)
