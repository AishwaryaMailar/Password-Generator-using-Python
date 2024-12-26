# Password-Generator-using-Python
import random
import string
length = int(input("Enter the desired password length: "))
use_letters = input("Include letters? (yes/no): ").strip().lower() == 'yes'
use_digits = input("Include digits? (yes/no): ").strip().lower() == 'yes'
use_punctuation = input("Include punctuation? (yes/no): ").strip().lower() == 'yes'
def generate_password(length, use_letters=True, use_digits=True, use_punctuation=True):

    characters = ""
    if use_letters:
        characters += string.ascii_letters # includes both A-Z and a-z
    if use_digits:
        characters += string.digits  #includes 0-9
    if use_punctuation:
        characters += string.punctuation #includes Special Characters like !@#$%^&*()

    if not characters:
        raise ValueError("At least one character type must be selected.")


    password = ''.join(random.choice(characters) for i in range(length))
    return password
password = generate_password(length, use_letters, use_digits, use_punctuation)
print("Generated password:", password)   
    
