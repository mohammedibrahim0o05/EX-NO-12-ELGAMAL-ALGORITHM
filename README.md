# EX-NO-12-ELGAMAL-ALGORITHM

### Name Mohammed Ibrahim MN 
### Roll No 212223100034

## AIM:
To Implement ELGAMAL ALGORITHM

## ALGORITHM:

1. ElGamal Algorithm is a public-key cryptosystem based on the Diffie-Hellman key exchange and relies on the difficulty of solving the discrete logarithm problem.

2. Initialization:
   - Select a large prime \( p \) and a primitive root \( g \) modulo \( p \) (these are public values).
   - The receiver chooses a private key \( x \) (a random integer), and computes the corresponding public key \( y = g^x \mod p \).

3. Key Generation:
   - The public key is \( (p, g, y) \), and the private key is \( x \).

4. Encryption:
   - The sender picks a random integer \( k \), computes \( c_1 = g^k \mod p \), and \( c_2 = m \times y^k \mod p \), where \( m \) is the message.
   - The ciphertext is the pair \( (c_1, c_2) \).

5. Decryption:
   - The receiver computes \( s = c_1^x \mod p \), and then calculates the plaintext message \( m = c_2 \times s^{-1} \mod p \), where \( s^{-1} \) is the modular inverse of \( s \).

6. Security: The security of the ElGamal algorithm relies on the difficulty of solving the discrete logarithm problem in a large prime field, making it secure for encryption.

## Program:
```
# ElGamal Encryption and Decryption

# Function for modular exponentiation
def mod_exp(base, exp, mod):
    return pow(base, exp, mod)


# Step 1: Input prime number and generator
p = int(input("Enter a large prime number (p): "))
g = int(input("Enter a generator (g): "))

# Step 2: Shankar enters private key
private_key = int(input("Enter Allahbakash's private key: "))

# Step 3: Calculate Shankar's public key
public_key = mod_exp(g, private_key, p)

print("Allahbakash's public key:", public_key)

# Step 4: Enter message and random k
message = int(input("Enter the message to encrypt (as a number): "))
k = int(input("Enter a random number k: "))

# Step 5: Encryption
c1 = mod_exp(g, k, p)

shared_key = mod_exp(public_key, k, p)

c2 = (message * shared_key) % p

print("Encrypted message (c1, c2):", (c1, c2))

# Step 6: Decryption
# Calculate inverse of shared key
shared_key_inverse = pow(shared_key, -1, p)

decrypted_message = (c2 * shared_key_inverse) % p

print("Decrypted message:", decrypted_message)

```



## Output:
<img width="1512" height="921" alt="image" src="https://github.com/user-attachments/assets/33f90291-8601-4bbe-b806-4082968a1a2d" />



## Result:
The program is executed successfully.
