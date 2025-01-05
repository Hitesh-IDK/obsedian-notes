#### Cryptography and its terms

*  Plain text
*  Cipher Text
*  Encryption 
*  Decryption
*  Cryptography
*  Cipher
*  Cryptoanalysis 
*  Cryptology

#### Symmetric Cipher Model

The five ingredients,
- Plain text
- Encryption Algorithm
- Secret Key
- Cipher Text
- Decryption Algorithm

![[Pasted image 20250105151739.png]]

Requirements of a secure use of Symmetric Cipher model,
- Use of strong encryption algorithms
- Secret key is shared in a secure manner

Model of a conventional Symmetric Crypto System
![[Pasted image 20250105175201.png]]

#### Cryptography

Characteristics or Characterization of cryptographic systems,
- Operation used for transforming plaintext to ciphertext - (Substitution & Transposition)
- The number of keys used - (Symmetric or single key or secret key and Asymmetric or two-key or public key)
- The way in which plain text is processed - (Block cipher & Stream cipher)

#### Caesar Cipher - Substitution Technique

- By Julius Caesar
- Replace each letter with letter standing three places further down
- Alphabets are wrapped, after Z is A
- C = E(3, p) = (p + 3) mod 26
- General formula - C = E(k, p)

Brute Force cryptoanalysis of Caesar Cipher
![[Pasted image 20250105193739.png]]

Why Brute force is easy to apply on Caesar Cipher
- The language of plain text is known to everyone
- There are only 25 possible keys to try
- The encryption and decryption algorithms are widely known

#### Monoalphabetic Cipher - Substitution Technique

- Permutation of 26, 26! number of possibilities
- 10 times more combinations than DES
- Removes the easiness of Brute Force 

Ways to Brute Force
- Relative frequency of english letters can be compared
- More probable with longer messages
- Other regularities like look for known words present in the text
- Looking for repeating sequence of cipher texts
- Relative frequency of two letter combinations - th is most common, look for most common terms in cipher and replace them as th

#### PlayFair Cipher

- Treats multiple letters of a text as single units for translation
- Uses 5x5 matrix constructed using a keyword, starting with keyword, rest of the non repeating letters fills the matrix, from top to bottom, left to right
![[Pasted image 20250105210521.png]]

Rules of encryption
- Two letter pairs are constructed
- Repeating letters are separated using a filler letter like x, ex LLO becomes Lx LO
- Two letters that appear in the same row is replaced with letters to the right, circularly wrapping
- Two letters that appear in the same column is replaced with letters to the top, circularly wrapping
- Otherwise, the plaintext letter in a pair is replaced by letters in its own row and column occupied by the other letter

#### Hill Cipher - (SKIPPED FOR NOW)

#### One Time Pad

- Random Key used is as long as the message to be sent, to avoid repeating
- One time use key, discarded after a single encryption and decryption
- A single cipher text can have multiple plausible plain texts based on the key used
- Security of the cipher text completely depends on the randomness of the key used

Two fundamental problems with One time pad,
- Practical problem of generating large quantities of random keys
- Problem of key distribution and protection


#### 