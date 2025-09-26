# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```
#include <stdio.h>
 #include <string.h>
 void encrypt(char *message, char *key, char *encryptedMessage, int
 messageLength) {
 int keyLength = strlen(key);
 for (int i = 0; i < messageLength; i++) {
 // Encrypt by XORing message byte with key byte
 encryptedMessage[i] = message[i] ^ key[i % keyLength];
 }
 encryptedMessage[messageLength] = '\0'; 
 }
 // Function to perform decryption (XOR again with the same key)
 void decrypt(char *encryptedMessage, char *key, char *decryptedMessage, int
 messageLength) {
 int keyLength = strlen(key);
 for (int i = 0; i < messageLength; i++) {
 // Decrypt by XORing encrypted byte with key byte
 decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength];
 }
 decryptedMessage[messageLength] = '\0'; // Null-terminate the decrypted
 }
 int main() {
 char message[100];
 char key[100];
 printf("\n**Simulation of DES encryption and decryption\n\n");
 // Get user input for the message
 printf("Enter the message to encrypt: ");
 fgets(message, sizeof(message), stdin);
 message[strcspn(message, "\n")] = '\0'; // Remove newline character if present
 // Get user input for the key
 printf("Enter the encryption key: ");
 fgets(key, sizeof(key), stdin);
 key[strcspn(key, "\n")] = '\0'; // Remove newline character if present
 int messageLength = strlen(message);
 // Buffers to hold encrypted and decrypted messages
 char encryptedMessage[100];
 char decryptedMessage[100];
 // Encrypt the message
 encrypt(message, key, encryptedMessage, messageLength);
 printf("Original Message: %s\n", message);
 printf("Encrypted Message: ");
 // Print encrypted message in hex format
 for (int i = 0; i < messageLength; i++) {
 printf("%02X ", (unsigned char)encryptedMessage[i]);
 }
 printf("\n");
 // Decrypt the message
 decrypt(encryptedMessage, key, decryptedMessage, messageLength);
 printf("Decrypted Message: %s\n", decryptedMessage);
 return 0;
 }
```

# OUTPUT:
<img width="922" height="256" alt="image" src="https://github.com/user-attachments/assets/6d646728-ab76-41b4-9bec-a12b00994145" />



# RESULT:
The program is executed successfully


