import math

def calculator():
    print("=" * 40)
    print("      Python Calculator")
    print("=" * 40)

    while True:
        print("\nSelect an operation:")
        print("1. Addition (+)")
        print("2. Subtraction (-)")
        print("3. Multiplication (*)")
        print("4. Division (/)")
        print("5. Power (^)")
        print("6. Square Root (√)")
        print("7. Exit")

        choice = input("\nEnter your choice (1-7): ")

        if choice == "7":
            print("\nThanks for using the calculator!")
            break

        if choice == "6":
            try:
                num = float(input("Enter a number: "))
                if num < 0:
                    print("Error: Cannot calculate the square root of a negative number.")
                else:
                    print(f"√{num} = {math.sqrt(num)}")
            except ValueError:
                print("Invalid input. Please enter a valid number.")
            continue

        if choice in ["1", "2", "3", "4", "5"]:
            try:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))

                if choice == "1":
                    result = num1 + num2
                    operator = "+"

                elif choice == "2":
                    result = num1 - num2
                    operator = "-"

                elif choice == "3":
                    result = num1 * num2
                    operator = "*"

                elif choice == "4":
                    if num2 == 0:
                        print("Error: Division by zero is not allowed.")
                        continue
                    result = num1 / num2
                    operator = "/"

                elif choice == "5":
                    result = num1 ** num2
                    operator = "^"

                print(f"\nResult: {num1} {operator} {num2} = {result}")

            except ValueError:
                print("Invalid input. Please enter numbers only.")

        else:
            print("Invalid choice. Please select a number between 1 and 7.")

if __name__ == "__main__":
    calculator()
