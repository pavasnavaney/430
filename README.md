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



### Command line parameters
- "- -operation", "**-o**" : denotes the task - 'encrypt' or 'decrypt' or ('generate' or 'verify' for p4.py only). Only these 2 are valid tasks allowed.
- "- -input", "**-i**": the message to be encrypted or the cipher to be decrypted. For program 3 and 4, while decrypting feed in the JSON object with 4 parameters -> nonce, header, tag, and cipher. Encrypted Authentication and CBC MAC modes require these.
   For p4.py it is the message for which tag must be generated or verified.
- "- -decrypt_key", "**-d**": The key to be used for decrypting the cipher. Take from the output of encrypt task and feed it here.
   For p4.py it is the key using which we generate or re-generate tag.
- "- -mode", "**-m**": "CBC or CTR mode." This only required for program 2, to specify which mode to use in - CBC or counter mode.

### examples

1. p1.py program

   default mode: python3 p1.py
   sample encrypt only: python3 p1.py -o encrypt -i 'World Peace'
    sample encryption output is: 
       key generated is:  9OFgfZgLzKf
       Encrypted msg in bytes:  [110, 32, 52, 11, 2, 122, 55, 41, 27, 40, 3]
   
   sample decrypt only: python3 p1.py -o decrypt -i '[110, 32, 52, 11, 2, 122, 55, 41, 27, 40, 3]' -d '9OFgfZgLzKf'
    sample decryption output:
        Now decrypting: 
        Decrypted msg:  World Peace
        
2. p2.py program

   default mode: python3 p2.py
   
sample cbc encrypt only: python3 p2.py -o encrypt -i 'World Peace' -m 'cbc'

		sample encryption output is: 
		   key generated is:  ZsVNrsCDCl5d1cDQ
		   Encrypted msg in bytes:  {"iv": "MoGy9uYv/uWM+yfOxfQezQ==", "ciphertext": "K116PFN2wstru4/RQ1gljw=="}


 sample cbc decrypt only: python3 p2.py -o decrypt -i '{"iv": "MoGy9uYv/uWM+yfOxfQezQ==", "ciphertext": "K116PFN2wstru4/RQ1gljw=="}' -d 'ZsVNrsCDCl5d1cDQ' -m 'cbc'
 
		sample decryption output:
			Now decrypting: 
			Decrypted msg:  World Peace

sample ctr encrypt only: python3 p2.py -o encrypt -i 'World Peace' -m 'ctr'

		sample encryption output is: 
		   key generated is:  VfyHWqAojG5pzmKF
		   Encrypted msg in bytes:  {"iv": "HXRZUzZh+uR6qePCWFBe6A==", "ciphertext": "7OvZyBPXqGRjqvSbhy0v5w=="}


 sample ctr decrypt only: python3 p2.py -o decrypt -i '{"iv": "HXRZUzZh+uR6qePCWFBe6A==", "ciphertext": "7OvZyBPXqGRjqvSbhy0v5w=="}' -d 'VfyHWqAojG5pzmKF' -m 'ctr'
 
		sample decryption output:
			Now decrypting: 
			Decrypted msg:  World Peace

3. p3.py program

   default mode: python3 p3.py
   sample encrypt only: python3 p3.py -o encrypt -i 'World Peace'
    sample encryption output is: 
       key generated is:  8XEhPCGblvNghBPe
       Encrypted msg in bytes:  {"nonce": "mRAo9jUAnkYCCGKrklpIMg==", "header": "OUI1QkpVQXFHQzE=", "ciphertext": "n3pl1X7whYGeD9E=", "tag": "ywdVCyE7wdvtx9LC4OxRfw=="}
   
 sample decrypt only: python3 p3.py -o decrypt -i '{"nonce": "mRAo9jUAnkYCCGKrklpIMg==", "header": "OUI1QkpVQXFHQzE=", "ciphertext": "n3pl1X7whYGeD9E=", "tag": "ywdVCyE7wdvtx9LC4OxRfw=="}' -d '8XEhPCGblvNghBPe'
    sample decryption output:
        Now decrypting: 
        Decrypted msg:  World Peace






