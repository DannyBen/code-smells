# Code Smells Reference

| Code Smell                                                                                             | Summary                                                                     |
|:-------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------|
| [Afraid To Fail](doc/Afraid%20To%20Fail.md)                                                                   | Reluctance to refactor due to fear of breaking the code.                    |
| [Alternative Classes with Different Interfaces](doc/Alternative%20Classes%20with%20Different%20Interfaces.md) | Classes that perform similar functions but have different interfaces.       |
| [Base Class depends on Subclass](doc/Base%20Class%20depends%20on%20Subclass.md)                               | A base class that relies on its subclasses, violating hierarchy principles. |
| [Binary Operator in Name](doc/Binary%20Operator%20in%20Name.md)                                               | Using binary operators in method or variable names, causing confusion.      |
| [Boolean Blindness](doc/Boolean%20Blindness.md)                                                               | Overuse of boolean parameters that make code difficult to understand.       |
| [Callback Hell](doc/Callback%20Hell.md)                                                                       | Excessive nesting of callbacks, making code hard to read and maintain.      |
| [Clever Code](doc/Clever%20Code.md)                                                                           | Code that is overly complex or tricky, making it hard to understand.        |
| [Combinatorial Explosion](doc/Combinatorial%20Explosion.md)                                                   | Rapidly increasing number of code paths due to combinations of conditions.  |
| [Complicated Boolean Expression](doc/Complicated%20Boolean%20Expression.md)                                   | Boolean expressions that are too complex and hard to understand.            |
| [Complicated Regex Expression](doc/Complicated%20Regex%20Expression.md)                                       | Regular expressions that are overly complex and hard to read.               |
| [Conditional Complexity](doc/Conditional%20Complexity.md)                                                     | Excessive use of complex conditional statements.                            |
| [Data Clump](doc/Data%20Clump.md)                                                                             | Grouping of related data items that should be in an object.                 |
| [Dead Code](doc/Dead%20Code.md)                                                                               | Code that is never executed or used.                                        |
| [Divergent Change](doc/Divergent%20Change.md)                                                                 | A class that is changed often for different reasons.                        |
| [Dubious Abstraction](doc/Dubious%20Abstraction.md)                                                           | Abstractions that are not useful or necessary.                              |
| [Duplicated Code](doc/Duplicated%20Code.md)                                                                   | Repetition of the same code in multiple places.                             |
| [Fallacious Comment](doc/Fallacious%20Comment.md)                                                             | Misleading or incorrect comments in the code.                               |
| [Fallacious Method Name](doc/Fallacious%20Method%20Name.md)                                                   | Method names that do not accurately describe their functionality.           |
| [Fate over Action](doc/Fate%20over%20Action.md)                                                               | Code that reacts to states rather than actions, reducing clarity.           |
| [Feature Envy](doc/Feature%20Envy.md)                                                                         | Methods that access data of other objects excessively.                      |
| [Flag Argument](doc/Flag%20Argument.md)                                                                       | Boolean arguments that control method behavior, making it less clear.       |
| [Global Data](doc/Global%20Data.md)                                                                           | Use of global variables that can be modified from anywhere.                 |
| [Hidden Dependencies](doc/Hidden%20Dependencies.md)                                                           | Dependencies that are not obvious or well-documented.                       |
| [Imperative Loops](doc/Imperative%20Loops.md)                                                                 | Use of traditional loops instead of more declarative constructs.            |
| [Inappropriate Static](doc/Inappropriate%20Static.md)                                                         | Overuse of static methods or variables, reducing flexibility.               |
| [Incomplete Library Class](doc/Incomplete%20Library%20Class.md)                                               | Library classes that lack necessary functionality.                          |
| [Inconsistent Names](doc/Inconsistent%20Names.md)                                                             | Using different names for the same concept.                                 |
| [Inconsistent Style](doc/Inconsistent%20Style.md)                                                             | Variations in coding style within the same codebase.                        |
| [Indecent Exposure](doc/Indecent%20Exposure.md)                                                               | Exposing too much of the internal details of a class.                       |
| [Insider Trading](doc/Insider%20Trading.md)                                                                   | Classes that know too much about each other’s internal workings.            |
| [Large Class](doc/Large%20Class.md)                                                                           | Classes that have grown too large and do too much.                          |
| [Lazy Element](doc/Lazy%20Element.md)                                                                         | Elements that are not fulfilling their responsibilities.                    |
| [Long Method](doc/Long%20Method.md)                                                                           | Methods that are too long and complex.                                      |
| [Long Parameter List](doc/Long%20Parameter%20List.md)                                                         | Methods with too many parameters, making them hard to understand.           |
| [Magic Number](doc/Magic%20Number.md)                                                                         | Using literal numbers in code instead of named constants.                   |
| [Message Chain](doc/Message%20Chain.md)                                                                       | A sequence of method calls forming a chain, increasing coupling.            |
| [Middle Man](doc/Middle%20Man.md)                                                                             | Classes that add little value and simply delegate work.                     |
| [Mutable Data](doc/Mutable%20Data.md)                                                                         | Data that can be changed unexpectedly, leading to bugs.                     |
| [Null Check](doc/Null%20Check.md)                                                                             | Excessive null checks indicating poor design.                               |
| [Obscured Intent](doc/Obscured%20Intent.md)                                                                   | Code that does not clearly convey its purpose.                              |
| [Oddball Solution](doc/Oddball%20Solution.md)                                                                 | Unique solutions to problems that deviate from common practices.            |
| [Parallel Inheritance Hierarchies](doc/Parallel%20Inheritance%20Hierarchies.md)                               | Inheritance hierarchies that mirror each other and complicate maintenance.  |
| [Primitive Obsession](doc/Primitive%20Obsession.md)                                                           | Overuse of primitives instead of small objects for simple tasks.            |
| [Refused Bequest](doc/Refused%20Bequest.md)                                                                   | Subclasses that do not use inherited methods or properties.                 |
| [Required Setup or Teardown Code](doc/Required%20Setup%20or%20Teardown%20Code.md)                             | Code that requires specific setup or teardown to function correctly.        |
| [Shotgun Surgery](doc/Shotgun%20Surgery.md)                                                                   | Making a small change requires altering many different parts of the code.   |
| [Side Effects](doc/Side%20Effects.md)                                                                         | Methods that alter state or have effects beyond their scope.                |
| [Special Case](doc/Special%20Case.md)                                                                         | Code handling specific cases instead of generalizing the solution.          |
| [Speculative Generality](doc/Speculative%20Generality.md)                                                     | Adding features that might be useful in the future but are not needed now.  |
| [Status Variable](doc/Status%20Variable.md)                                                                   | Variables that track the state of an object, complicating logic.            |
| [Temporary Field](doc/Temporary%20Field.md)                                                                   | Fields that are only set in certain circumstances.                          |
| [Tramp Data](doc/Tramp%20Data.md)                                                                             | Data passed through many methods without being used.                        |
| [Type Embedded in Name](doc/Type%20Embedded%20in%20Name.md)                                                   | Including type information in variable or method names unnecessarily.       |
| [Uncommunicative Name](doc/Uncommunicative%20Name.md)                                                         | Names that do not clearly describe their purpose.                           |
| [Vertical Separation](doc/Vertical%20Separation.md)                                                           | Separation of related code lines by unrelated lines, reducing readability.  |
| [What Comment](doc/What%20Comment.md)                                                                         | Comments that explain "what" the code does instead of "why".                |


Extracted from <https://github.com/Luzkan/smells>
