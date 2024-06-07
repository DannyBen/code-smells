# Inappropriate Static

The rule of thumb given by uncle Robert is that when in doubt, one should prefer
non-static methods to static methods. The best way to check whether a method
should be static would be to think if the method should behave polymorphically.
An excellent example of a static method given by Martin is `math.max(double a,
double b)` - it is hard to think of polymorphic behavior for a `max` function.
On the other hand, `HourlyPayCalculator.calculate_pay(employee, overtime_rate)`
is dubious, as there could be different algorithms to calculate the payment,
and thus it should be a nonstatic method of class `Employee`. However, one
should be aware and take caution of the
[Speculative Generality](Speculative%20Generality.md) code smell. At the very
present moment, when there are no different algorithms yet requested or planned,
this is a stateless operation, which is acceptable for static methods. Steve
Smiths addresses that statics should be reserved for behavior that will never
change, besides the previously mentioned stateless operations, giving global
constants as examples[[1](#sources)].

[Static Cling](Inappropriate%20static.md) is a code smell based on the border of
the test code and the source code, although, following the Fail-Fast principle,
the issue starts in the developing parts of the codebase.

Whenever a static function is called, in most languages, it is, to say the
least, not trivial to test or mock the method in which it occurs. There are 3rd
party mocking frameworks, but that is more of a workaround for bad design.
Developers should look out for these dependencies because they are effortlessly
introduced into the code in styles other than Test-Driven Development.

## Problems

### Hard to Test

Using static functions and variables makes the code harder to test; requires
mocking.

### Coupling

### Single Responsibility Principle Violation

## Example



### Smelly

```py
class FooUtils:
    @staticmethod
    def wrap_tag_premium(foo: Foo):
        return f"[TAG]: {foo.action()}"

    @staticmethod
    def wrap_tag_special(foo: Foo):
        return f"[TAG]: {foo.action()}"
```

### Solution

```py
@dataclass
class FooTagWrapper:
    foo: Foo

    def wrap_tag_premium(self):
        return f"[PREMIUM]: {self.foo}"

    def wrap_tag_special(self):
        return f"[SPECIAL]: {self.foo}"
```



### Refactoring

- Encapsulate Method

---

#### Sources

- [[1](#sources)] - Steve Smith, _"Refactoring Fundamentals"_ (2013)
- [Origin] - Robert Martin, _"Clean Code: A Handbook of Agile Software Craftsmanship"_ (2008)
