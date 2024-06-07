# Combinatorial Explosion

The Combinatorial Explosion occurs when a lot of code does almost the same thing - here, the word "almost" is crucial. The number of cases needed to cover every possible path is massive, as is the number of methods. You can grasp a solid intuition of this smell by thinking about code blocks that differ from each other only by the quantities of data or objects used in them. Wake specifies that "(...) this is a relative of [Parallel Inheritance Hierarchies](./parallel-inheritance-hierarchies.md) Code Smell, but everything has been folded into one hierarchy." [[1](#sources)].

## Causation

Instead, what should be an independent decision, gets implemented via a hierarchy. Let us suppose that someone organized the code so that it queries an API by a specific method with specific set-in conditions and data. Sooner or later, there are just so many of these methods as the need for different queries increases in demand.

## Problems

### **Don't Repeat Yourself Principle Violation**

Introducing new functionality requires multiple versions to be introduced in various places.

### **Open-Closed Principle Violation**

Class is not closed for modification if it "prompts" the developer to add another `elif`.

## Example



### Smelly

```py
class Minion:
    name: str
    state: 'ready'

    def action(self):
        if self.state == 'ready':
            self.animate('standing')
        elif self.state == 'fighting':
            self.animate('fighting')
        elif self.state == 'resting':
            self.animate('resting')

    def next_state(self):
        if self.state == 'ready':
            return 'fighting'
        elif self.state == 'fighting':
            return 'resting'
        elif self.state == 'resting':
            return 'ready'

    def animate(self, animation: str):
        print(f"{self.name} is {animation}!")

```

### Solution

```py
class State(ABC):
    @abstractmethod
    def next() -> State:
        """ Return next State """

    @abstractmethod
    def animate() -> str:
        """ Returns a text-based animation """

class Ready(State):
    def next():
        return States.FIGHT

    def animate():
        return 'standing'

class Fight(State):
    def next():
        return States.REST

    def animate():
        return 'fighting'

class Rest(State):
    def next():
        return States.READY

    def animate():
        return 'resting'

class States(Enum):
    READY: State = Ready
    FIGHT: State = Fight
    REST: State = Rest

class Minion:
    name: str
    state: State = States.Ready

    def action(self):
        self.state.animate()

    def next_state(self):
        self.state = self.state.next()

    def animate(self, animation: str):
        print(f"{self.name} is {self.state.animate()}!")
```



## Refactoring

- Replace Inheritance with Delegation
- Tease Apart Inheritance
- It's pretty hard to fix, as the existence of this Code Smell (Design Smell) occurs as soon as the system's design is decided.

#### Sources

- [[1](#sources)], [Origin] - William C. Wake, _"Refactoring Workbook"_ (2004)
