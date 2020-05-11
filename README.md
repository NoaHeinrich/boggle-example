# boggle-example
```python
import random 
import string
class BoggleBoard:
  
  def __init__(self):
    self.grid = [['_','_','_','_'],['_','_','_','_'],['_','_','_','_'], ['_','_','_','_']]

  def __str__(self):
    return_string = ""
    for array in self.grid:
      for char in array:
        if char == "Qu":
          return_string += " Qu"
        else:
          return_string += f" {char} "
      return_string += '\n'
    return return_string

  def shake(self):
    dice_strings = [
      "AAEEGN",
      "ELRTTY",
      "AOOTTW",
      "ABBJOO",
      "EHRTVW",
      "CIMOTU",
      "DISTTY",
      "EIOSST",
      "DELRVY",
      "ACHOPS",
      "HIMNQU",
      "EEINSU",
      "EEGHNW",
      "AFFKPS",
      "HLNNRZ",
      "DEILRX"
    ]
    random.shuffle(dice_strings)
    for array in self.grid:
      for i in range(4):
        die = Die(dice_strings.pop())
        die.roll()
        array[i] = die.side_up
    
class Die:
  def __init__(self, string):
    self.string = string
    self.side_up = ""

  def roll(self):
    self.side_up = random.choice(self.string)
    if self.side_up == "Q":
      self.side_up = "Qu"






```
