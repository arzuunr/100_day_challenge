# 101 Coding

## *Tips*

-Books are good as references. If you want to dive deep into delegates and protocols read that chapter, when it comes to learning; hands on project is the best.

-Being a copycat if you have no idea for a project at first.

-Find a code mentor.

-There' always a bug.

-Never a copy paste a code that you didnt undertsand completely.

-Always go with 2 screen. 

### **Day 1: Python Basics - Band Name Generator**  

| Category              | Takeaways                                                                 | Code Example/Solution                          |
|-----------------------|---------------------------------------------------------------------------|-----------------------------------------------|
| **Printing**          | `print()` outputs text to console. Use f-strings for dynamic values.      | `print(f"Hello, {name}!")`                    |
| **Input**            | `input()` captures user input (always returns a string).                  | `city = input("Your city: ")`                 |
| **Variables**        | Store data with meaningful names. Python is dynamically typed.            | `pet_name = "Whiskers"`                       |
| **String Manipulation/Concatenation** | Concatenate with `+` or `,` in `print()`. Format with f-strings.         | `print(city + " " + pet_name)`                |
| **Debugging**        | Common errors: `NameError` (undefined var), `SyntaxError` (typos).        | Fix: Check variable names/brackets.           |
| **Indentation**      | Python uses indentation (4 spaces) for code blocks.                       | ```python<br>if True:<br>    print("Indented!")``` |
| **Variable Swapping** | Pythonic way: `a, b = b, a`. No temp variable needed.                    | `x, y = y, x`                                |
| **Comments**         | Use `#` for single-line explanations. Avoid obvious comments.             | `# Calculate total (avoid: "This adds x+y")`  |



### The Input/Print Power Duo
### Project 1: Band Name Generator

```python
name = input("Name? ").strip()  # .strip() removes accidental space without if the user gives space it shows
print(f"Your name is: {name.title()}") #title used for making it upper every new word

welcome="Welcome to the Band Name Generator."
print(welcome)
name_city=input("What is the name of the city you grew up in? \n")
name_pet=input("What is your pet's name? \n")
print("Your band name could be " + name_city +" "+ name_pet) #str concatenation 
print("Your band name could be", name_city, name_pet)
```


### **Day 2: Python Data Types & Number Manipulation**  

| Category               | Key Insights                                                                 | Pro Code Examples                          |
|------------------------|-----------------------------------------------------------------------------|-------------------------------------------|
| **Data Types**         | str, int, float, boolean `type()` reveals a variable's DNA. Underscores improve number readability.  | `1_000_000` (equals `1000000`)           |
| **String Indexing**    | `"hello"[0]` → `'h'` (zero-based), `"hello"[-1]` → `'o'` (negative = from end) | `last_char = user_input[-1]`             |
| **Type Conversion**    | Explicit conversion avoids `TypeError` but may cause `ValueError`            | `int("32")` ✅ vs `int("hello")` ❌       |
| **Float Precision**    | Floating-point math is binary-based (IEEE 754). Use `round(,2)` for decimals and digit choosing option. For flooring use int() or //  | `round(3.14159, 2)` → `3.14`             |
| **Boolean Truthiness** | All values implicitly convert to `bool`. Empty sequences = `False`.          | `bool("")` → `False`, `bool(" ")` → `True` |

`

### 🚨 Common Pitfalls
**ValueError!** 
**TypeError!**

### **Number Theory Nuggets**
```markdown
1. **Why 0.1 + 0.2 ≠ 0.3?**  
   - Binary floating-point can't precisely represent base-10 decimals  

2. **Underscore Magic**  
   ```python
   # Legal in Python 3.6+ (ignored by interpreter)
   bytes = 1_048_576  # More readable than 1048576
   ```

3. **String Slicing Pro Tip**  
   ```python
   user_id = "[USER:1532]"
   # Get numbers between colons
   id_num = int(user_id.split(":")[-1].rstrip("]"))
   print(user_id[6:-1]) #=print(id_num)
   ```


### Project 2: Tip Calculator & Memory Usage on Different Data Types

