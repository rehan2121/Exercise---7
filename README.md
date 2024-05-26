☕️ Cafe Order System 🍰

Welcome to the Cafe Order System! This Python script simulates a simple cafe ordering system where you can choose items from a menu, select a payment method, and receive an estimated time for your order to be ready.

Features
Display a menu with available items and prices.
Allow users to select a payment method (Card or Cash).
Provide a randomized time estimate for order completion.
Option to place multiple orders.
Requirements
Python 3.x
How to Run
Clone the Repository:

bash
Copy code
git clone https://github.com/yourusername/cafe-order-system.git
cd cafe-order-system
Run the Script:

bash
Copy code
python cafe_order_system.py
Code Explanation
The script is divided into several functions, each handling different parts of the ordering process.

Functions

menu():

Displays the menu with available items and their prices.
python
Copy code
def menu():
    a = "1. Coffee 1$\n2. Pastry 2$\n3. Special Cakes 3$\n"
    return print(a)
card_or_cash():

Prompts the user to choose a payment method (Card or Cash).
Ensures input is valid and displays the chosen method.
python
Copy code
def card_or_cash():
    cash = input("Pay With Card Or Cash: ")
    if cash.lower() == "card":
        print("\nThe Payment Is Done With Card")
    elif cash.lower() == "cash":
        print("\nThe Payment Is Done With Cash")
    else:
        print("\nInvalid payment method. Please try again.")
        card_or_cash()
take_time():

Randomly selects and displays the time required to prepare the order.
python
Copy code
def take_time():
    tt = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    time = random.choice(tt)
    print(f"The Order Is Ready In {time} Minutes")
order_twice():

Asks the user if they want to place another order.
If yes, it calls the user_input() function again.
python
Copy code
def order_twice():
    ask_again = input("\nWant To Order Again (No/Yes): ")
    if ask_again.lower() == "no":
        print("Thank you for your order!")
        quit()
    elif ask_again.lower() == "yes":
        user_input()
    else:
        print("Invalid input. Please enter 'Yes' or 'No'.")
        order_twice()
user_input():

Prompts the user to enter the dish number.
Validates the input and processes the order accordingly.
Calls other functions to handle payment and order preparation.
python
Copy code
def user_input():
    try:
        u_i = int(input("Enter The Dish Number: "))
        money = 0

        if u_i == 1:
            money = "1 $"
            card_or_cash()
            print("\nYour Order Is - Coffee", money)
            take_time()
        
        elif u_i == 2:
            money = "2 $"
            card_or_cash()
            print("\nYour Order Is - Pastry", money)
            take_time()
        
        elif u_i == 3:
            money = "3 $"  # Corrected the price for Special Cake
            card_or_cash()
            print("\nYour Order Is - Special Cake", money)
            take_time()
        
        else:
            print("Invalid dish number. You ordered nothing - ", money)
        
        order_twice()
    except ValueError:
        print("Please enter a valid dish number.")
        user_input()
Main Execution:

Displays the menu and starts the user input process.
Prints a farewell message after the ordering process is complete.
python
Copy code
menu()
user_input()

greet = "We loved having you here and can't wait to welcome you back soon!"
print(greet.center(50))
Enjoy Your Virtual Cafe Experience! ☕️🍰
This script is a simple way to simulate ordering at a cafe and can be expanded with more features like additional menu items, detailed payment processing, and more interactive elements. Feel free to fork and improve!
