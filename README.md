# HOUSE PROFIT TRACKER-
ITE 260 P3- FINAL PROJECT 


records = []

while True:
        print("-----HOUSE PROFIT TRACKER-----")
        print()
        print("1. Add House Sale")
        print("2. Add House Expense")
        print("3. View Summary")
        print("4. Exit")

        user = input("Choose an option:")
        if user == '1':
            location = input("Enter the location of the house:")
            price = float(input("Enter sale price of the house (P): "))
            records.append(("Sale", price))
            records.append(("Location", location))
            print(f"Sale recorded (P{price})")

        elif user == '2':
            description = input("Enter expense description:")
            amount = float(input("Enter expense amount (P): "))
            records.append(("Expense", amount))
            records.append(("Description",description))
            print("Expense Recorded")

        elif user == '3':
            total = sum(amount for rtype, amount in records if rtype == "Sale")
            total_expenses = sum(amount for rtype, amount in records if rtype == "Expense")
            profit = total - total_expenses
            print("-----Summary-----")
            print(f"Total House Sales: P{total:}")
            print()
            print(f"Total Expenses:    P{total_expenses:}")
            print()
            print(f"Net Profit:        P{profit:}")
            print()

        elif user == '4':
            print("Exiting program")
            break

        else:
            print("Invalid choice Please try again.")
