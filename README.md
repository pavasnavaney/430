# CS430 Assignment 1

## Name: Pavas Navaney
## USCID: 3407804292

### Basic guidelines to operate programs.

1. One-Time Pad
- The Program consists of two files OneTimePad.java and StringGenerator.java.
- The progams take in command line inputs for operation type(encrypt) and the message in case of encryption.
- The progams take in command line inputs for operation type(decrypt) , the secret key and the byte[] ciphertext.
- All random strings generated(Secret Key in this case) are **true random strings** obtained from random.org's API.
- Please note that random strings by the API are only of **max length 20**. So **please make sure the message length is <=20**
	
  ### Example usage
   #### Encrypt
   Example usage : java OneTimePad encrypt pavas
   Sample Encryption output :
  
   	Your key is : g8sWF
	Please note it down in a safe place as you will need this to decrypt your message!
	Your encrypted message is : 23 89 5 54 53
  
  #### Decrypt
   Example usage : java OneTimePad decrypt g8sWF 23 89 5 54 53
   Sample Encryption output :
  
   	Your decrypted Message is : pavas
   
