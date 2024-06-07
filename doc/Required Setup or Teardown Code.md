# Required Setup or Teardown Code

If, after the use of a class or method, several lines of code are required to:

- set it properly up,
- the environment requires specific actions beforehand or after its use,
- clean up actions are required,

then there is a _Required Setup or Teardown Code_ code smell. Furthermore, this
may indicate [improper abstraction level](Dubious%20Abstraction.md).

## Causation

Some functionality was taken beyond the class during development, and the need
for their use within the class itself was overlooked.

## Problems

### Lack of Cohesion

Class can't be reused by itself - it requires extra lines of code outside of its
scope to use it.

## Examples



### Smelly

```py
class Radio:
    def __init__(self, ip, port):
        socket = socket.connection(f"{ip}:{port}")

    ...

radio: Radio = Radio(ip, port)
...
# Doing something with the object
...
# Finalizing its use
radio.socket.shutdown(socket.shut_RDWR)
radio.socket.close()
...
```

### Solution

```py
class Radio:
    def __init__(self, ip, port):
        socket = socket.connection(f"{ip}:{port}")

    def __del__(self):
        def graceful_shutdown():
            self.socket.shutdown(socket.shut_RDWR)
            self.socket.close()

        graceful_shutdown()
        super().__del__()

    ...

radio: Radio = Radio(ip, port)
...
# Doing something with the object
...
# Finalizing its use no longer requires manual socket closing
...
```



## Refactoring

- Replace Constructor with Factory Method
- Introduce Parameter Object

---

#### Sources

- [Origin] - Steve Smith, _"Refactoring Fundamentals"_ (2013)
