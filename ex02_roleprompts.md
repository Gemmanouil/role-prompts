

Objective: Use role-based prompts for personalized feedback.

Ask the model to act as a coding mentor.

Provide a simple piece of code (e.g., a Python function with a bug).

Prompt the model: "Act as a mentor reviewing this code. Provide corrections and explain improvements."

Review the response and check if the role influences feedback style.

def greet_user(name, age):
if age < 18:
    print(f"Hello {name}! You're a young explorer!")
elif age < 50:
    print(f"Hello {name}! Hope you're having a productive day!")
else:
    print(f"Hello {name}! Wishing you a wonderful day!")

name = input("Enter your name: ")
age = input("Enter your age: ") #this must be int
greet_user(name, age)

Mentor Review
1️⃣ Issue: Age input type

Problem: age is taken using input(), which returns a string. Later in greet_user, you compare it to numbers (18 and 50). Comparing a string to an integer will cause a TypeError in Python 3.

Correction: Convert the input to an integer right away.

age = int(input("Enter your age: "))

2️⃣ Issue: Input validation

Problem: If the user enters something that isn’t a number, the program will crash.

Improvement: Use a try/except block to handle invalid inputs gracefully.

try:
    age = int(input("Enter your age: "))
except ValueError:
    print("Please enter a valid number for age.")
    exit()  # Stop program if input is invalid

3️⃣ Enhancement: Function separation

Right now, greet_user prints directly.

Improvement: For better design, functions can return a string instead of printing. This makes your function reusable in other contexts (like GUIs, web apps, or logging).

def greet_user(name, age):
    if age < 18:
        return f"Hello {name}! You're a young explorer!"
    elif age < 50:
        return f"Hello {name}! Hope you're having a productive day!"
    else:
        return f"Hello {name}! Wishing you a wonderful day!"


Then print it outside:

message = greet_user(name, age)
print(message)

4️⃣ Enhancement: Code readability

Add comments, consistent spacing, and a separator line to make the output clear.

Example:

print("-" * 40)
print(message)
print("-" * 40)

5️⃣ Optional improvement: Personalization

You can ask for hobbies, favorite color, or other details and make the message more interactive.

This teaches combining inputs, logic, and strings, a key skill in Python.

✅ Improved Version
def greet_user(name, age):
    if age < 18:
        return f"Hello {name}! You're a young explorer!"
    elif age < 50:
        return f"Hello {name}! Hope you're having a productive day!"
    else:
        return f"Hello {name}! Wishing you a wonderful day!"

# Main program
name = input("Enter your name: ")

try:
    age = int(input("Enter your age: "))
except ValueError:
    print("Please enter a valid number for age.")
    exit()

message = greet_user(name, age)
print("-" * 40)
print(message)
print("-" * 40)


💡 Mentor takeaway:

Always validate inputs.

Prefer functions that return values instead of printing directly.

Make code readable and maintainable with comments and formatting.

Think ahead about reusability and error handling.

It deepens thinking and explain what could have been done better
