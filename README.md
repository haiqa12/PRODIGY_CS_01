def encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            encrypted_char = chr((ord(char) - shift_base + shift) % 26 + shift_base)
            encrypted_text += encrypted_char
        else:
            encrypted_text += char
    return encrypted_text

def decrypt(text, shift):
    decrypted_text = ""
    for char in text:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            decrypted_char = chr((ord(char) - shift_base - shift) % 26 + shift_base)
            decrypted_text += decrypted_char
        else:
            decrypted_text += char
    return decrypted_text

def main():
    print("Caesar Cipher Encryption/Decryption")
    choice = input("Type 'encrypt' to encrypt a message, or 'decrypt' to decrypt a message: ").lower()
    text = input("Enter your message: ")
    shift = int(input("Enter the shift value: "))

    if choice == 'encrypt':
        encrypted_message = encrypt(text, shift)
        print(f"Encrypted message: {encrypted_message}")
    elif choice == 'decrypt':
        decrypted_message = decrypt(text, shift)
        print(f"Decrypted message: {decrypted_message}")
    else:
        print("Invalid choice! Please type 'encrypt' or 'decrypt'.")

if __name__ == "__main__":
    main()
