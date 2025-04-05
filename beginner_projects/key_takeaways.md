# 101 Coding

## *Tips*

-Books are good as references. If you want to dive deep into delegates and protocols read that chapter, when it comes to learning; hands on project is the best.

-Being a copycat if you have no idea for a project at first.

-Find a code mentor.

-There' always a bug.

-Never a copy paste a code that you didnt undertsand completely.

-Always go with 2 screen. 

### **Day 1: Python Basics - Band Name Generator**  
## 🔍 Key Takeaways (Structured for Muscle Memory)


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
```python
# Anti-pattern (beginner):
print("Your name is: " + input("Name? "))

# Pro pattern (immediate feedback):
name = input("Name? ").strip()  # .strip() removes accidental whitespace
print(f"Processed: {name.title()}")

# Project 1: Band Name Generator
welcome="Welcome to the Band Name Generator."
print(welcome)
name_city=input("What is the name of the city you grew up in? \n")
name_pet=input("What is your pet's name? \n")
print("Your band name could be " + name_city +" "+ name_pet)
print("Your band name could be", name_city, name_pet)













