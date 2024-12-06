# File Encryptor Using Fernet (Cryptography Library)

This Python-based tool encrypts and decrypts files using symmetric encryption (AES) provided by the cryptography library's Fernet module. It generates a unique encryption key, encrypts files with that key, and allows decryption using the same key. This project is simple, secure, and effective for managing sensitive files.

Features
Symmetric Encryption: Uses AES (Advanced Encryption Standard) via the Fernet module.
Key Generation: Generates a secure random key for file encryption.
File Encryption and Decryption: Encrypt and decrypt any file using a key.
Key Storage: Save and load the encryption key from a file for future use.
CLI Usage: Easy command-line interface for encrypting and decrypting files.
Prerequisites
Python 3.x
cryptography library
bash
Copy code
pip install cryptography
How It Works
The program uses the cryptography.fernet module to securely encrypt and decrypt files. Here's how it functions:

Generate Key: A secure, random key is generated using Fernet.generate_key().
Encrypt File: The input file is read, encrypted using the key, and saved as an encrypted file.
Decrypt File: The encrypted file is read, decrypted using the same key, and saved as the original file.
Usage
1. Generate a key and save it:
python
Copy code
key = generate_key()
key_file = "encryption_key.key"
save_key(key, key_file)
This generates a key and saves it to the file encryption_key.key. This key must be kept safe for decryption later.
2. Encrypt a file:
python
Copy code
encrypt_file("plain_text.txt", "encrypted_file.txt", key)
The file plain_text.txt will be encrypted and saved as encrypted_file.txt.
3. Decrypt a file:
python
Copy code
decrypt_file("encrypted_file.txt", "decrypted_file.txt", key)
The encrypted file encrypted_file.txt will be decrypted and saved as decrypted_file.txt.
Full Example:
python
Copy code
# Generate and save encryption key
key = generate_key()
key_file = "encryption_key.key"
save_key(key, key_file)

# Encrypt a file
encrypt_file("plain_text.txt", "encrypted_file.txt", key)
print(f"File 'plain_text.txt' encrypted to 'encrypted_file.txt'")

# Decrypt a file
decrypt_file("encrypted_file.txt", "decrypted_file.txt", key)
print(f"File 'encrypted_file.txt' decrypted to 'decrypted_file.txt'")
Functions
generate_key()
Generates a secure random key for encryption and decryption.

save_key(key, key_file)
Saves the encryption key to a specified file.

load_key(key_file)
Loads the encryption key from a specified file.

encrypt_file(input_file, output_file, key)
Encrypts the specified input file and saves the encrypted content to the output file using the provided key.

decrypt_file(input_file, output_file, key)
Decrypts the specified encrypted file and saves the decrypted content to the output file using the provided key.

Example Files
Plain text file: plain_text.txt - Original file to be encrypted.
Encrypted file: encrypted_file.txt - Output file after encryption.
Decrypted file: decrypted_file.txt - Output file after decryption.
Security Considerations
Key management: The encryption key is critical for decrypting files. Ensure that the key file is stored securely and kept private.
AES Key Size: Fernet ensures that the key used for encryption is always 32 bytes, which is compatible with AES encryption standards.
