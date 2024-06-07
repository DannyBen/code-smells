# Code Smells Reference

| Code Smell                                                                                             | Summary                                                                     |
|:-------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------|
| [Afraid To Fail](Afraid%20To%20Fail)                                                                   | Reluctance to refactor due to fear of breaking the code.                    |
| [Alternative Classes with Different Interfaces](Alternative%20Classes%20with%20Different%20Interfaces) | Classes that perform similar functions but have different interfaces.       |
| [Base Class depends on Subclass](Base%20Class%20depends%20on%20Subclass)                               | A base class that relies on its subclasses, violating hierarchy principles. |
| [Binary Operator in Name](Binary%20Operator%20in%20Name)                                               | Using binary operators in method or variable names, causing confusion.      |
| [Boolean Blindness](Boolean%20Blindness)                                                               | Overuse of boolean parameters that make code difficult to understand.       |
| [Callback Hell](Callback%20Hell)                                                                       | Excessive nesting of callbacks, making code hard to read and maintain.      |
| [Clever Code](Clever%20Code)                                                                           | Code that is overly complex or tricky, making it hard to understand.        |
| [Combinatorial Explosion](Combinatorial%20Explosion)                                                   | Rapidly increasing number of code paths due to combinations of conditions.  |
| [Complicated Boolean Expression](Complicated%20Boolean%20Expression)                                   | Boolean expressions that are too complex and hard to understand.            |
| [Complicated Regex Expression](Complicated%20Regex%20Expression)                                       | Regular expressions that are overly complex and hard to read.               |
| [Conditional Complexity](Conditional%20Complexity)                                                     | Excessive use of complex conditional statements.                            |
| [Data Clump](Data%20Clump)                                                                             | Grouping of related data items that should be in an object.                 |
| [Dead Code](Dead%20Code)                                                                               | Code that is never executed or used.                                        |
| [Divergent Change](Divergent%20Change)                                                                 | A class that is changed often for different reasons.                        |
| [Dubious Abstraction](Dubious%20Abstraction)                                                           | Abstractions that are not useful or necessary.                              |
| [Duplicated Code](Duplicated%20Code)                                                                   | Repetition of the same code in multiple places.                             |
| [Fallacious Comment](Fallacious%20Comment)                                                             | Misleading or incorrect comments in the code.                               |
| [Fallacious Method Name](Fallacious%20Method%20Name)                                                   | Method names that do not accurately describe their functionality.           |
| [Fate over Action](Fate%20over%20Action)                                                               | Code that reacts to states rather than actions, reducing clarity.           |
| [Feature Envy](Feature%20Envy)                                                                         | Methods that access data of other objects excessively.                      |
| [Flag Argument](Flag%20Argument)                                                                       | Boolean arguments that control method behavior, making it less clear.       |
| [Global Data](Global%20Data)                                                                           | Use of global variables that can be modified from anywhere.                 |
| [Hidden Dependencies](Hidden%20Dependencies)                                                           | Dependencies that are not obvious or well-documented.                       |
| [Imperative Loops](Imperative%20Loops)                                                                 | Use of traditional loops instead of more declarative constructs.            |
| [Inappropriate Static](Inappropriate%20Static)                                                         | Overuse of static methods or variables, reducing flexibility.               |
| [Incomplete Library Class](Incomplete%20Library%20Class)                                               | Library classes that lack necessary functionality.                          |
| [Inconsistent Names](Inconsistent%20Names)                                                             | Using different names for the same concept.                                 |
| [Inconsistent Style](Inconsistent%20Style)                                                             | Variations in coding style within the same codebase.                        |
| [Indecent Exposure](Indecent%20Exposure)                                                               | Exposing too much of the internal details of a class.                       |
| [Insider Trading](Insider%20Trading)                                                                   | Classes that know too much about each other’s internal workings.            |
| [Large Class](Large%20Class)                                                                           | Classes that have grown too large and do too much.                          |
| [Lazy Element](Lazy%20Element)                                                                         | Elements that are not fulfilling their responsibilities.                    |
| [Long Method](Long%20Method)                                                                           | Methods that are too long and complex.                                      |
| [Long Parameter List](Long%20Parameter%20List)                                                         | Methods with too many parameters, making them hard to understand.           |
| [Magic Number](Magic%20Number)                                                                         | Using literal numbers in code instead of named constants.                   |
| [Message Chain](Message%20Chain)                                                                       | A sequence of method calls forming a chain, increasing coupling.            |
| [Middle Man](Middle%20Man)                                                                             | Classes that add little value and simply delegate work.                     |
| [Mutable Data](Mutable%20Data)                                                                         | Data that can be changed unexpectedly, leading to bugs.                     |
| [Null Check](Null%20Check)                                                                             | Excessive null checks indicating poor design.                               |
| [Obscured Intent](Obscured%20Intent)                                                                   | Code that does not clearly convey its purpose.                              |
| [Oddball Solution](Oddball%20Solution)                                                                 | Unique solutions to problems that deviate from common practices.            |
| [Parallel Inheritance Hierarchies](Parallel%20Inheritance%20Hierarchies)                               | Inheritance hierarchies that mirror each other and complicate maintenance.  |
| [Primitive Obsession](Primitive%20Obsession)                                                           | Overuse of primitives instead of small objects for simple tasks.            |
| [Refused Bequest](Refused%20Bequest)                                                                   | Subclasses that do not use inherited methods or properties.                 |
| [Required Setup or Teardown Code](Required%20Setup%20or%20Teardown%20Code)                             | Code that requires specific setup or teardown to function correctly.        |
| [Shotgun Surgery](Shotgun%20Surgery)                                                                   | Making a small change requires altering many different parts of the code.   |
| [Side Effects](Side%20Effects)                                                                         | Methods that alter state or have effects beyond their scope.                |
| [Special Case](Special%20Case)                                                                         | Code handling specific cases instead of generalizing the solution.          |
| [Speculative Generality](Speculative%20Generality)                                                     | Adding features that might be useful in the future but are not needed now.  |
| [Status Variable](Status%20Variable)                                                                   | Variables that track the state of an object, complicating logic.            |
| [Temporary Field](Temporary%20Field)                                                                   | Fields that are only set in certain circumstances.                          |
| [Tramp Data](Tramp%20Data)                                                                             | Data passed through many methods without being used.                        |
| [Type Embedded in Name](Type%20Embedded%20in%20Name)                                                   | Including type information in variable or method names unnecessarily.       |
| [Uncommunicative Name](Uncommunicative%20Name)                                                         | Names that do not clearly describe their purpose.                           |
| [Vertical Separation](Vertical%20Separation)                                                           | Separation of related code lines by unrelated lines, reducing readability.  |
| [What Comment](What%20Comment)                                                                         | Comments that explain "what" the code does instead of "why".                |


Extracted from <https://github.com/Luzkan/smells>
