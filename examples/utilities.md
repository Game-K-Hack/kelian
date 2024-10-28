# Examples Utilities

### Example 1: Hash

```python
from kelian import string2hash

# Generate a sha256 hash from a string
hashed_string = string2hash("password123")
print(hashed_string)
```

### Example 2: Fix encoding

```python
from kelian import fix_encoding

text = fix_encoding("PrÃƒÂ©nom")
print(text)
```
