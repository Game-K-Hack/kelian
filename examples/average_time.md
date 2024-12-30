# Examples Average Time

### Example 1

```python
at = AverageTime()
at.start("total")
at.start("task")
for i in range(100):
    # task
    at.loop("task")
at.stop("total")
print(at)
```
```txt
total: 0:00:03.454809
task : 0:00:00.034543
```
