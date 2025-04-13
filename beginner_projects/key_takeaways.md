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
# Anti-pattern (beginner):
print("Your name is: " + input("Name? "))

# Pro pattern (immediate feedback):
name = input("Name? ").strip()  # .strip() removes accidental whitespace
print(f"Processed: {name.title()}")

welcome="Welcome to the Band Name Generator."
print(welcome)
name_city=input("What is the name of the city you grew up in? \n")
name_pet=input("What is your pet's name? \n")
print("Your band name could be " + name_city +" "+ name_pet)
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
    __slots__ = ['x', 'y']  # Saves ~40% memory vs regular class
    def __init__(self, x, y):
        self.x = x
        self.y = y
```

## Day 3: Conditional Statements & Logical Operators

'''= Assignment
== Checking
'''

Category | Key Concepts | Examples
--- | --- | ---
If/Else | Execute code blocks based on conditions | `if condition: do_this() else: do_that()`
Comparison Operators | `>`, `<`, `>=`, `<=`, `==`, `!=` | `age >= 18` (check voting eligibility)
Modulo Operator | Returns division remainder | `10 % 3` → `1` (useful for even/odd checks)
Nested Conditionals | If statements inside other if statements | ```python<br>if x > 0:<br>    if y > 0: ...```
Elif | Chain multiple conditions (getting inside one breaks everything) | `if...elif...elif...else`
Multiple Ifs | Independent conditions (vs mutually exclusive elif) | Each if gets checked regardless of others
Logical Operators | Combine conditions (`and`, `or`, `not`) | `if age >= 18 and has_id:`

### Key Insights

1. **Conditional Flow**:
   
   ```python
   # Basic structure
   if condition:
       # code block
   elif another_condition:
       # code block  
   else:
       # default code
   
   choice = input("Yes/No? ").lower()  # Case-insensitive comparison

2. **Treasure Island Project**:
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











