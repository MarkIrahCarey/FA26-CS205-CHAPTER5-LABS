# General Instructions

Like always, each Lab should have the following header:
```
"""
Author: Your Name
Date: Today's Date/Due Date
FileName: The File's Name
Purpose: What the program is about
"""
```

---

## Lab 5a: Typhoon Tracker!

You're a meteorologist working at the National Weather Service in Guam. Your job is to check if there's enough ocean energy for a typhoon to form near Guam. If there is, you need to warn the island!

GPI (Genesis Potential Index) is a score from 0-100 that tells you how likely a typhoon is to form:

Below is the ranges of GPI:

| GPI Range | Risk Level | Color | Meaning | Action Required |
|-----------|------------|-------|---------|-----------------|
| **0-20** | Very Low | 🔵 Blue | No typhoon formation expected | None |
| **21-40** | Low | 🟢 Green | Very unfavorable conditions | Monitor once daily |
| **41-50** | Moderate-Low | 🟡 Yellow | Slightly favorable | Monitor every 12 hours |
| **51-60** | Moderate | 🟠 Orange | Favorable conditions | Monitor every 6 hours |
| **61-70** | Moderate-High | 🟤 Brown | Very favorable | Issue advisory |
| **71-80** | High | 🔴 Red | Highly favorable | Issue warning |
| **81-90** | Very High | 🟣 Purple | Extremely favorable | Issue alert |
| **91-100** | Extreme | ⚫ Black | Almost certain formation | Emergency notification |

Given the following GPI 2D list, your job is to print the grid of colors for the GPI. Note that Guam is in column 4, row 5, so instead of the color, please put 🏝️ instead.

```
gpi_grid = [
    [15, 18, 22, 25, 28, 30, 32, 28, 24, 20],  # 0°N
    [18, 22, 28, 32, 35, 38, 40, 36, 30, 25],  # 3.3°N
    [22, 28, 35, 40, 45, 48, 50, 45, 38, 32],  # 6.7°N
    [28, 35, 42, 48, 55, 58, 60, 55, 45, 38],  # 10°N
    [32, 40, 48, 55, 65, 68, 70, 65, 55, 45],  # 13.3°N (Guam row!)
    [35, 45, 55, 62, 72, 78, 80, 75, 65, 55],  # 16.7°N
    [38, 48, 58, 68, 78, 85, 88, 85, 75, 62],  # 20°N
    [35, 45, 55, 65, 75, 80, 82, 80, 70, 58],  # 23.3°N
    [30, 38, 48, 58, 68, 72, 75, 72, 62, 52],  # 26.7°N
    [25, 32, 40, 48, 55, 58, 60, 58, 50, 42]   # 30°N
]

longitudes = [124, 131, 137, 144, 151, 157, 164, 171, 177, 180]  # °E
```

When mapping the colors, you should get the following:
```
       120E 127E 133E 140E 147E 153E 160E 167E 173E 180E
    0N  🔵   🔵   🟢   🟢   🟢   🟢   🟢   🟢   🟢   🔵
  3.3N  🔵   🟢   🟢   🟢   🟢   🟢   🟢   🟢   🟢   🟢
  6.7N  🟢   🟢   🟢   🟢   🟡   🟡   🟡   🟡   🟢   🟢
   10N  🟢   🟢   🟡   🟡   🟠   🟠   🟠   🟡   🟡   🟢
 13.3N  🟢   🟢   🟡   🏝️   🟤   🟤   🟤   🟤   🟠   🟡
 16.7N  🟢   🟡   🟠   🟤   🔴   🔴   🔴   🔴   🟤   🟠
   20N  🟢   🟡   🟠   🟤   🔴   🟣   🟣   🟣   🔴   🟤
 23.3N  🟢   🟡   🟠   🟤   🔴   🔴   🔴   🔴   🟤   🟠
 26.7N  🟢   🟢   🟡   🟠   🟤   🔴   🔴   🔴   🟤   🟠
   30N  🟢   🟢   🟢   🟡   🟠   🟠   🟠   🟠   🟡   🟡
```

### Your task:

- Create a program `typhoon_tracker.py` where it takes a 2D list and converts the GPI numbers to its respective colors. You do not need to create a function, loops and coditions are fine.

Recommended functions/methods: 
There are many ways to do this.

You can create a function that takes in the GPI number and returns the color. 

