# vityarthi_project
VITyarthi individual project - Password Generator and Strength Evaluator

import random
import string

def gen_password(length):
    chars = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(chars) for _ in range(length))
    return password

def check_strength(password):
    score = 0
    remarks = []
    if len(password) >= 8:
        score += 1
    else: 
        remarks.append("try at least 8 characters")
    if any (c.islower() for c in password):
        score += 1
    else:
        remarks.append("add lowercase letters")
    if any(c.isupper() for c in password):
        score += 1
    else:
        remarks.append("add uppercase letters")
    if any(c.isdigit() for c in password):
        score += 1
    else:
        remarks.append("add numbers")
    if any(c in string.punctuation for c in password):
        score += 1
    else:
        remarks.append("add special characters")

    if score == 5:
        print("strong password!")
    elif score >= 3:
        print(f"moderate password; {remarks})
    else:
        print(f"weak password; {remarks})

print("This is the the Password Generator & Strength Evaluator! Kindly choose which option you want to move ahead with:")

while True:
    print("1. Password Generation")
    print("2. Strength Evaluator")
    print("3. Exit")
    choice = input("Enter the number corresponding to your choice: ")

    if choice == "1"
        len = input("enter desired number of characters in the password: ")
        if not length.isdigit() or int(length) < 4:
            print("a password with over 3 characters is recommended")
            continue
        password = gen_password(int(len))
        print("generated password:", password)
    
        strength, feedback = check_strength(password)
        print("strength:", strength)
        print("feedback:", feedback)
        
    elif choice == "2":
        password = input(enter your password:)
        strength, feedback = check_strength(password)
        print("strength:", strength)
        print("feedback:", feedback)

    elif choice == "3":
        print("Thank you for using the Password Generator & Strength Evaluator!")
        break

    else:
        print("invalid input, please try again.")
    
