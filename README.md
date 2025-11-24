# EX-NO-12-ELGAMAL-ALGORITHM

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
p = 23        
g = 5         
x = 6         
y = pow(g, x, p)

print("Public Key (p, g, y):", p, g, y)
print("Private Key x:", x)
m = 13
print("\nOriginal Message:", m)
k = 7

c1 = pow(g, k, p)
c2 = (m * pow(y, k, p)) % p

print("Encrypted (c1, c2):", (c1, c2))
s = pow(c1, x, p)         
s_inv = pow(s, p-2, p)     
m_dec = (c2 * s_inv) % p

print("Decrypted Message:", m_dec)
```
## Output:

<img width="470" height="152" alt="image" src="https://github.com/user-attachments/assets/530a4709-0119-4aa3-9d9f-d9b6c98928e2" />

## Result:
The program is executed successfully.
