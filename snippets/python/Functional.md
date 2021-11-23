## Foldleft

```python
def fold_left(collection, init, op):
    accumulator = init
    [accumulator := op(accumulator, x) for x in collection]
    return accumulator
```
