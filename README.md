# Projects

#project 1
#Atm transaction system
# Starting balance of the user
balance = 25000

# while True is used because the ATM menu should
# keep appearing until the user chooses Exit
while True:

    print("\n===== ATM MENU =====")
    print("1. Check Balance")
    print("2. Deposit Money")
    print("3. Withdraw Money")
    print("4. Exit")

    choice = input("Enter your choice: ")

    # match-case is used to perform different
    # operations according to the user's choice
    match choice:

        case "1":
            # Display the current balance
            print("Current Balance: ₹", balance)

        case "2":
            # Take the deposit amount from the user
            amount = float(input("Enter deposit amount: ₹"))

            # Deposit should not be zero or negative
            if amount <= 0:
                print("Invalid deposit amount.")

            else:
                # Add the deposit amount to the existing balance
                balance = balance + amount
                print("Money deposited successfully.")
                print("New Balance: ₹", balance)

        case "3":
            # Take the withdrawal amount from the user
            amount = float(input("Enter withdrawal amount: ₹"))

            # Withdrawal should not be zero or negative
            if amount <= 0:
                print("Invalid withdrawal amount.")

            # The user cannot withdraw more than the balance
            elif amount > balance:
                print("Insufficient balance.")

            else:
                # Subtract the withdrawal amount from the balance
                balance = balance - amount
                print("Money withdrawn successfully.")
                print("Remaining Balance: ₹", balance)

        case "4":
            # Show the final balance before exiting
            print("\nFinal Balance: ₹", balance)
            print("Thank you for using the ATM.")

            # break is used to stop the while loop
            break

        case _:
            # This runs when the user enters an invalid option
            print("Invalid choice. Please try again.")

            
#project 2
#super market billing system


# These variables are used to store the total number
# of products and the total amount of the bill
total_products = 0
total_bill = 0

# The loop allows the customer to enter multiple products
while True:

    product = input("\nEnter product name (or 'done' to finish): ")

    # If the customer enters done, billing is finished
    if product.lower() == "done":
        break

    # Take the price of the product
    price = float(input("Enter product price: ₹"))

    # Negative prices are not allowed
    if price < 0:
        print("Invalid price. Product skipped.")

        # continue skips this product and starts the loop again
        continue

    # Count the valid product
    total_products = total_products + 1

    # Add the price to the total bill
    total_bill = total_bill + price


# Check whether any product was entered
if total_products > 0:

    # Average price is total bill divided by number of products
    average_price = total_bill / total_products

    print("\n===== BILL SUMMARY =====")
    print("Total Products:", total_products)
    print("Total Bill: ₹", total_bill)
    print("Average Product Price: ₹", average_price)

    # Discount is given only when the bill is above ₹5000
    if total_bill > 5000:

        # Calculate 10% discount
        discount = total_bill * 0.10

        # Subtract discount from the original bill
        final_bill = total_bill - discount

        print("Discount (10%): ₹", discount)
        print("Final Bill: ₹", final_bill)

    else:
        # No discount if the bill is ₹5000 or less
        print("Discount: ₹0")
        print("Final Bill: ₹", total_bill)

else:
    print("No products were entered.")


  #project 3
  #bank lone eligibility system

  # The program will continue checking customers
# until the user decides to stop
while True:

    print("\n===== LOAN ELIGIBILITY CHECK =====")

    # Take the required information from the customer
    age = int(input("Enter age: "))
    salary = float(input("Enter monthly salary: ₹"))
    credit_score = int(input("Enter credit score: "))
    existing_loan = input(
        "Do you have an existing loan? (yes/no): "
    ).lower()

    # First check the age requirement
    if age < 21 or age > 60:
        print("Loan Status: REJECTED")
        print("Reason: Age must be between 21 and 60.")

    # Check the minimum salary requirement
    elif salary < 30000:
        print("Loan Status: REJECTED")
        print("Reason: Salary must be at least ₹30000.")

    # Check the minimum credit score
    elif credit_score < 700:
        print("Loan Status: REJECTED")
        print("Reason: Credit score must be at least 700.")

    # Existing loan should not be yes
    elif existing_loan == "yes":
        print("Loan Status: REJECTED")
        print("Reason: Existing loan detected.")

    else:
        # If all conditions are satisfied, loan is approved
        print("Loan Status: APPROVED")

    # Ask whether another customer needs to be checked
    again = input(
        "\nDo you want to check another customer? (yes/no): "
    ).lower()

    # Stop the loop if the user does not enter yes
    if again != "yes":
        break

print("\nLoan eligibility processing completed.")

#project 4
#food delivery order system

# This variable stores the total cost of all ordered items
total_bill = 0

# The loop allows the customer to order more than one item
while True:

    print("\n===== FOOD MENU =====")
    print("1. Pizza    - ₹250")
    print("2. Burger   - ₹150")
    print("3. Pasta    - ₹200")
    print("4. Sandwich - ₹120")
    print("5. Exit")

    choice = input("Enter your choice: ")

    # match-case is used to identify the selected food
    match choice:

        case "1":
            item = "Pizza"
            price = 250

        case "2":
            item = "Burger"
            price = 150

        case "3":
            item = "Pasta"
            price = 200

        case "4":
            item = "Sandwich"
            price = 120

        case "5":
            # Exit the ordering system
            break

        case _:
            # Invalid menu choices are ignored
            print("Invalid menu option. Please try again.")

            # continue starts the menu again
            continue

    # Ask how many items the customer wants
    quantity = int(input("Enter quantity: "))

    # Quantity should be positive
    if quantity <= 0:
        print("Invalid quantity.")
        continue

    # Calculate the cost of the selected item
    item_total = price * quantity

    # Add it to the total bill
    total_bill = total_bill + item_total

    print(quantity, item, "added to the order.")
    print("Item Total: ₹", item_total)


