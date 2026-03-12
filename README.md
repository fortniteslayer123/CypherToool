Cypher Tool
A command-line tool for encrypting and decrypting messages using classical cypher techniques.

What It Does
This tool allows you to:

Encrypt plaintext messages using various classical ciphers.
Decrypt encrypted messages back to plaintext (original message).
Preserve non-alphabetic characters (numbers, punctuation, spaces) in their original form.
Choose from three different encryption algorithms.
Usage
Running the Tool
go run main.go
Example Session
=================================
Welcome to the Cypher Tool!
=================================

Select operation:
1. Encrypt
2. Decrypt
Enter your choice (1 or 2): 1

Select encryption type:
1. ROT13 - Rotate alphabet by 13 positions
2. Reverse - Reverse alphabet cipher (A<->Z, b<->y, etc.)
3. Caesar - Caesar cipher with shift of 3
Enter your choice (1, 2, or 3): 1

Enter your message: Hello, World! 123

--- Result ---
Uryyb, Jbeyq! 123
Input Validation
The tool automatically trims leading nad trailing whitespace from inputs.
Invalid selections will prompt you to enter again.
Empty messages are invalid input.
Non-alphabetic characters remain unchanged during encryption/decryption.
Supported Ciphers
1. ROT13 (Rotate by 13)
How it works: Each letter is replaced by the letter 13 positions forward in the alphabet. Since there are 26 letters, applying ROT13 twice returns the original text (it's its own inverse).

Example:

Plaintext: Hello
Encrypted: Uryyb
2. Reverse Alphabet
How it works: Each letter is replaced by its mirror position in the alphabet. A becomes Z, b becomes y, etc. Like ROT13, it's also its own inverse.

Example:

Plaintext: Hello
Encrypted: Svool
3. Caesar Cipher (Shift by 3)
How it works: Each letter is shifted 3 positions forward in the alphabet. This is the cipher famously used by Julius Caesar. To decrypt, shift 3 positions backward.

Example:

Plaintext: Hello
Encrypted: Khoor
Implementation Details
Allowed Packages
bufio - For reading user input.
fmt - For formatted I/O.
os - For operating system functionality.
strconv - For converting strings.
strings - For string manipulation.
Key Features
Case preservation (uppercase stays uppercase, lowercase stays lowercase).
Non-alphabetic characters pass through unchanged.
Empty message got retry pop-up.
Robust input validation with retry logic.
Clean, modular code structure.
