---
{"dg-publish":true,"permalink":"/Code for Dice Rolls/","tags":["coding"]}
---


---
# Code for Dice Rolls
We can use the Random Library for a Dice Roll! 
```Python
import random

def diceD8():
	d8 = random.choice(["1", "2", "3", "4", "5", "6", "7", "8"])
	# OR
	d8 = random.randint(1, 8)
	# OR
	d8_list = ["1", "2", "3", "4", "5", "6", "7", "8"]
	d8 = random.shuffle(d8_list)
	print()
	print(d8)
	print() # Empty print statements so that numbers are clearly visible.
# Similarly we can now do this for d2, d4, d6, d10, d12 and d20.
```

---
# Footnotes