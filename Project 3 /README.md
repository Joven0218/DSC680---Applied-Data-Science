Cash Register Program
Overview

This Cash Register Program demonstrates Python object-oriented programming concepts by creating a simple cash register application. The program allows users to add charter fishing trips to their cart, keeping track of the number of items and the total price, formatted as currency.
Features

    Welcome Message: A greeting for the user.
    Class: CashRegister class with methods to add items, get total price, and get item count.
    Instance Methods:
        addItem to add an item by price.
        getTotal to return the total price.
        getCount to return the number of items.
    Main Function: Handles user interaction and manages the cart.
    Loop for Adding Items: Allows the user to add items until they choose to quit.
    Formatted Output: Displays the total number of items and the total amount in the cart, formatted as currency using the locale library.

Requirements

    Python 3
    locale library

Installation

    Clone the Repository:

    bash

git clone https://github.com/Joven0218/DSC680---Applied-Data-Science.git
cd DSC680---Applied-Data-Science/Weather Program

Run the Program:

bash

    python CashRegister.py

Usage

    Welcome Message:
    Upon running the program, a welcome message is displayed.

    Charter Options:
    Users can choose from different charter options with details and prices.

    Adding Items:
    Users can add items to their cart by entering the corresponding number or type "done" to finish.

    Displaying Totals:
    The program displays the total number of items and the total price formatted as currency.

Example

python

Welcome to Young Fishing Charters, please choose from trips below.

Charter:1     Price:450     Details:6 Hours inshore fishing, 7am - 1pm
Charter:2     Price:500     Details:6 Hours inshore fishing, lunch and drinks provided
Charter:3     Price:650     Details:8 Hours offshore fishing, 7am - 3pm
Charter:4     Price:700     Details:8 Hours offshore fishing, lunch and drinks provided

Add order to cart using numbers 1-4. Once done adding trip(s) to cart type "done": 1
You have added Charter 1 to your cart, you have 1 trip(s) in total.

Total charter price: $450.00
Total charter count: 1
Captain will reach out for scheduling, gratuity is very much appreciated!

Notes

    Ensure proper error handling for invalid inputs.
    Follow PEP8 guidelines for code formatting.

Conclusion

This Cash Register Program is a practical application that demonstrates how to use Python classes and methods to create a functional and user-friendly program for managing a shopping cart.
Bankers Financial Corp workspace
