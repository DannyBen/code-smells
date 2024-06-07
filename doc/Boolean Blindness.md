# Boolean Blindness

In the Haskell community, there is a well-(un)known question about the filter function - does the filter predicate means to `TAKE` or to `DROP` (check [example](#example))? Boolean Blindness smell occurs in a situation in which a function or method that operates on `bool`-s destroys the information about what _boolean_ represents. It would be much better to have an expressive equivalent of type _boolean_ with appropriate names in these situations. For the filter function, it could be of type `Keep` defined as `Keep = Drop | Take`.

This smell is in the same family as [Uncommunicative Names](./uncommunicative-name.md) and [Magic Numbers](./magic-number.md).

## Problems

### Comprehensibility

Neither in real life one can answer just _yes_/_no_ without ever confusing interlocutor to every single closed question that may possible.

## Example



### Ambiguity of Boolean

```hs
data Bool = False | True
filter :: (a -> Bool) -> [a] -> [a]
```

### Meaningful Boolean

```hs
data Keep = Drop | Take
filter :: (a -> Keep) -> [a] -> [a]
```



## Refactoring

- Introduce New Type

---

#### Sources

- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
