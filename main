# Program that calculates how many days someone has been dead or alive based on their date of death (dod) or date of birth (dob)

# TODO Clear and redraw screen between invalid inputs to avoid scrolling

import datetime
import sys

def get_user_status():
    while True:
        status = input("\nAre you dead or alive? ").lower()
        if status == "dead" or status == "alive":
            return status
        else:
            print("\nInvalid input, please enter 'dead' or 'alive'.")

def get_date_input(prompt):
    while True:
        try:
            date_input = input(prompt)
            date = datetime.datetime.strptime(date_input, "%Y-%m-%d").date()
            return date
        except ValueError:
            print("\nInvalid date format, please enter in the format YYYY-MM-DD.")

def calculate_days(date):
    # Get today's date
    today = datetime.date.today()
    # Calculate the number of days between the two dates
    days = (today - date).days
    return days

def print_result(status, days):
    plural = "" if days == 1 else "s"
    verb = "been dead" if status == "dead" else "lived"
    print(f"\nYou have {verb} for {days} day{plural}.\n")

def get_yes_no_input(prompt):
    while True:
        user_choice = input(f"{prompt} (y/n or yes/no) ").strip().lower()
        if user_choice in ['y', 'yes']:
            return True
        elif user_choice in ['n', 'no']:
            return False
        else:
            print("\nPlease enter a valid response (y/n or yes/no).\n")

def main():
    status = get_user_status()

    # Get the user's date of death or birth
    prompt = f"\nEnter your date of {'death' if status == 'dead' else 'birth'} (YYYY-MM-DD): "
    date = get_date_input(prompt)

    # Calculate the number of days dead or alive
    days = calculate_days(date)

    print_result(status, days)

# Main program loop
while True:
    main()
    prompt = "Do you want to calculate again?"
    user_choice = get_yes_no_input(prompt)
    if not user_choice:
        sys.exit("\nThank you for using the program!\n")
