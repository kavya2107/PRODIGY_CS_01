# PRODIGY_CS_01
def caesar_cipher(text, shift, encrypt=True):
    result = ""
    for char in text:
        if char.isalpha():  # Process only letters
            shift_amount = shift if encrypt else -shift
            base = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - base + shift_amount) % 26 + base)
        else:
            result += char  # Keep non-alphabet characters unchanged
    return result

# Example usage
plaintext = "HELLO KAVYA"
shift = 5
ciphertext = caesar_cipher(plaintext, shift)
decrypted_text = caesar_cipher(ciphertext, shift, encrypt=False)

print(f"Plaintext: {plaintext}")
print(f"Ciphertext: {ciphertext}")
print(f"Decrypted: {decrypted_text}")
