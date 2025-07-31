# Secure File Exchange (RSA + AES Hybrid)

## Encryption Flow
1. Bob generates RSA key pair.
2. Alice composes her message.
3. Alice creates a random AES-256 key and IV.
4. Alice encrypts the message using AES-256 (CBC mode).
5. Alice encrypts the AES key with Bob's RSA public key.
6. Bob decrypts the AES key using his private RSA key.
7. Bob uses the decrypted key and IV to decrypt the file.
8. Both verify integrity using SHA-256 hash.

## Comparison: AES vs. RSA

| Feature   | AES                          | RSA                          |
|-----------|------------------------------|------------------------------|
| Speed     | Extremely fast (symmetric)   | Slow (asymmetric)            |
| Use Case  | Bulk data encryption         | Key exchange, encrypting small data |
| Security  | Strong, with long keys       | Strong, but longer key needed for same strength |

AES is ideal for encrypting large files due to its speed. RSA is slow but secure for encrypting small items (like symmetric keys). Hybrid schemes use RSA to protect an AES key, combining safety and performance.

