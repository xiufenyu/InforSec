# Symmetric Algorithms
They use a single, shared secret key to both encrypt and decrypt the data.      
| **Algorithm**                      | **KeySize**        | **Primary Key Class (JCA)**                       |
|------------------------------------|--------------------|---------------------------------------------------|
| AES (Advanced Encryption Standard) | 128, 192, 256 bits | javax.crypto.spec.SecretKeySpec                   |
| DES (Data Encryption Standard)     | 56 bits            | javax.crypto.spec.DESKeySpec  or SecretKeySpec    |
| 3DES (Triple DES)                  | 112 or 168 bits    | javax.crypto.spec.DESedeKeySpec  or SecretKeySpec |
| ChaCha20                           | 256 bits           | javax.crypto.spec.SecretKeySpec                   |
| Blowfish                           | 32–448 bits        | javax.crypto.spec.SecretKeySpec                   |
| Twofish                            | Up to 256 bits     | javax.crypto.spec.SecretKeySpec                   |


# Asymmetric Algorithms
These use a Key Pair: a Public Key (to encrypt) and a Private Key (to decrypt).             

| **Algorithm**                     | **Common Usage**                                        | **Primary Key Class (JCA)**                                                    |
|-----------------------------------|---------------------------------------------------------|-------------------------------------------------------------------|
| RSA                               | Used for digital signatures and "wrapping" AES keys.    | java.security.interfaces.RSAPublicKey java.security.interfaces.RSAPrivateKey   |
| ECC (Elliptic Curve Cryptography) | Used in Bitcoin, WhatsApp, and TLS 1.3.                 | java.security.interfaces.ECPublicKey java.security.interfaces.ECPrivateKey     |
| Diffie-Hellman (DH)               | Key Exchange (creating a shared key over an open line). | javax.crypto.interfaces.DHPublicKey javax.crypto.interfaces.DHPrivateKey|
| DSA (Digital Signature Algorithm) | Used strictly for signing, not for encrypting data.     | java.security.interfaces.DSAPublicKey java.security.interfaces.DSAPrivateKey   |
| EdDSA (e.g., Ed25519)             | A high-speed, high-security version of ECC.             | java.security.interfaces.EdECPublicKey java.security.interfaces.EdECPrivateKey |
