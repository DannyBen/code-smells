# Uncommunicative Name

The name should convey meaning and meaning that is preferably not misleading ([Fallacious Method Name](./fallacious-method-name.md)). Descriptive names can save countless hours if they are good enough, just like a good abstract in a scientific article. The code should be as expressive as possible [[1](#sources)]. In the "Clean Code" by Robert Martin, this smell is "shredded" into five very descriptive smells and recommendations that underline the importance of having "good labels" [[2](#sources)]:

- [Obscured Intent](./obscured-intent.md),
- Function Names Should Say What They Do,
- Choose Descriptive Names,
- Unambiguous Names,
- Names Should Describe Side-Effects

Martin Fowler added this smell under the name _"Mysterious Name"_ in his third edition of the Refactoring book, saying that a good name, with much thought put into its definition, can save hours of incomprehensibility problems later. He says that titles should communicate what they do and how to use them.

## Causation

People tend not to return to the names of the variables or methods that they have already declared. Usually, it is the best they can come up with at the declaration moment, but maybe later on, there could have been a much better name for the thing thought of. The names could also be short, and the developer could be afraid of making them longer, thus cutting off the meaning potential.

## Problems

### **Comprehensibility**

Good names are one of the most critical factors contributing to the Clean Code feeling. If the developer can not rely on the naming of variables, methods, and classes, it drastically reduces his ability to understand everything.

## Examples



### Smelly

```py
data = m1.get_f()
data_2 = m2.get_f()

value = data_2['dmg'] * data['def']
val = math.rand(value-3, value+3)
```

### Solution

```py
def wobble_the_value(value: int, wobble_by: int):
    """ Adds tiny bit of randomness to the output """
    return math.rand(value-wobble_by, value+wobble_by)

attack_information: FightingInformation = attacking_minion.get_fighting_information()
defense_information: FightingInformation = defending_minion.get_fighting_information()

calculated_damage: int = attack_information.damage * defense_information.defense
final_damage_dealt: int = wobble_the_value(calculated_damage, wobble_by=3)
```



## Refactoring

- Change Method Declaration
- Rename Variable
- Rename Field

#### Sources

- [[1](#sources)] - Robert Martin, _"Clean Code: A Handbook of Agile Software Craftsmanship"_ (2008)
- [[2](#sources)] - Eessaar, E., Käosaar, E., +"On finding model smells based on code smells"\_ (2018)
- [Origin] - William C. Wake, _"Refactoring Workbook"_ (2004)