```python
print("Welcome to the tip calculator!")
bill = float(input("What was the total bill? $"))
tip_percentage = int(input("How much tip would you like to give? 10, 12, or 15? "))
people = int(input("How many people to split the bill? "))
finalize = round((bill * (1 + tip_percentage / 100 )) / people, 2 )
print(f"Each person should pay ${finalize}")

import sys

print(sys.getsizeof(10))       # 28 bytes (int)
print(sys.getsizeof(10.0))     # 24 bytes (float)
print(sys.getsizeof("a"))      # 50 bytes (1-char string)
print(sys.getsizeof([1,2,3]))  # 88 bytes (list overhead)

class Compact:
    __slots__ = ['x', 'y']  # Optimization saves ~40% memory vs regular class
    def __init__(self, x, y):
        self.x = x
        self.y = y
```

## Day 3: Conditional Statements & Logical Operators

= Assignment
== Checking

Category | Key Concepts | Examples
--- | --- | ---
If/Else | Execute code blocks based on conditions | `if condition: do_this() else: do_that()`
Comparison Operators | `>`, `<`, `>=`, `<=`, `==`, `!=` | `age >= 18` (check voting eligibility)
Modulo Operator | Returns division remainder | `10 % 3` → `1` (useful for even/odd checks)
Nested Conditionals | If statements inside other if statements | ```python<br>if x > 0:<br>    if y > 0: ...```
Elif | Chain multiple conditions (getting inside one breaks everything) | `if...elif...elif...else`
Multiple Ifs | Independent conditions (vs mutually exclusive elif) | Each if gets checked regardless of others
Logical Operators | Combine conditions (`and`, `or`, `not`) | `if age >= 18 and has_id:`

### Treasure Island Project

```python
#ASCII Art Trick:
print('''
Art goes here
 /\_/\
( o.o )
 > ^ <
''')

print("Welcome to Treasure Island.")
print("Your mission is to find the treasure.")

direction = input("You're at a cross road. Where do you want to go? Type \"left\" or \"right\". \n").lower()

if direction == "left":
    action = input("You've come to a lake. There is an island in the middle. Type \"wait\" or \"swim\". \n").lower()
    
    if action == "wait":
        door = input("You arrive at the island unharmed. Choose a door: \"red\", \"yellow\", or \"blue\". \n").lower()
        
        if door == "yellow":
            print("You found the treasure! You Win!")
        elif door == "red":
            print("It's a room full of fire. Game Over.")
        else:
            print("You enter a room of beasts. Game Over.")
            
    else:
        print("You get attacked by an angry trout. Game Over.")
        
else:
    print("You fell into a hole. Game over.")
```


### **Day 4: Randomization & Python Lists**  
**Aim:** Rock, Paper, Scissors game

-Randomness related with games the most.

-Computers, machines are deterministic; their operation is repeatable and predictable.

-Pseudorandom generators crucial: randomness is nondeterminitistic in computing the valid case is what is possible and what is possible in a reasonable time.

-Pseudorandom numbers vs Random walks

-In computers randomness repeats eventually when it is huge amount seed * milisecond and take the middle of the result and after repetation that called period, due to the seed it might not visible in a long run.

-Random module is a python module.

-Each module is responsible for a different bit of functionality of your program and perfect for collaboration in a project ❤️.

#coding is like an open book exam

| Category              | Key Takeaways                                                                 | Code Example/Solution                          |
|-----------------------|---------------------------------------------------------------------------|-----------------------------------------------|
| **Random Module**     | `random.randint()` includes both bounds, `random.random()` gives float [0,1). Use `random.uniform()` for custom ranges. | `random.randint(1,6)` → Dice roll |
| **Pseudorandomness**  | Computers use mathematical algorithms (Mersenne Twister) - deterministic but unpredictable without seed. Security depends on seed complexity. | `random.seed(42)` |
| **Lists**            | Data structure, Ordered, mutable collections. Can mix data types. Zero-indexed with negative indices from end. | `my_list = ["a", 1, True]` |
| **List Methods**     | `.append()` adds single item, `.extend()` merges lists, `len()` gets length. | `states.extend(["Puerto Rico"])` |
| **Nested Lists**     | Lists can contain other lists. Access with multiple indices: `matrix[0][1]`. | `grid = [[1,2], [3,4]]` |
| **Common Errors**    | `IndexError` when accessing non-existent indices. Always check `len()` first. | `print(states[50])` ❌ |

