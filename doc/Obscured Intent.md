# Obscured Intent

The [Obscured Intent](Obscured%20Intent.md) Code Smell, initially proposed by
Robert Martin in _"Clean Code"_ [[37](#sources)]), is cross-smelly with other
smells in the **Obfuscators** category. When
[Uncommunicative Names](Uncommunicative%20Name.md)/[Numbers](Magic%20Number.md)
are placed within a [Vertically Separated Space](Vertical%20Separation.md)
hiding an [Imperative Loop](Imperative%20Loops.md) with a
[What Comment](What%20Comment.md) explanation on top of that, then the
[Obscured Intent](Obscured%20Intent.md) is going to be caught quite easily by
intuition or by metrics of other smells.

The code should be as expressive as possible [[1](#sources)]). Robert Martin
gives an example of an utterly unreadable
[overtime function](#Obscured%20Intent.md) noting that even if the code is
small and compact, it may still be tragic. In this case, correcting the
[Uncommunicative Names](Yncommunicative%20Name.md)/[Numbers](Magic%20Number.md)
would probably do the trick to make that snippet of code much more fragrant.

There is a famous real-world example of an Obscured Intent. In the _Quake 3:
Arena_ [fast inverse square root](#example-1), the problem is with the
[Uncommunicative Naming](Uncommunicative%20Name.md),
[What Comments](What%20Comment.md), [Dead Code](Dead%20code.md), and
[Magic Numbers](Magic%20Number.md). I will also point out that games have a
slightly different specificity for their industry. Usually, the code out there
is very confusing, and priorities are not put on things such as reusability, so
there is a lot to explore.

## Causation

Sometimes, a developer can forget that something that seems evident to him is
not as clear to other developers. There may also be cases where the developer
intentionally compacts the code to appear brighter by making it more
mysterious.

## Problems

### Comprehensibility Issues

Code does not convey meaning and thus is not understandable. It may be a
considerable time waste if someone ever has to touch parts of the code that
interact with an _obscure intent_ piece of code.

## Example



### Smelly

An example given by Robert Martin.

```py
def m_ot_calc() -> int:
    return i_ths_wkd * i_ths_rte \
        + round(0.5 * i_ths_rte *
        max(0, i_ths_wkd - 400))
```





### Smelly

Quake 3 Arena Fast Inverse Square Root

```c++
float Q_rsqrt( float number )
{
        long i;
        float x2, y;
        const float threehalfs = 1.5F;

        x2 = number * 0.5F;
        y  = number;
        i  = * ( long * ) &y;                       // evil floating point bit level hacking
        i  = 0x5f3759df - ( i >> 1 );               // what the f*ck?
        y  = * ( float * ) &i;
        y  = y * ( threehalfs - ( x2 * y * y ) );   // 1st iteration
//      y  = y * ( threehalfs - ( x2 * y * y ) );   // 2nd iteration, this can be removed

        return y;
}
```



## Refactoring

- Remove the code smells that cause _Obscure Intent_

---

#### Sources

- [[1](#sources)], [Origin] - Robert C. Martin, _"Clean Code: A Handbook of Agile Software Craftsmanship"_ (2008)
