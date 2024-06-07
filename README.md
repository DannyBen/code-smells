# Code Smells Reference

| Code Smell                                                                                             | Summary                                                                     |
|:-------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------|
| [doc/Afraid To Fail.md](Afraid%20To%20Fail)                                                                   | Reluctance to refactor due to fear of breaking the code.                    |
| [doc/Alternative Classes with Different Interfaces.md](Alternative%20Classes%20with%20Different%20Interfaces) | Classes that perform similar functions but have different interfaces.       |
| [doc/Base Class depends on Subclass.md](Base%20Class%20depends%20on%20Subclass)                               | A base class that relies on its subclasses, violating hierarchy principles. |
| [doc/Binary Operator in Name.md](Binary%20Operator%20in%20Name)                                               | Using binary operators in method or variable names, causing confusion.      |
| [doc/Boolean Blindness.md](Boolean%20Blindness)                                                               | Overuse of boolean parameters that make code difficult to understand.       |
| [doc/Callback Hell.md](Callback%20Hell)                                                                       | Excessive nesting of callbacks, making code hard to read and maintain.      |
| [doc/Clever Code.md](Clever%20Code)                                                                           | Code that is overly complex or tricky, making it hard to understand.        |
| [doc/Combinatorial Explosion.md](Combinatorial%20Explosion)                                                   | Rapidly increasing number of code paths due to combinations of conditions.  |
| [doc/Complicated Boolean Expression.md](Complicated%20Boolean%20Expression)                                   | Boolean expressions that are too complex and hard to understand.            |
| [doc/Complicated Regex Expression.md](Complicated%20Regex%20Expression)                                       | Regular expressions that are overly complex and hard to read.               |
| [doc/Conditional Complexity.md](Conditional%20Complexity)                                                     | Excessive use of complex conditional statements.                            |
| [doc/Data Clump.md](Data%20Clump)                                                                             | Grouping of related data items that should be in an object.                 |
| [doc/Dead Code.md](Dead%20Code)                                                                               | Code that is never executed or used.                                        |
| [doc/Divergent Change.md](Divergent%20Change)                                                                 | A class that is changed often for different reasons.                        |
| [doc/Dubious Abstraction.md](Dubious%20Abstraction)                                                           | Abstractions that are not useful or necessary.                              |
| [doc/Duplicated Code.md](Duplicated%20Code)                                                                   | Repetition of the same code in multiple places.                             |
| [doc/Fallacious Comment.md](Fallacious%20Comment)                                                             | Misleading or incorrect comments in the code.                               |
| [doc/Fallacious Method Name.md](Fallacious%20Method%20Name)                                                   | Method names that do not accurately describe their functionality.           |
| [doc/Fate over Action.md](Fate%20over%20Action)                                                               | Code that reacts to states rather than actions, reducing clarity.           |
| [doc/Feature Envy.md](Feature%20Envy)                                                                         | Methods that access data of other objects excessively.                      |
| [doc/Flag Argument.md](Flag%20Argument)                                                                       | Boolean arguments that control method behavior, making it less clear.       |
| [doc/Global Data.md](Global%20Data)                                                                           | Use of global variables that can be modified from anywhere.                 |
| [doc/Hidden Dependencies.md](Hidden%20Dependencies)                                                           | Dependencies that are not obvious or well-documented.                       |
| [doc/Imperative Loops.md](Imperative%20Loops)                                                                 | Use of traditional loops instead of more declarative constructs.            |
| [doc/Inappropriate Static.md](Inappropriate%20Static)                                                         | Overuse of static methods or variables, reducing flexibility.               |
| [doc/Incomplete Library Class.md](Incomplete%20Library%20Class)                                               | Library classes that lack necessary functionality.                          |
| [doc/Inconsistent Names.md](Inconsistent%20Names)                                                             | Using different names for the same concept.                                 |
| [doc/Inconsistent Style.md](Inconsistent%20Style)                                                             | Variations in coding style within the same codebase.                        |
| [doc/Indecent Exposure.md](Indecent%20Exposure)                                                               | Exposing too much of the internal details of a class.                       |
| [doc/Insider Trading.md](Insider%20Trading)                                                                   | Classes that know too much about each other’s internal workings.            |
| [doc/Large Class.md](Large%20Class)                                                                           | Classes that have grown too large and do too much.                          |
| [doc/Lazy Element.md](Lazy%20Element)                                                                         | Elements that are not fulfilling their responsibilities.                    |
| [doc/Long Method.md](Long%20Method)                                                                           | Methods that are too long and complex.                                      |
| [doc/Long Parameter List.md](Long%20Parameter%20List)                                                         | Methods with too many parameters, making them hard to understand.           |
| [doc/Magic Number.md](Magic%20Number)                                                                         | Using literal numbers in code instead of named constants.                   |
| [doc/Message Chain.md](Message%20Chain)                                                                       | A sequence of method calls forming a chain, increasing coupling.            |
| [doc/Middle Man.md](Middle%20Man)                                                                             | Classes that add little value and simply delegate work.                     |
| [doc/Mutable Data.md](Mutable%20Data)                                                                         | Data that can be changed unexpectedly, leading to bugs.                     |
| [doc/Null Check.md](Null%20Check)                                                                             | Excessive null checks indicating poor design.                               |
| [doc/Obscured Intent.md](Obscured%20Intent)                                                                   | Code that does not clearly convey its purpose.                              |
| [doc/Oddball Solution.md](Oddball%20Solution)                                                                 | Unique solutions to problems that deviate from common practices.            |
| [doc/Parallel Inheritance Hierarchies.md](Parallel%20Inheritance%20Hierarchies)                               | Inheritance hierarchies that mirror each other and complicate maintenance.  |
| [doc/Primitive Obsession.md](Primitive%20Obsession)                                                           | Overuse of primitives instead of small objects for simple tasks.            |
| [doc/Refused Bequest.md](Refused%20Bequest)                                                                   | Subclasses that do not use inherited methods or properties.                 |
| [doc/Required Setup or Teardown Code.md](Required%20Setup%20or%20Teardown%20Code)                             | Code that requires specific setup or teardown to function correctly.        |
| [doc/Shotgun Surgery.md](Shotgun%20Surgery)                                                                   | Making a small change requires altering many different parts of the code.   |
| [doc/Side Effects.md](Side%20Effects)                                                                         | Methods that alter state or have effects beyond their scope.                |
| [doc/Special Case.md](Special%20Case)                                                                         | Code handling specific cases instead of generalizing the solution.          |
| [doc/Speculative Generality.md](Speculative%20Generality)                                                     | Adding features that might be useful in the future but are not needed now.  |
| [doc/Status Variable.md](Status%20Variable)                                                                   | Variables that track the state of an object, complicating logic.            |
| [doc/Temporary Field.md](Temporary%20Field)                                                                   | Fields that are only set in certain circumstances.                          |
| [doc/Tramp Data.md](Tramp%20Data)                                                                             | Data passed through many methods without being used.                        |
| [doc/Type Embedded in Name.md](Type%20Embedded%20in%20Name)                                                   | Including type information in variable or method names unnecessarily.       |
| [doc/Uncommunicative Name.md](Uncommunicative%20Name)                                                         | Names that do not clearly describe their purpose.                           |
| [doc/Vertical Separation.md](Vertical%20Separation)                                                           | Separation of related code lines by unrelated lines, reducing readability.  |
| [doc/What Comment.md](What%20Comment)                                                                         | Comments that explain "what" the code does instead of "why".                |


Extracted from <https://github.com/Luzkan/smells>
