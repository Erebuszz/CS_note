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

# Hash Functions

- Provide integrity (Detect unintentional modifications)
- Turn an input into a fixed size string of characters - **Message Digest**, which can never be converted back to the original input
- MD2, MD4, MD5, SHA, SHA1 (weak)  /, SHA256, SHA384, SHA512, etc. 
- Can be used to store the hash of a password into the database
- Can also include a pre-agreed shared secret into the message, and then hash that message, which is known as **HMAC**
- [Hashes Examples](https://defuse.ca/truecrypt-7.1a-hashes.htm)
- [QuickHash GUI](http://www.quickhash-gui.org/)
- [Hashing Security](https://crackstation.net/hashing-security.htm)

# Digital Signatures

- A hash value that has been encrypted with the sender’s private key.
- The act of signing means encrypting the message’s hash value with a private key.
- Requires public/private keys. And PKI in a practical sense. 
- Encrypted, which provides confidentiality.
- Hashed, which provides integrity.
- Digitally signed, which provides authentication, nonrepudiation, and integrity.
- Encrypted and digitally signed, which provides confidentiality, authentication, nonrepudiation, and integrity.
- [Symantec Code-signing](https://www.symantec.com/en/uk/code-signing/)
- [Windows 10 Device Guard using Digital Signatures](https://venturebeat.com/2015/04/21/microsofts-device-guard-locks-down-windows-10-only-allows-running-trusted-apps/)
- [Making and verifying signatures](https://www.gnupg.org/gph/en/manual/x135.html)

# Secure Sockets Layer (SSL) and Transport layer security (TLS)

- Include all of the cryptographic technology mentioned above
- Cryptographic protocols designed to provide communication security over a network or the Internet (TLS is newer)
- Not only for web browsing (HTTPS) but FTP and VPN
    - Private (confidential) -> symmetric
    - Authenticated -> public key, certificates, digital signatures
    - Integrity -> message authentication code (MAC)
- [Wikipedia Transport Layer Security (TLS) page](https://en.wikipedia.org/wiki/Transport_Layer_Security)

## Cipher Suite

- A concept used in TLS / SSL
- Before TLS version 1.3, a cipher suite is a named combination of authentication, encryption, message authentication code (MAC) and key exchange algorithms used to negotiate the security settings.
- In the current TLS 1.3 draft document, cipher suites are only used to negotiate encryption and HMAC algorithms
- [Mozilla Cipher Suite Recommendations](https://wiki.mozilla.org/Security/Server_Side_TLS)
- [Weakdh Cipher Suite Recommendations](https://weakdh.org/sysadmin.html)
- [Steve Gibson's Cipher Suite Recommendations](https://www.grc.com/miscfiles/SChannel_Cipher_Suites.txt)