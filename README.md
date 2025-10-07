# calculator# calculator.py
# A simple command-line calculator using functions
# Developed for Python Developer Internship

# --- Define operation functions ---
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b == 0:
        return "Error: Division by zero is not allowed."
    return a / b


# --- Main calculator loop ---
def calculator():
    print("===== Command-Line Calculator =====")
    print("Operations: +  -  *  /")
    print("Type 'exit' to quit.")
    print("==================================")

    while True:
        # Take user input
        choice = input("\nEnter operation (+, -, *, /) or 'exit' to quit: ")

        if choice.lower() == 'exit':
            print("Exiting calculator... Goodbye!")
            break

        # Validate operation choice
        if choice not in ['+', '-', '*', '/']:
            print("Invalid operation! Please choose +, -, * or /.")
            continue

        try:
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))
        except ValueError:
            print("Invalid input! Please enter numeric values.")
            continue

        # Perform selected operation
        if choice == '+':
            result = add(num1, num2)
        elif choice == '-':
            result = subtract(num1, num2)
        elif choice == '*':
            result = multiply(num1, num2)
        elif choice == '/':
            result = divide(num1, num2)

        print(f"Result: {result}")


# --- Run the calculator ---
if __name__ == "__main__":
    calculator()