```python
def gpi_color(gpi_num):
  color = "" # change this to the correct color
  # do something with gpi_num to get the color

  return color # return the color
```

For traversing through the list, you can do the following:

- Access each row, then loop through the row and find the color. Store this in a temporary list. Once you go through the row, append into an empty list that holds all the colors.

```
_2D_List_colors = []
for row in gpi_grid:
  # create a temporary list
  temp_row = []
  # do something with row, store color using temp_row.append()
    .
    .
    .
  # then append the temp_row into _2D_List_colors
  _2D_List_colors.append(temp_row)
```
- Create a nested for loop that goes through the rows and columns.

```
for row in range(len(gpi_grid)):
  for col in range (len(gpi_grid[row])):
    # do something here by accesing gpi_grid[row][col]
```

If you are using a 2D list to store all the colors, you can change the location for Guam using:
```
name_of_your_2Dlist_of_colors[4][3] = "🏝️" 
```

---

## Lab5b: `my_range()` function

We are now all familiar with python's `range()` function and we use this in conjuction with for loops.

For this part, you are going to implement the features of range but as your own!

Implement the following function:

- `my_range()` should take a list with at least a length of 1 and at most a length of 3. If the range does not reach this interval, return an empty list.
- If the user enters a list of length 1, then return a list starting from 0 incrementing to the entered parameter. If the number is negative, return an empty list.
- If the user enters a list of length 2, then return a list starting from the first parameter, incrementing to the second parameter. If start is not strictly less than stop, return an empty list. 
- If the user enters a list of length 3, then return a list starting from the first parameter, incrementing based on the third parameter, ending before the second parameter (the last value is the largest value strictly less than the second parameter). If start is not strictly less than stop (with a positive step), return an empty list. You must also do the same but for a negative step. 
- Check for other cases:
    - If they enter a step of zero, return an empty list
    - For a list of 1 or 2, assume the step is 1.

### Your task:
Create a program called `my_range.py` where you recreate the function `range()` called `my_range(input)` where input is a list.
Suppose that the user entered some start, stop, and step. It must have the following behavior:
- Entering `my_range([start])` should return a list from 0 to start. If its negative or a length not between 1 and 3, return an empty list.
- Entering `my_range([start, stop])` should return a list from start to stop. If start is less than stop or if the length is not between 1 and 3, return an empty list.
- Entering `my_range([start, stop, step])` should return a list from start to stop, incrementing based on step. It should have both positive and negative step functionality. 

**DO NOT USE THE RANGE() FUNCTION TO CREATE YOUR LISTS**. Instead use while loops.


Please use the test case below to cover everything.
Test cases:

When you call each function:
```python
print(my_range([3]))
print(my_range([0]))
print(my_range([-1]))

print(my_range([14, 19]))
print(my_range([5, 5]))
print(my_range([7, 3]))

print(my_range([3, 30, 3]))
print(my_range([10, 0, -2]))
print(my_range([0, 10, 0]))
print(my_range([5, 0, 1]))

print(my_range([1, 2, 3, 4]))
```

Output:
```
[0, 1, 2]
[]
[]
[14, 15, 16, 17, 18]
[]
[]
[3, 6, 9, 12, 15, 18, 21, 24, 27]
[10, 8, 6, 4, 2]
[]
[]
[]
```


---

## Lab 5c: Grade curver

Suppose that you are a professor and your class just took an exam. It seemed that your exam was a little harder than you expected so as a way to help the students, you want to curve their grades. 

The following below is the curving algorithm:

- Normalize each grade by rewriting the grades between 0 to 1.
- After normalizing, square root each grade then round to the nearest 2 decimals. This would be our boosted score. We do this as the square root of a fraction less than 1 has diminishing returns. Lower scores jump higher while higher scores get smaller jumps.
- After obtaining each score, we must rescale them back. To rescale, follow the formula below:

$ min(\text{boosted} * 110 + \text{normalized score}, 110)$

Note: The professor did have extra credit, but only up to 10 points. So any student with a score over 110, must stay below that. 

### Your task:

Create a program called `grade_curver.py`. Ensure the program has two helper functions `normalize_scores(grades)`, `get_boosted_scores(norm_grades)`, and a `curve_grades(grades)`, where grades, norm_grades, are all a list of some `n` length. Each function must return a list of the following steps above. 

You must also create a `analyze(previous, adjusted)` function that takes in the previous and adjusted scores and prints a dictionary of the number of scores, average score, lowest grade, and highest grade of both inputs.

