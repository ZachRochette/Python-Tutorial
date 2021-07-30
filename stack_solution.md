## Solution:

```python
# Function to create an empty stack
def create_stack():
    stack = []
    return stack

# Checks to see if the stack is empty 
def is_empty(stack):
    return(len(stack) == 0)

# Function to push an item to the stack
def push(stack, item):
    stack.append(item)
    print(item + " has been pushed to the stack")

# Funtion to remove an item from the stack
def pop(stack):
    if(is_empty(stack)):
        return str(-1)

    return stack.pop()

stack = create_stack()

# Provide a while loop for the user to add as many items as they want
while True:
    
    #Get user input
    user_input = input("What would you like to do with the stack: add, remove, check, end: ")
    
    # Provide what happens depending on what the user decides to do
    if user_input == "add":
        item = input("What would you like to add? ")
        push(stack, str(item))
    elif user_input == "remove":
        print(pop(stack) + " has been removed from stack")
    elif user_input == "end":
        print("Closing the application")
        break
    elif user_input == "check":
        print(f"The length of stack is {len(stack)} ") #Checks how many items are in stack
    else:
        print("Please enter a valid input")

            #Basic run through
    # What would you like to do with the stack: add, remove, check, end: add
    # What would you like to add? 1
    # 1 has been pushed to the stack

    # What would you like to do with the stack: add, remove, check, end: add
    # What would you like to add? 2
    # 2 has been pushed to the stack

    # What would you like to do with the stack: add, remove, check, end: add
    # What would you like to add? 3

    # 3 has been pushed to the stack
    # What would you like to do with the stack: add, remove, check, end: check
    # The length of stack is 3 

    # What would you like to do with the stack: add, remove, check, end: remove
    # 3 has been removed from stack
    
    # What would you like to do with the stack: add, remove, check, end: check
    # The length of stack is 2 

    # What would you like to do with the stack: add, remove, check, end: end
    # Closing the application
```

Back to stacks: [Stacks](stacks.md)