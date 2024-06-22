# PRODIGY-INFOTECH-Internship

Task 01 Objective: Create a Python program that can encrypt and decrypt text using the Caesar Cipher algorithm. Allow users to input a message and a shift value to perform encryption and decryption.

Explanation: 

What is a Caesar Cipher?
A Caesar Cipher is a way to encrypt text by shifting each letter by a certain number of positions in the alphabet. 
For example, if you shift each letter by 3 positions, the letter "a" becomes "d", "b" becomes "e", and so on.

The code is a Python program that implements a Caesar Cipher(PRODIGY_CS_01.py).
Here's a breakdown of what each part does:

Function caesar_cipher This function takes two inputs:

text: the message you want to encrypt or decrypt
shift: the number of positions to shift each letter in the alphabet
The function returns the encrypted or decrypted text.

How it works!

The function loops through each character in the input text.
For each character, it checks if it's an uppercase letter (using isupper()).
If it's uppercase, it encrypts the letter by shifting it by the shift amount. Here's the magic formula:
ord(char) gets the ASCII code of the character (e.g., "A" becomes 65).
+ shift adds the shift amount to the ASCII code.
- 65 adjusts the result to be within the range of uppercase letters (A-Z).
% 26 ensures that the result wraps around the alphabet (e.g., if you shift "Z" by 1, it becomes "A").
+ 65 converts the result back to an ASCII code.
chr() converts the ASCII code back to a character.
If the character is lowercase, the same process is applied, but with a different adjustment (- 97 instead of - 65) to account for the lowercase letter range (a-z).
The encrypted or decrypted character is added to the result string.
The function returns the complete result string.
Main Program The main program:

Asks the user to input a message (text) and a shift key (shift).
Calls the caesar_cipher function to encrypt the message with the given shift key.
Prints the encrypted text.
Calls the caesar_cipher function again, but with the negative of the shift key, to decrypt the encrypted text.
Prints the decrypted text.
