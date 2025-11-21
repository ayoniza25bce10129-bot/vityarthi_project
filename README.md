# vityarthi_project
VITyarthi individual project - Password Generator and Strength Evaluator

import random
import string

def generate_password(length):
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
