# PasswordGenerator
import random
import string

def generate_password(length):
    if length <= 0:
        return "Password length must be greater than 0."
    
    
    characters = string.ascii_letters + string.digits + string.punctuation
    
    # Generate the password
    password = ''.join(random.choice(characters) for i in range(length))
    
    return password

def main():
    while True:
        try:
            length = int(input("Enter the desired length for the password: "))
            break
        except ValueError:
            print("Please enter a valid number.")

    password = generate_password(length)
    print(f"Generated password: {password}")

if __name__ == "__main__":
    main()
