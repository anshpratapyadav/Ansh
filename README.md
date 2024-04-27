Name: priyanshu sharma
University Roll No.: 2315001715
Class Roll No.: 48
Section:- BG

1: BASIC CALCULATOR

def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error! Division by zero."
    else:
        return x / y

print("Select operation:")
print("1. Addition")
print("2. Subtraction")
print("3. Multiplication")
print("4. Division")

while True:
    choice = input("Enter choice (1/2/3/4): ")

    if choice in ('1', '2', '3', '4'):
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))

        if choice == '1':
            print("Result:", add(num1, num2))
        elif choice == '2':
            print("Result:", subtract(num1, num2))
        elif choice == '3':
            print("Result:", multiply(num1, num2))
        elif choice == '4':
            print("Result:", divide(num1, num2))
        break
    else:
        print("Invalid Input")

2: NUMBER SYSTEM

def decimal_to_binary(decimal):
    return bin(decimal)[2:]

def binary_to_decimal(binary):
    return int(binary, 2)

def decimal_to_octal(decimal):
    return oct(decimal)[2:]

def octal_to_decimal(octal):
    return int(octal, 8)

def decimal_to_hexadecimal(decimal):
    return hex(decimal)[2:]

def hexadecimal_to_decimal(hexadecimal):
    return int(hexadecimal, 16)

print("Select conversion:")
print("1. Decimal to Binary")
print("2. Binary to Decimal")
print("3. Decimal to Octal")
print("4. Octal to Decimal")
print("5. Decimal to Hexadecimal")
print("6. Hexadecimal to Decimal")

while True:
    choice = input("Enter choice (1/2/3/4/5/6): ")

    if choice in ('1', '2', '3', '4', '5', '6'):
        num = input("Enter the number: ")

        if choice == '1':
            print("Binary:", decimal_to_binary(int(num)))
        elif choice == '2':
            print("Decimal:", binary_to_decimal(num))
        elif choice == '3':
            print("Octal:", decimal_to_octal(int(num)))
        elif choice == '4':
            print("Decimal:", octal_to_decimal(num))
        elif choice == '5':
            print("Hexadecimal:", decimal_to_hexadecimal(int(num)))
        elif choice == '6':
            print("Decimal:", hexadecimal_to_decimal(num))
        break
    else:
        print("Invalid Input")

3: VOTING SYSTEM

def voting_system():
    candidates = {}
    num_candidates = int(input("Enter the number of candidates: "))

    # Initialize candidates with zero votes
    for i in range(num_candidates):
        candidate_name = input(f"Enter the name of candidate {i+1}: ")
        candidates[candidate_name] = 0

    num_voters = int(input("Enter the number of voters: "))

    # Record votes
    for i in range(num_voters):
        print(f"Voter {i+1}, please select your candidate:")
        for candidate in candidates:
            print(f"{candidate}")
        vote = input("Enter candidate name: ")

        # Check if the candidate exists
        if vote in candidates:
            candidates[vote] += 1
            print("Vote recorded successfully!")
        else:
            print("Invalid candidate! Vote not recorded.")

    print("\nElection Results:")
    for candidate, votes in candidates.items():
        print(f"{candidate}: {votes} votes")

voting_system()

4: GRADING SYSTEM

def calculate_grade(score):
    if score >= 90:
        return 'A'
    elif 80 <= score < 90:
        return 'B'
    elif 70 <= score < 80:
        return 'C'
    elif 60 <= score < 70:
        return 'D'
    else:
        return 'F'

def main():
    num_students = int(input("Enter the number of students: "))

    for i in range(1, num_students + 1):
        score = float(input(f"Enter the score of student {i}: "))
        grade = calculate_grade(score)
        print(f"Student {i}: Score = {score}, Grade = {grade}")

if _name_ == "_main_":
    main()

5: INVENTORY SYSTEM

class Product:
    def _init_(self, id, name, price, quantity):
        self.id = id
        self.name = name
        self.price = price
        self.quantity = quantity

class Inventory:
    def _init_(self):
        self.products = []

    def add_product(self, product):
        self.products.append(product)
        print("Product added to inventory.")

    def remove_product(self, product_id):
        for product in self.products:
            if product.id == product_id:
                self.products.remove(product)
                print("Product removed from inventory.")
                return
        print("Product not found.")

    def display_inventory(self):
        if not self.products:
            print("Inventory is empty.")
            return
        print("Inventory:")
        for product in self.products:
            print(f"ID: {product.id}, Name: {product.name}, Price: ${product.price}, Quantity: {product.quantity}")


def main():
    inventory = Inventory()

    while True:
        print("\nSelect an option:")
        print("1. Add Product")
        print("2. Remove Product")
        print("3. Display Inventory")
        print("4. Exit")

        choice = input("Enter choice (1/2/3/4): ")

        if choice == '1':
            id = input("Enter product ID: ")
            name = input("Enter product name: ")
            price = float(input("Enter product price: "))
            quantity = int(input("Enter product quantity: "))
            product = Product(id, name, price, quantity)
            inventory.add_product(product)
        elif choice == '2':
            id = input("Enter product ID to remove: ")
            inventory.remove_product(id)
        elif choice == '3':
            inventory.display_inventory()
        elif choice == '4':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.")


if _name_ == "_main_":
    main()

6: NO. GUESSING GAME

import random

def guessing_game():
    print("Welcome to the Guessing Game!")
    print("I have selected a number between 1 and 100. Try to guess it.")

    # Generate a random number between 1 and 100
    secret_number = random.randint(1, 100)
    attempts = 0

    while True:
        guess = int(input("Enter your guess: "))
        attempts += 1

        if guess < secret_number:
            print("Too low! Try again.")
        elif guess > secret_number:
            print("Too high! Try again.")
        else:
            print(f"Congratulations! You guessed the number {secret_number} correctly!")
            print(f"It took you {attempts} attempts.")
            break

if _name_ == "_main_":
    guessing_game()

7: ROLL THE DICE

import random

def roll_dice():
    print("Rolling the dice...")
    return random.randint(1, 6)

if _name_ == "_main_":
    input("Press Enter to roll the dice...")
    result = roll_dice()
    print("The result is:", result)

8: ROCK PAPER SCISSOR

import random

def play_game():
    print("Let's play Rock, Paper, Scissors!")
    choices = ['rock', 'paper', 'scissors']

    while True:
        user_choice = input("Enter your choice (rock/paper/scissors): ").lower()
        if user_choice not in choices:
            print("Invalid choice. Please try again.")
            continue
        
        computer_choice = random.choice(choices)
        print("Computer chooses:", computer_choice)

        if user_choice == computer_choice:
            print("It's a tie!")
        elif (user_choice == 'rock' and computer_choice == 'scissors') or \
             (user_choice == 'paper' and computer_choice == 'rock') or \
             (user_choice == 'scissors' and computer_choice == 'paper'):
            print("You win!")
        else:
            print("Computer wins!")
        
        play_again = input("Do you want to play again? (yes/no): ").lower()
        if play_again != 'yes':
            break

if _name_ == "_main_":
    play_game()
