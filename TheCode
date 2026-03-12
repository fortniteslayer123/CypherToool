package main

import (
	"bufio"
	"fmt"
	"os"
	"strings"
)

// Main logic, invoking other functions
func main() {
	// 1. Greet the user
	fmt.Println("=================================")
	fmt.Println("Welcome to the Cypher Tool!")
	fmt.Println("=================================")
	fmt.Println()

	// 2-4. Get input data
	toEncrypt, encoding, message := getInput()

	// 5. Perform operation and output result
	var result string

	if toEncrypt {
		// Encrypt
		switch encoding {
		case "rot13":
			result = encrypt_rot13(message)
		case "reverse":
			result = encrypt_reverse(message)
		case "caesar":
			result = encrypt_caesar(message)
		}
	} else {
		// Decrypt
		switch encoding {
		case "rot13":
			result = decrypt_rot13(message)
		case "reverse":
			result = decrypt_reverse(message)
		case "caesar":
			result = decrypt_caesar(message)
		}
	}

	fmt.Println("\n--- Result ---")
	fmt.Println(result)
}

// Get the input data required for the operation
func getInput() (toEncrypt bool, encoding string, message string) {
	scanner := bufio.NewScanner(os.Stdin) // create a scanner object that reads text input from the user's keyboard.

	// Get operation encrypt or decrypt (toEncrypt)
	for {
		fmt.Println("Select operation:")
		fmt.Println("1. Encrypt")
		fmt.Println("2. Decrypt")
		fmt.Print("Enter your choice (1 or 2): ")

		if !scanner.Scan() { // scanner.Scan() returns false if it fails to read input, skip to next iteration
			continue		// scanner.Scan() is called directly inside condition
		}

		input := strings.TrimSpace(scanner.Text()) // scanner.Text() get the text, read input and trim spaces

		if input == "1" {
			toEncrypt = true
			break // break here to stop the loop
		} else if input == "2" {
			toEncrypt = false
			break
		}

		fmt.Println()
		fmt.Println("Invalid input. Please enter 1 or 2.")
		fmt.Println()
	}

	// Get encoding type (encoding)
	for {
		fmt.Println("\nSelect encryption type:")
		fmt.Println("1. ROT13 - Rotate alphabet by 13 positions")
		fmt.Println("2. Reverse - Reverse alphabet cipher (A↔Z, B↔Y, etc.)")
		fmt.Println("3. Caesar - Caesar cipher with shift of 3")
		fmt.Print("Enter your choice (1, 2, or 3): ")

		if !scanner.Scan() {
			continue
		}

		input := strings.TrimSpace(scanner.Text())

		if input == "1" {
			encoding = "rot13"
			break // the reason to break here is to exit the loop when valid input is received, because in the loop we didnt have any condition to exit the loop
		} else if input == "2" {
			encoding = "reverse"
			break
		} else if input == "3" {
			encoding = "caesar"
			break
		}

		fmt.Println()
		fmt.Println("Invalid input. Please enter 1, 2, or 3.")
		
	}

	// Get message (message)
	for {
		fmt.Print("\nEnter your message: ")

		if !scanner.Scan() {
			continue
		}

		input := strings.TrimSpace(scanner.Text())

		if input != "" {
			message = input
			break
		}
		
		fmt.Println()
		fmt.Println("Message cannot be empty. Please try again.")
		
	}

	return toEncrypt, encoding, message
}

// Encrypt the message with rot13
func encrypt_rot13(s string) string {
	var result = ""
	for i := 0; i < len(s); i++ {
		var l = s[i]
		if l >= 'a' && l <= 'z' {
			l = 'a' + (l-'a'+13)%26
		} else if l >= 'A' && l <= 'Z' {
			l = 'A' + (l-'A'+13)%26
		}
		result += string(l)
	}
	return result
}

// Encrypt the message with reverse
func encrypt_reverse(s string) string {
	var output []rune
	for _, ch := range s {
		if ch >= 'a' && ch <= 'z' {
			output = append(output, 'z'-(ch-'a'))
		} else if ch >= 'A' && ch <= 'Z' {
			output = append(output, 'Z'-(ch-'A'))
		} else {
			output = append(output, ch)
		}
	}
	return string(output)
}

// Encrypt the message with caesar cipher (shift by 3)
func encrypt_caesar(s string) string {
	var result string

	for _, char := range s {
		if char >= 'a' && char <= 'z' {
			result += string('a' + (char-'a'+3)%26)
		} else if char >= 'A' && char <= 'Z' {
			result += string('A' + (char-'A'+3)%26)
		} else {
			result += string(char)
		}
	}

	return result
}

// Decrypt the message with rot13
func decrypt_rot13(s string) string {
	// ROT13 is its own inverse
	return encrypt_rot13(s)
}

// Decrypt the message with reverse
func decrypt_reverse(s string) string {
	// Reverse alphabet is its own inverse
	return encrypt_reverse(s)
}

// Decrypt the message with caesar cipher (shift by -3)
func decrypt_caesar(s string) string {
	var result string

	for _, char := range s {
		if char >= 'a' && char <= 'z' {
			// Shift backwards by 3
			result += string('a' + (char-'a'+23)%26) // +23 is same as -3 (mod 26), it helps shorter the code because I dont have to handle negative values.
		} else if char >= 'A' && char <= 'Z' {
			result += string('A' + (char-'A'+23)%26)
		} else {
			result += string(char)
		}
	}

	return result
}
