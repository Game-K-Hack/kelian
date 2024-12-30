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

### Example 3: Multi replace

```python
from kelian import multi_replace

texte = "aaabbc"
resultat = multi_replace(texte, ("a", "1"), ("b", "2"))
print(resultat) # Affiche "11122c"

resultat = multi_replace(texte, ("a", "1", 1), ("b", "2"))
print(resultat) # Affiche "1aa22c"

resultat = multi_replace(texte, ("a", "1", "b", "2"))
print(resultat) # Affiche "11122c"
```

### Example 4: Milti replace by one
```python
from kelian import multi_replace_by_one

texte = "bonjour, ça va ?"
print(multi_replace_by_one(txt, ("o", "a", "u"), "")) # Affiche "bnjr, ç v ?"
```

### Example 5: While replace

```python
from kelian import while_replace

texte = "bonjour,   ça  va       ?"
resultat = while_replace(texte, "  ", " ")
print(resultat) # Affiche "bonjour, ça va ?"
```
