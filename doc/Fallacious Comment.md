# Fallacious Comment

_Comments_ differ from most other syntaxes available in programming languages; it is not executed. This might lead to situations where, after code rework, the comments around it were left intact and no longer true to what they described. First and foremost, this situation should not even happen, as good comments from the _**"Why"** Comment_ family are not susceptible to this situation. If the comment explained **"what"** was happening, then it will be relevant as long as the code it explains is intact. Of course, ["What" Comments](./what-comment.md) are a Code Smell themselves, and so is [Duplicated Code](./duplicated-code.md).

This might generally happen within docstrings in real-life scenarios, which developers usually find in methods exposed to other users.

## Causation

The developer was in a hurry and did not double-check that everything was up-to-date after the changes. A passing unit test could also reaffirm him - there is no practical automated way to check for the correctness of comments/docstrings.

## Problems

### Decreased Readability

The developer does not know whether he should trust the method's signature or comment.

## Example



_["What" Comment](./what-comment.md)_ and _Fallacious Comment_.

### Smelly

```py
def rename_description(product, manufacturer):
    """
    Adds the manufacturer footer to the
    products description.
    """
    ...


```

### Solution

```py
def add_manufacturer_footer_to_product_description(product, manufacturer):
    ...
```



## Refactoring

- Remove Inconsistency

---

#### Sources

- [Origin] - Marcel Jerzyk, _"Code Smells: A Comprehensive Online Catalog and Taxonomy"_ (2022)
- [Parentage1] - Venera Arnaoudova, Massimiliano Di Penta, Giuliano Antoniol _"Linguistic Antipatterns: What they are and how developers perceive them"_ (2015)
- [Parentage2] - Martin Fowler, _"Refactoring: Improving the Design of Existing Code"_ (1999)
