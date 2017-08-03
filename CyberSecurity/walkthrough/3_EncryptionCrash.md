# Symmetric Encryption

- Encrytion is a method of trasforming readable data, called plain text, into a form that is unreadable, which is called cypher text.
    - enables the storage or transmission of data in a form that is unreadable and which remains confidential and private
- Decryption is a process that turn cypher text back into readable plain text
- Two main components of encryption: 
    1. Algorithm (Public)
    2. Key (Secret)
- Symmetric algorithm uses the same key to encrypt and decrypt the file (Password becomes the key)
- Algorithms: DES, 3DES, Blowfish, RC4 (5, 6), AES 
- 256 or 128 is bit length or key space (strength)

# Asymmetric Encrytion

- Uses two keys (Public & Private) (Generated at the same time )
- RSA, ECC, DH, El Gamal
- Help solve the problem of exchanging or agreeing keys, and also allow for something called digital signatures
- If the message is encrypted by one key, the other key is required in order to decrypt that message
- Encrypt with
    - receiver's public key for **confidentiality** (PGP for email)
    - sender's private key for **authentication**
- Very slow compared to symmetric algorithm, which is why we have something called hybrid system (Public and private keys are used to exchange an agreed key, and we use symmetric algorithm to actually encrypt the data, eg. HTTPs using TLS and SSL, and so is PGP )