# Dead Code

If part of the code is not executed, it is a Dead Code. This code smell includes
any place that the code executor will never reach, including the code that was
commented out. Any if or case condition that cannot be reached, any code in
methods and functions after the final `return` statement, or any code inside a
`try` `except`/`catch` block that will never throw an error. [[1]
(#sources)] This usually is not that easy to detect and requires tool
assistance. [[2](#sources)]

## Causation

Never refactored [long else-if blocks](Conditional%20Complexity.md) eventually
have so many paths that no one even remembers if they are accessed anymore.
Perhaps a new way of working was introduced, and the old code was never cleaned
up.

## Problems

### **You Ain't Gonna Need It Principle Violation**

Old code that was not deleted but commented out _"just-in-case"_ is just
bloating the codebase.

## Refactoring

- Remove It

---

#### Sources

- [[1](#sources)] - Robert Martin, _"Clean Code: A Handbook of Agile Software Craftsmanship"_ (2008)
- [[2](#sources)], [Origin] - William C. Wake, _"Refactoring Workbook"_ (2004)
