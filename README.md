def generate_password(length, use_letters=True, use_numbers=True, use_special_chars=True):
    characters = " "

    if use_letters:
        characters += string.ascii_letters    # Includes both uppercase and lowercase letters
    if use_numbers:
        characters += string.digits     # Includes digits 0-9
    if use_special_chars:
        characters += string.punctuation    # Includes special characters

    if not characters:
        return "You need to select at least one character set!"

    password = ''.join(random.choice(characters) for _ in range(length))
    return password


# User input for password preferences
try:
    length = int(input("Enter the desired password length: "))
    include_letters = input("Include letters? (y/n): ").lower() == 'y'
    include_numbers = input("Include numbers? (y/n): ").lower() == 'y'
    include_special_chars = input("Include special characters? (y/n): ").lower() == 'y'

 # Generate password based on user preferences
    password = generate_password(length, include_letters, include_numbers, include_special_chars)
    print(f"Generated Password: {password}")

except ValueError:
    print("Please enter a valid number for the length.")
