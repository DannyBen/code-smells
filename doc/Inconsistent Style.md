# Inconsistent Style

The same thing as in [Inconsistent Names](Inconsistent%20Names.md) applies to
the general formatting and code style used in the project. Browsing through the
code should have a similar feeling to reading a good article or a book -
consistent and elegant. In the project, the code layout should not be changed
preferentially or randomly but should be uniform so as not to disturb the
expected form of code in the following lines

Reading a novel where on each page, the reader is surprised by the new font
ranging from <span style="font-family: 'Times New Roman'">Times New
Roman</span> through <span style="font-family: 'Comic Sans MS'">Comic
Sans</span> up to <span style="font-family: consolas">Consolas</span> is
distracting and could break out of the flow state.

Another example of an _Inconsistent Style_ smell could be _Sequence
Inconsistency_, for example, in the order of parameters within classes or
methods. Once defined, the order should be kept in the group of all
abstractions on that particular subject. If the order is not preserved, it
leads, once again, to the unpleasant feeling of dissatisfaction after(if ever!)
the mind realizes that it was again surprised wrong. Depending on the specific
case, it would still be only half the trouble if the flipped parameters were of
different types (such as `string` and `int`). If the type were the same
(e.g., `int`), this could lead unnoticeably to a significant hidden bug.

## Causation

Team members working on the same project disagreed on one particular coding
style, linter, or code formatter. In the worst case, different people could use
different formatters or different formatting rules and overwrite the whole
files with their style of choice over each other, littering the git history
with new commits.

## Problems

### Error-Prone

With advanced IDE type-hinting nowadays, change is smaller, but when a bug gets
introduced by a sequence inconsistency, it might not be enjoyable to find out
its root cause.

### Comprehensibility

Depending on the state of code, the comprehensibility issues that the
inconsistent style can cause range from irrelevant up to illegible.

### Flow State Disruption

Familiarity is an essential factor in code orientation and navigation.

## Examples



### Smelly

Inconsistent Style

```py
my_first_function(
    arg1=1,
    arg2=2,
    arg3=3
)
my_second_function(arg1=1,
                   arg2=2,
                   arg3=3)
my_third_function(
    arg1=1, arg2=2, arg3=3)
```





### Smelly

Sequence Inconsistency

```py
class Character:
    DAMAGE_BONUS: float

    def rangeAttack(self, enemy: Character, damage: int, extra_damage: int):
        total_damage = damage + extra_damage*self.DAMAGE_BONUS
        ...

    def meleeAttack(self, enemy: Character, extra_damage: int, damage: int):
        total_damage = damage + extra_damage*self.DAMAGE_BONUS
        ...

witcher.rangeAttack(skeleton, 300, 200)
witcher.meleeAttack(skeleton, 300, 200)  # potentially overlooked error
```



## Refactoring

- Introduce Linter Rules
- Reorder Parameters

---

#### Sources

- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
