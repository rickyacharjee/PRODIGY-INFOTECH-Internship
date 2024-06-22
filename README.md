# PRODIGY-INFOTECH-Internship
____________________________________________________________________________________________________________________________________________________________________
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


___________________________________________________________________________________________________________________________________________________________________

Task 03 Objective: Build a tool that assesses the strength of a password based on criteria such as length, presence of uppercase and lowercase letters, numbers, and special characters. Provide feedback to users on the password's strength.

Explanation:

What is this code for?
This code checks if a password is strong enough and provides tips to make it stronger if it's not.

The Function check_password_complexity This function takes one input:

password: the password you want to check
The function returns a dictionary with two keys:

valid: a boolean value indicating whether the password is valid or not
tips: a list of strings providing tips to strengthen the password if it's not valid

How it works!

The function initializes an empty list tips to store tips and sets valid to True, assuming the password is valid initially.
It checks the password's length. If it's less than 12 characters, it sets valid to False and adds a tip to the tips list.
It checks if the password contains at least one:
Uppercase letter (using a regular expression r"[A-Z]")
Lowercase letter (using a regular expression r"[a-z]")
Number (using a regular expression r"\d")
Special character (using a regular expression r"[!@#$%^&*()_+=-{};:'<>,./?]")
If any of these checks fail, it sets valid to False and adds a corresponding tip to the tips list. 4. The function returns a dictionary with the valid status and the tips list.

Main Program- The main program:

Asks the user to input a password.
Calls the check_password_complexity function to check the password.
If the password is valid, it prints a success message.
If the password is not valid, it prints an error message and lists the tips to strengthen the password.
Example If you input a password like "hello", the program will:

Check the password and find that it's not valid (too short, no uppercase letter, no number, no special character)
Print an error message and provide tips to strengthen the password, such as:
"Password should be at least 12 characters long."
"Password should contain at least one uppercase letter."
"Password should contain at least one number."
"Password should contain at least one special character."

___________________________________________________________________________________________________________________________________________________________________

Task 04 Objective: Create a basic keylogger program that records and logs keystrokes. Focus on logging the keys pressed and saving them to a file. Note: Ethical considerations and permissions are crucial for projects involving keyloggers.

Explanation:

What is this code for? 
This code is a simple keylogger, which is a program that records every key you press on your keyboard. The recorded keys are saved to a file called "keylog.txt".

The Function keylogger:This function does the following:

Creates a file called "keylog.txt" and writes the current date and time to it, indicating when the keylogger started.
Enters an infinite loop, which means it will keep running until it's manually stopped.
Inside the loop, it waits for a key press event using the keyboard.read_event() function.
When a key is pressed, it checks if the key is the "esc" key. If it is, the loop breaks, and the keylogger stops.
If the key is not "esc", it writes the key to the "keylog.txt" file and prints it to the console.
Once the loop breaks (i.e., the "esc" key is pressed), it writes the current date and time to the "keylog.txt" file, indicating when the keylogger stopped.

How it works!

The keyboard module is used to read keyboard events.
The time module is used to get the current date and time.
The with open() statement is used to open the "keylog.txt" file in write mode ("w" or "a"). This ensures that the file is properly closed when we're done with it.
The f.write() function is used to write to the file.
The print() function is used to print the key to the console.
Note This code requires the keyboard module, which is not a built-in Python module. You need to install it using pip install keyboard before running this code.

Important Keyloggers can be used for malicious purposes, such as spying on someone's keyboard input without their knowledge. This code is for educational purposes only, and you should not use it to invade someone's privacy. Always use keyloggers responsibly and with the user's consent.
___________________________________________________________________________________________________________________________________________________________________

Task 05 Objective: Develop a packet sniffer tool that captures and analyzes network packets. Display relevant information such as source and destination IP addresses, protocols, and payload data. Ensure the ethical use of the tool for educational purposes

Explanation:
What is this code for? 
This code is a simple network packet analyzer, which captures and analyzes network packets sent and received by your computer. It's like a "wiretap" for your network traffic.

The Function sniff_packets: This function is called for each captured packet. It does the following:

Checks if the packet has an IP layer (i.e., it's an IP packet).
Extracts the source IP address (src_ip) and destination IP address (dst_ip) from the packet.
Checks if the packet has a Raw layer (i.e., it contains payload data).
If it does, extracts the payload data and prints it.
Writes the packet information (source IP, destination IP, and payload) to a file called "captured_packets.txt".
The Main Program The main program:

Prints a message indicating that packet sniffing has started.
Uses the scapy.sniff function to capture packets on the "eth0" network interface (you may need to change this to your actual network interface).
Sets store=False to prevent Scapy from storing the packets in memory.
Sets prn=sniff_packets to call the sniff_packets function for each captured packet.
Catches the KeyboardInterrupt exception, which is raised when the user presses Ctrl+C to stop the program.
Prints a message indicating that packet sniffing has stopped.

How it works!

Scapy is a powerful Python library for packet manipulation and analysis.
The scapy.sniff function captures packets on a specified network interface.
The prn parameter specifies a function to call for each captured packet.
The sniff_packets function analyzes each packet and extracts relevant information.
The packet information is written to a file for later analysis.
Note This code requires the Scapy library, which is not a built-in Python library. You need to install it using pip install scapy before running this code.

Important Packet sniffing can be used for malicious purposes, such as intercepting sensitive information. This code is for educational purposes only, and you should not use it to intercept packets without the owner's consent. Always use packet sniffing responsibly and with the owner's knowledge.