# Display the bill after the customer exits
print("\n===== BILL SUMMARY =====")
print("Total Bill: ₹", total_bill)

# Apply discount if the bill is more than ₹1000
if total_bill > 1000:

    # Calculate 15% discount
    discount = total_bill * 0.15

    # Calculate the amount after discount
    final_bill = total_bill - discount

    print("Discount (15%): ₹", discount)
    print("Final Bill: ₹", final_bill)

else:
    print("Discount: ₹0")
    print("Final Bill: ₹", total_bill)

print("Thank you for ordering!")

#project 5
#student result processing system

# These variables are used to calculate the class average
total_students = 0
total_percentage = 0

# The loop allows us to process multiple students
while True:

    print("\n===== STUDENT RESULT =====")

    name = input("Enter student name (or 'done' to finish): ")

    # If done is entered, stop processing students
    if name.lower() == "done":
        break

    # List of subjects
    subjects = [
        "Python",
        "Database",
        "Mathematics",
        "Computer Networks"
    ]

    # This list will store marks of the student
    marks = []

    valid = True

    # for loop is used to take marks for all four subjects
    for subject in subjects:

        mark = float(input("Enter marks in " + subject + ": "))

        # Marks cannot be below 0 or above 100
        if mark < 0 or mark > 100:
            print("Invalid marks. Student record skipped.")

            # Change valid to False because the marks are invalid
            valid = False
            break

        # Store valid marks in the list
        marks.append(mark)

    # If marks were invalid, skip this student
    if not valid:
        continue

    # Calculate the total marks
    total = sum(marks)

    # There are four subjects, so divide total by 4
    percentage = total / 4

    # If any subject is below 40, student fails
    if any(mark < 40 for mark in marks):
        grade = "F"
        result = "FAIL"

    # Grade is decided according to percentage
    elif percentage >= 90:
        grade = "A+"
        result = "PASS"

    elif percentage >= 80:
        grade = "A"
        result = "PASS"

    elif percentage >= 70:
        grade = "B"
        result = "PASS"

    elif percentage >= 60:
        grade = "C"
        result = "PASS"

    elif percentage >= 50:
        grade = "D"
        result = "PASS"

    else:
        grade = "F"
        result = "FAIL"

    # Count this student for the class average
    total_students = total_students + 1
    total_percentage = total_percentage + percentage

    # Display the student's result
    print("\n===== RESULT =====")
    print("Student:", name)
    print("Total Marks:", total, "/ 400")
    print("Percentage:", percentage, "%")
    print("Grade:", grade)
    print("Result:", result)


# Calculate the class average after all students are processed
if total_students > 0:

    class_average = total_percentage / total_students

    print("\n===== CLASS SUMMARY =====")
    print("Total Students:", total_students)
    print("Class Average:", class_average, "%")

else:
    print("No valid student records were entered.")

 #project 6
 #smart traffic signal controller

 # Counters are used to keep track of how many times
# each traffic signal was entered
red_count = 0
yellow_count = 0
green_count = 0

# Keep accepting signals until the user enters exit
while True:

    signal = input(
        "\nEnter signal (red/yellow/green/exit): "
    ).lower()

    # match-case is useful here because there are
    # different actions for different signal names
    match signal:

        case "red":
            print("STOP")

            # Increase red counter by 1
            red_count = red_count + 1

        case "yellow":
            print("GET READY")

            # Increase yellow counter by 1
            yellow_count = yellow_count + 1

        case "green":
            print("GO")

            # Increase green counter by 1
            green_count = green_count + 1

        case "exit":
            # Stop the simulation
            break

        case _:
            # This handles any signal not in our menu
            print("Invalid Signal")


# Display the counters after the loop ends
print("\n===== SIGNAL STATISTICS =====")
print("Red:", red_count)
print("Yellow:", yellow_count)
print("Green:", green_count)

print("Traffic simulation terminated.")

#project 7
#login security system

# Store the correct username and password
correct_username = "admin"
correct_password = "Python@123"

# This variable counts the number of login attempts
attempts = 0

# Maximum number of attempts allowed
max_attempts = 3

# Keep asking until the maximum attempts are reached
while attempts < max_attempts:

    username = input("Enter username: ")

    # An empty username should not count as an attempt
    if username == "":
        print("Username cannot be empty. Please try again.")

        # continue takes us back to the beginning of the loop
        continue

    password = input("Enter password: ")

    # Count the login attempt only after a username is entered
    attempts = attempts + 1

    # Check both username and password
    if username == correct_username and password == correct_password:

        print("Login Successful")

        # Login is successful, so there is no need to continue
        break

    else:

        # Calculate how many attempts are left
        remaining = max_attempts - attempts

        if remaining > 0:
            print(
                "Incorrect credentials."
            )
            print("Attempts remaining:", remaining)

        else:
            print("Incorrect credentials.")
            print("Account locked. Maximum attempts exceeded.")

  
            
