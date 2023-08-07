# Implementation of 256 bit AES Encryption and Decryption Standard
This project shows the design of 256-bit AES Encryption and Decryption Algorithms
## AES Encryption and Decryption Standard
AES 256 aims to encrypt plaintext of 128 bits into cipher text, with the help of a 256-bit secret key. The ciphertext is transferred to the receiver, and using the same secret key, the ciphertext is decrypted to give back the same plaintext.
## Encryption
The encryption process involves the following algorithms for the generation of secret keys.
1) Pre-Round Transformation
2) Substitute Bytes
3) Shift Rows
4) Mix Columns
5) Add Round Key
![Untitled Diagram drawio](https://github.com/Manikanta-IITB/Implementation_of_256_bit_AES_Encryption_and_Decryption_Standard/assets/138108630/ff2f24da-3bb7-4d95-99ce-900a73407e41)
### Pre-Round Transformation
This step is bitwise XOR of plaintext and key 0. Required keys (key2 to key14) are provided by the
key expansion process.
### Substitute Bytes
The 16 input bytes are substituted by looking up a fixed table (S-box). The output is also a matrix of four rows and four columns.
### Shift Rows
After BYTEs substitution, the 128-bit state matrix undergoes shift rows operation. Each of the four rows of the matrix is shifted to the left in a circular fashion, respectively.
1) The first row is not shifted (Shifted zero bytes to the left).
2) The second row is shifted one position (one byte) to the left.
3) The third row is shifted to two positions (two bytes) to the left.
4) The fourth row is shifted three positions (three bytes) to the left, circularly.
5) The result is a new matrix consisting of the same 16 bytes but shifted with respect to each other.
### Mix Columns
Each column of four bytes is now transformed individually, using a special mathematical function. This function takes one column as input and outputs four completely new column bytes which replace the original column. The result is another new matrix consisting of 16 new bytes.
### Add Round Key
The 16 bytes of the matrix are now considered as 128 bits and are XORed with the 128 bits of the round key (key n). Similar rounds are carried 14 times in total. (Excluding Mix Columns in the final round).