You may assume that the grades are all valid, ranging from 0 to 110.

Please use these list of grades:
```python
list_of_grades = [87, 44, 46, 50, 78, 57, 97, 56, 64, 80, 
                  86, 46, 97, 102, 103, 104, 82, 70, 60, 60, 
                  101, 85, 50, 59, 85, 81, 90, 82, 69, 76, 108, 
                  108, 42, 93, 86, 64, 67, 75, 52, 92, 103, 71, 
                  55, 99, 81, 73, 54, 59, 48, 100]
```

The following below is a sample output given the grades above:

```
List of Grades: [87, 44, 46, 50, 78, 57, 97, 56, 64, 80, 86, 46, 97, 102, 103, 104, 82, 70, 60, 60, 101, 85, 50, 59, 85, 81, 90, 82, 69, 76, 108, 108, 42, 93, 86, 64, 67, 75, 52, 92, 103, 71, 55, 99, 81, 73, 54, 59, 48, 100]
Curved Grades: [99, 70, 72, 75, 93, 80, 104, 79, 84, 95, 98, 72, 104, 107, 107, 108, 96, 88, 82, 82, 106, 97, 75, 81, 97, 95, 100, 96, 88, 92, 110, 110, 68, 102, 98, 84, 86, 92, 76, 101, 107, 89, 78, 105, 95, 90, 78, 81, 73, 106]
{'Scores': 50, 'Average': 75.54, 'Lowest': 42, 'Highest': 108}
{'Scores': 50, 'Average': 91.02, 'Lowest': 68, 'Highest': 110}
```

---

## Lab 5d: [Part 1] RPG Level up and and use item manager

RPG stands for Role-Playing Game. In an RPG, you take on the role of a character "class" (like a Warrior, Mage, or Rogue) and go on adventures. 

Your character has stats (like strength, health, and level), gains experience points (EXP), encounter and defeat enemies, and levels up to become stronger. 

You can also collect and use items (like apples or health potions) to heal yourself during battles. 

The goal is to make strategic decisions like which stat to increase when you level up, or when to use a healing item during battle to defeat enemies and progress through the game.

Throughout this lab, you will create a simple RPG by creating functions that handles the following:
- A function that handles leveling when a player levels up
- A function for using items in battle
- A function for random encounters
- A function that handles combat (simplified)

For Part 1, you will do the first two, and for Part 2, you will do the last two. 

The player will be the following dictionary. Please use this when testing your functions.
```
player = {"class" : "Warrior", 
          "level" : 20,
          "current_exp" : 1374,
          "current_health" : 400,
          "max_health" : 520,
          "attributes" : [10, 4, 2, 9, 6, 7], # STR, INT, DEX, VIT, CON, CHR
          "inventory" : [["apple", 10], ["health potion", 3], ["key", 1], ["stick", 1]]}
```

##### Function one, `level_manager(player)`
The first function relates with the leveling system. Lets call it `level_manager(player)` where player is a dictionary.
- Check if the player is close to leveling up by checking thier current exp. 
- If their exp is over the the exp to next level:
  - Subtract the current exp by the exp to next level 
  - Level up the character, then prompt the user to ask what attribute they want to level up by one point!

To keep track of levels and when they level up, please use this formula:
EXP_TO_NEXT_LVL $= 100 × 1.3^{(level-1)}$

Here is a sample:
```
Level up! You are now level 21!
Current attributes: STR=10, INT=4, DEX=2, VIT=9, CON=6, CHR=7
Which attribute would you like to increase? (STR/INT/DEX/VIT/CON/CHR): STR
STR increased to 11!
```

##### Function two, `use_item(player, item_name)`
This function allows the player to use items from their inventory:

To make things simple, lets only look at two items
Item effects:
- `"apple"`: Restore 50 health (cannot exceed max health)
- `"health_potion"`: Restore 100 health + 10% of their max health (cannot exceed max health)

During combat, if a player uses an item, update the count of said item accordingly and return a message describing what happened. 

If there is zero of the item, tell the user they cannot use the item, they don't have any. 

For example:
```
# Assuming max_health = 520 and current health is 400
use_item(player, "apple")
# Returns: "Used apple! Restored 50 HP. Current health: 450/520"

use_item(player, "health_potion")  
# Returns: "Used health potion! Restored 120 HP. Current health: 520/520"
``` 

Please name the file `rpg_base.py`.


---