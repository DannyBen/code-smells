# Type Embedded in Name

Whenever a variable has an explicit type prefix or suffix, it can strongly
signal that it should be just a class of its own. For example,
`current_date = "2021-14-11"`, embeds the potential class `Date` in the name of
a variable, and that could also be classified as the
[Primitive Obsession](Primitive%20Obsession.md) code smell.

Wake signals that the embedded type could also be in the method names, giving an
example of a `schedule.add_course(course)` function in contrast to
`schedule.add(course)`. He notes that it could have been a matter of
preference, although he insists that this can be a problem wherever some
generalization occurs [[1](#sources)]. When a parent class for `Course` is
introduced to cover not only _courses_ but also _series of courses_, then
`add_course()` has a name that is no longer appropriate, thus suggesting the
usage of more neutral terms. [[1](#sources)] Parameters of a method are part of
the method name, and this kind of naming is also a duplication.

With all the possibilities of annotating variables, it is unnecessary to mention
it twice through variable name when type annotation or type hinting is present.
Names with embedded types in them, for which no class yet could represent them,
are good candidates to be refactored into separate classes.

## Causation

This was a standard in pointer-based languages, but it is not helpful in modern
Object-Oriented Programming languages. [[1](#sources)]

## Problems

### Duplication

Both the argument and name mentions the same type.

### Comprehensibility Issues

If the name of a variable is just precisely the name of the class, it's a case
of [Uncommunicative Name](Uncommunicative%20Name.md).

## Examples



### Smelly

```py
player_name: str = "Luzkan"
player_health: int = 100
player_stamina: int = 50
player_attack: int = 7
```

### Solution

```py
@dataclass
class Player:
    stamina: int
    health: int
    attack: int
    name: str

luzkan = Player(
    name="Luzkan"
    health=100,
    stamina=50,
    attack=7,
)

```





### Smelly

```py
datetime = datetime.datetime.now()
foo()
datetime_2 = datetime.datetime.now()


```

### Solution

```py
foo_bench_start_time = datetime.datetime.now()
foo()
foo_bench_end_time = datetime.datetime.now()
```



## Refactoring

- Extract Class
- Rename Method
- Rename Variable

---

#### Sources

- [[1](#sources)], [Origin] - William C. Wake, _"Refactoring Workbook"_ (2004)
