import random
import string

def generate_password(length=12):
    
    characters = string.ascii_letters + string.digits + string.punctuation
    
    password = ''.join(random.choice(characters) for _ in range(length))

    return password

def generate_multiple_passwords(number_of_passwords, password_length):
    passwords = [generate_password(password_length) for _ in range(number_of_passwords)]
    return passwords

if __name__ == "__main__":
    print("Password Generator")

    try:
        password_length = int(input("Enter the desired password length: "))
        number_of_passwords = int(input("Enter the number of passwords to generate: "))
    except ValueError:
        print("Please enter valid numeric values for password length and number of passwords.")
        exit()
    strong_passwords = generate_multiple_passwords(number_of_passwords, password_length)

    print("\nGenerated Strong Passwords:")
    for idx, password in enumerate(strong_passwords, start=1):
        print(f"Password {idx}: {password}")
