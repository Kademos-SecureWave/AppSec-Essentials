# Cryptography Guide

## Introduction

Cryptography is essential for enhancing data security during processing, storage, and communication. It encompasses algorithms ensuring confidentiality, integrity, authentication, and nonrepudiation. This guide delves into cryptographic principles, focusing on private key cryptosystems.

### Goals of Cryptography

1. **Confidentiality**: Protecting data privacy, both at rest and in transit, using symmetric (shared secret key) and asymmetric (public and private keys) cryptosystems.  For instance, encrypting a user's personal data using AES before storing it in a database.
2. **Integrity**: Ensuring data is unaltered and authentic, often enforced through digital signatures. For instance, Using SHA-256 to generate a hash of a document, ensuring it hasn't been altered when compared at a later time.
3. **Authentication**: Verifying user identities in communication, typically through shared-secret systems or public key authentication.  Implementing RSA digital signatures to verify the sender of a message is a great example of this.
4. **Nonrepudiation**: Providing proof of origin and preventing denial of message sending, usually achieved with public key cryptosystems. For Instance, Using public key infrastructure (PKI) where the sender cannot deny sending a message, as in secure email communications.

### Cryptography Concepts

- **Plaintext and Ciphertext**: In cryptography, plaintext usually means unencrypted information and Ciphertext is encrypted text transformed from plaintext using an encryption algorithm. An example would be converting 'Hello World' into an unreadable format using an encryption algorithm..
- **Keys**: A key in cryptography is a piece of information, usually a string of numbers or letters that are stored in a file, which, when processed through a cryptographic algorithm, can encode or decode cryptographic data. The foundation of cryptography, where the security of the system depends on key confidentiality e.g A 'password' used for encrypting/decrypting data. The security lies in keeping this key secret
- **Algorithms**: the mathematical equation used to scramble the plain text and make it unreadable. Algorithims are the rules for encryption and decryption, generally public for scrutiny and validation. Rules or methods like AES or RSA are used for performing encryption and decryption.

### Types of Cryptosystems

1. **Symmetric Key Cryptography**: Uses a single key for encryption and decryption.
2. **Asymmetric Key Cryptography**: Employs a pair of keys – public and private – for secure communication.
3. **Hashing Algorithms**: Creates a unique, fixed-size hash value from data, ensuring data integrity.

### Cipher Systems

- **Transposition Ciphers**: Rearrange plaintext letters to form ciphertext.  Rearranging the letters in 'HELLO' to 'EHLLO' for instance
- **Substitution Ciphers**: Replace characters or bits in the plaintext with different ones. For example, replacing each letter in 'ABC' with 'ZXY'.
- **Block Ciphers**: Encrypts data in fixed-size blocks using algorithms like AES.
- **Stream Ciphers**: Encrypts data one bit at a time, often used in streaming services.

### Cryptographic Lifecycle

Cryptography systems have a lifespan influenced by advancing technology. Key lengths and algorithm strength should be updated periodically to ensure continued security. For Example, Updating from SHA-1 to SHA-256 for hashing due to increased security needs and vulnerabilities found in SHA-1.

### Best Practices

1. **Key Management**: Ensure keys are securely generated, stored, and destroyed. Example: Using hardware security modules (HSM) for key storage.
2. **Choose Appropriate Cryptosystem**: Select symmetric or asymmetric based on the use case.  E.g Selecting AES for fast encryption of large data volumes.
3. **Implement Secure Key Exchange**: Safeguard the exchange of keys, especially in public key cryptography. Use protocols like Diffie-Hellman for exchanging keys over an insecure channel.
4. **Apply Cryptography Correctly**: Understand the context of usage and implement cryptographic principles accordingly. Ensure SSL/TLS is properly implemented for secure web communications.
5. **Regularly Update and Review**: Keep up with advances in cryptography and update cryptographic practices.  Such as moving to TLS 1.3.

### Conclusion

Cryptography plays a vital role in the security of modern applications. Understanding and correctly implementing cryptographic principles is crucial for protecting data confidentiality, integrity, authentication, and nonrepudiation. As technology evolves, staying updated with the latest cryptographic standards and practices is essential for maintaining robust security.

----------

This guide is part of our AppSec Essentials series on GitHub, aimed at helping beginners, enthusiasts, and professionals in understanding the fundamental principles of application security. For more in-depth discussions, please visit the repository.
