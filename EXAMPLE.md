# Other examples

It is possible to retrieve information about the computer in order to encrypt and decrypt messages, depending on the machine on which the script is run.

```python
from kelian import system
from kelian.utils import string2hash
from kelian.encryption import encrypt_by_character_manga, encrypt

processor = system.get_processor_details()[0]["name"]
motherboard = system.get_motherboard_details()[0]["product"]
gpu = system.get_gpu_details()[0]["name"]
monitor = str(len(system.get_monitor_details()))
cd_drive = str(len(system.get_cd_drive_details()))
mouse = str(len(system.get_mouse_details()))
speaker = str(len(system.get_speaker_details()))
keyboard = str(len(system.get_keyboard_details()))
hard_disk = str(len(system.get_hard_disk_details()))
ram = "".join([f"{i['manufacturer']}{i['capaity']}" for i in system.get_ram_details()])

hash_id = processor + motherboard + gpu + monitor + cd_drive + mouse + speaker + keyboard + hard_disk + ram
hash_id = string2hash(hash_id.replace(" ", ""), 'sha256')

data = encrypt("Secret", hash_id)
print(data)

data = encrypt_by_character_manga("Secret", hash_id)
print(data)
```

`hash_id` : `AMD Ryzen 9 5950XASUS ROG Strix X570-ENVIDIA GeForce RTX 3080112112Kingston34359738368Kingston34359738368`

**Encrypt**
```txt
cCé~ï~#
ïB9D
```

**Encrypt by character manga**
```txt
Magma
Yoki
Gotanda Taishi
Sharon        
Mitsuru       
Shiro
Kokuyô        
En Ô
Sharon        
Saitô Miyako  
Ochanomizu Ran
Isogai Yûma
```

You can customize the result of the calculation by using the `encrypt_by_list` function.

```python
KEYS = ["Aa", "Bb", "Cc", "Dd", "Ee", "Ff", "Gg", "Hh", "Ii", "Jj", "Kk", "Ll", "Mm", "Nn", "Oo", "Pp", "Qq", "Rr", "Ss", "Tt", "Uu", "Vv", "Ww", "Xx", "Yy", "Zz"]
data = encrypt_by_list("Scecret", "password", KEYS, "")
print(data)
```

**Encrypt**
```txt
NnUuNnVvOoJjOoXxPpKkNnVvPpHh
```