### 🧠 Memory Nuggets
```python
print(my_module.my_favorite_number) #new module creation and getting sth

# Random float between 5-10
random_float = random.uniform(5, 10)  

# Select random item from list
print(random.choice(friends))  

# Shuffle list in-place
random.shuffle(states_of_america)  

# Nested list access
print(fruits_and_veg[1][1])  # "Kale"
```
### Rock, Paper, Scissors Project

```python

import random

rock = '''
    _______
---'   ____)
      (_____)
      (_____)
      (____)
---.__(___)
'''

paper = '''
    _______
---'   ____)____
          ______)
          _______)
         _______)
---.__________)
'''

scissors = '''
    _______
---'   ____)____
          ______)
       __________)
      (____)
---.__(___)
'''
game_ascii=[rock,paper,scissors]
player=int(input("What do you choose? Type 0 for Rock, 1 for Paper or 2 for Scissors. "))
if player>=0 and player<=3:
    print(game_ascii[player])
else:
    print("Undefined!")


print("Computer choose:")
computer=random.randint(0,2)
if computer>=0 and computer<=2:
    print(game_ascii[computer])

if player>=3 or player<0:
    print("You typed an invalid number. You lose!")
elif player==0 and computer==2:
    print("You won!")
elif player==2 and computer==0:
    print("Computer won!")

elif computer > player:
    print("Computer won!")
elif player > computer:
    print("You won!")

elif player==computer:
    print("It is a draw!")
```

### **Day 5: For Loops, Range & Password Generator**  
**Aim:** Build a secure password generator using loops

-Syntax refers to a concept in writing code dealing with a very specific set of words and a very specific order to those words when we give the computer instructions. This is why it is important when it comes to learning basic things in a fundamental syntax version.

-Python is really number friendly.

**For Loop Fundamentals**
```python
fruits = ["Apple", "Peach", "Pear"]
for fruit in fruits:  # fruit becomes each item temporarily
    print(len(fruit))  # Works on each fruit's length as letters
# After loop: fruit retains last value ("Pear")
```
**Range** is not useful when it is not qualified with a loop. ❗️❗️

```python
# Three forms of range():
range(10)        # 0-9 (stop only)
range(1, 10)     # 1-9 (start, stop)
range(1, 10, 2)  # 1,3,5,7,9 (start, stop, step)

# Gauss Summation Trick (1-100) german mathematician 101*100/2
total = 0
for num in range(1, 101):
    total += num  # 5050
```
### Password Generator Project
```python
import random
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']
symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']

print("Welcome to the PyPassword Generator!")
nr_letters = int(input("How many letters would you like in your password?\n"))
nr_symbols = int(input(f"How many symbols would you like?\n"))
nr_numbers = int(input(f"How many numbers would you like?\n"))

#Easy level
password=""
for char in range(0, nr_letters):
    #random_char=random.choice(letters)
    password+=random.choice(letters)
    #print(random_char)
#print(password)

for char in range(0, nr_symbols):
    password+=random.choice(symbols)

#for char in range(1, nr_numbers+1): we changed it the 1-ones
for char in range(0, nr_numbers):
    password+=random.choice(numbers)
#print(password)

pass_list=[]
for char in password:
    pass_list+=char
random.shuffle(pass_list)
#print(pass_list)

last_str=""
for char in pass_list:
    last_str+=char
print(f"Your password is: {last_str}") #this is f string
#print(last_str.join(pass_list))

"""
.shuffle works in list
.join helps to turn list to string in an empty one 
final_password = "".join(pass_list)

range usage in a loop is crucial
if there is numb unnecessary in both side plus 1 you can delete that while 
in both sides doing -1
you can use string concatenation = append or extend to an empty list
password_lett = random.sample(letters, nr_letters)  # Directly pick 'n' random letters
str_two=str.join(random.sample(pass_list,len(pass_list))) #The sample() method returns a list with a specified number of randomly selected items from a sequence.

"""
```

