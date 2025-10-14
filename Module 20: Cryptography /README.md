# 🔐 Cryptography Concepts and Encryption Algorithms
Cryptography enables one to secure transactions, communications, and other processes performed in the electronic world. Encryption is the process of converting readable plaintext into an unreadable ciphertext using a set of complex algorithms that transform the data into blocks or streams of random alphanumeric characters. <br>
This section deals with cryptography and its associated concepts, which will enable you to understand the advanced topics covered later in this module. It also deals with ciphers and various encryption algorithms such as DES, AES, RC4, RC5, RC6, DSA, RSA, MD5, SHA, etc. 

---
## Cryptography 
“Cryptography” comes from the Greek words **kryptos**, meaning “concealed, hidden, veiled, secret, or mysterious,” and **graphia**, meaning “writing”; thus, cryptography is “the art of secret writing.” 

Cryptography is the method of securing information by converting readable data into an unreadable code using encryption keys. It ensures that sensitive data like emails, online transactions, and personal or corporate information stay protected during transmission. Only authorized users with the correct key can decrypt the data back into its original form, keeping communication private and secure from unauthorized access.

### Objectives of Cryptography
- **Confidentiality:** Assurance that the information is accessible only to those authorized to access it.
- **Integrity:** Trustworthiness of data or resources in terms of preventing improper and unauthorized changes.
- **Authentication:** Assurance that the communication, document, or data is genuine.
- **Nonrepudiation:** Guarantee that the sender of a message cannot later deny having sent the message and that the recipient cannot deny having received the message.

### Cryptography Process
Plaintext (readable format) is encrypted by means of encryption algorithms such as RSA, DES, and AES, resulting in a ciphertext (unreadable format) that, on reaching the destination, is decrypted into readable plaintext.

<p align="center">
  <img width="495" height="100" alt="image" src="https://github.com/user-attachments/assets/a2f66621-b6e8-4471-b0ec-46e03fc15765" />
</p>

### Types of Cryptography
Cryptography is categorized into two types according to the number of keys employed for encryption and decryption: 

- **Symmetric Encryption** <br>
   Symmetric encryption is also known as secret-key cryptography, as it uses only one secret key to encrypt and decrypt the data, means symmetric encryption uses a single secret key for both encrypting and decrypting data. The sender encrypts the message with this key, and the receiver uses the same key to turn it back into readable form. It’s fast and efficient for secure communication between trusted parties, but not ideal for large networks like the Internet because both sides must share the key in advance. This limitation led to the development of asymmetric encryption, which uses separate keys for encryption and decryption.

  <p align="center">
    <img width="493" height="127" alt="image" src="https://github.com/user-attachments/assets/8859d998-0df1-4e85-b410-d003e1e8e531" />
  </p>

- **Asymmetric Encryption** <br>
  Asymmetric encryption, or public-key cryptography, uses two keys—a public key for encryption and a private key for decryption. The public key is shared openly, while the private key is kept secret by the owner. This method ensures that only the intended recipient can decrypt the data, providing confidentiality, authentication, and integrity. It also prevents key-sharing risks since private keys are never transmitted. Digital signatures are often used with asymmetric encryption to verify the sender’s identity and ensure the message hasn’t been altered.

  Asymmetric encryption uses the following sequence to send a message:
  1. An individual finds the public key of the person he or she wants to contact in a directory.
  2. This public key is used to encrypt a message that is then sent to the intended recipient.
  3. The receiver uses the private key to decrypt the message and reads it.

   <p align="center">
     <img width="464" height="109" alt="image" src="https://github.com/user-attachments/assets/eb0ce245-7c68-4788-986f-2396c7b430d8" />
   </p>

 ### Strengths and Weaknesses of Crypto Methods 
 | **Category** | **Symmetric Encryption** | **Asymmetric Encryption** |
|---------------|---------------------------|-----------------------------|
| **Strengths** | - Faster and easier to implement, as the same key is used to encrypt and decrypt data.<br>- Requires less processing power.<br>- Can be implemented in application-specific integrated chip (ASIC).<br>- Prevents widespread message security compromise as different secret keys are used to communicate with different parties.<br>- The key is not bound to the data being transferred on the link; therefore, even if the data are intercepted, it is not possible to decrypt it. | - Convenient to use, as the distribution of keys to encrypt messages is not required.<br>- Enhanced security, as one need not share or transmit private keys to anyone.<br>- Provides digital signatures that cannot be repudiated. |
| **Weaknesses** | - Lack of secure channel to exchange the secret key.<br>- Difficult to manage and secure too many shared keys that are generated to communicate with different parties.<br>- Provides no assurance about the origin and authenticity of a message, as the same key is used by both the sender and the receiver.<br>- Vulnerable to dictionary attacks and brute-force attacks. | - Slow in processing and requires high processing power.<br>- Widespread message security compromise is possible (i.e., an attacker can read complete messages if the private key is compromised).<br>- Messages received cannot be decrypted if the private key is lost.<br>- Vulnerable to man-in-the-middle and brute-force attacks. |

---
## Government Access to Keys (GAK) 
Government Access to Keys (GAK) is a policy that requires individuals and organizations to provide their cryptographic keys to government authorities when requested by law. This allows law enforcement agencies to decrypt communications or data during investigations involving national security or cybercrimes. Under this system, software companies may be obligated to share copies of encryption keys—or partial keys that the government can later decrypt. The government claims it will safeguard these keys securely and only use them under proper legal authorization, such as a court-issued warrant, similar to how traditional wiretapping operates for phone surveillance.

To manage this process, governments often use a method known as **key escrow**, where encryption keys are stored with a trusted third party—usually a government agency—that can access or release them under specific legal conditions. However, this system raises serious concerns about privacy and data protection. If a single government-held key secures multiple other keys or sensitive data, a single compromise could expose vast amounts of private information. Furthermore, agencies holding the keys may not fully understand the sensitivity of the data they protect, making it difficult to ensure adequate safeguards.

This creates a major trust and security issue: while GAK aims to help governments prevent crime and ensure national security, it also introduces the risk of misuse, unauthorized access, and large-scale data breaches. Before disclosing their encryption keys, key owners must have strong assurance that these keys will be stored and managed with the highest security standards to protect both individual privacy and organizational interests.

<p align="center">
  <img width="561" height="154" alt="image" src="https://github.com/user-attachments/assets/db802e70-f1a4-4430-989b-f5af468507c6" />
</p>

---
## Ciphers 
A cipher in cryptography is a mathematical algorithm used to secure data by converting readable information, known as plaintext, into an unreadable format called ciphertext. This process, known as encryption or encipherment, ensures that only authorized users with the correct decryption key can restore the original message through a process called decipherment. Ciphers are the foundation of secure communication systems used in the Internet, mobile networks, and other digital platforms to protect sensitive data from unauthorized access.

There are different types of ciphers—some are open-source, where the algorithm is publicly available but the key remains secret, allowing transparency and peer review. Others are closed-source, used in specialized or restricted environments like the military, where both the algorithm and keys are kept confidential for enhanced security. Depending on their design and purpose, ciphers can be freely available for public use or distributed under licenses. Overall, ciphers are vital for maintaining data confidentiality, integrity, and privacy in today’s interconnected digital world.

### Types of ciphers 

<p align="center">
  <img width="627" height="239" alt="image" src="https://github.com/user-attachments/assets/11825ae4-134d-434e-95d0-ba66a1f8a81e" />
</p>

Ciphers are of two main types: classical and modern. 
- **Classical Ciphers**
  Classical ciphers are the most basic type of ciphers, which operate on letters of the alphabet (A–Z). These ciphers are generally implemented either by hand or with simple mechanical devices. Because these ciphers are easily deciphered, they are generally unreliable.

  **Types of classical ciphers**
  - **Substitution cipher:** The user replaces units of plaintext with ciphertext according to a regular system. The units may be single letters, pairs of letters, or combinations of them, and so on. The recipient performs inverse substitution to decipher the text. Examples include the Beale cipher, autokey cipher, Gronsfeld cipher, and Hill cipher. <br>
    For example, “HELLO WORLD” can be encrypted as “PSTER HGFST” (i.e., H=P, E=S, etc.).
  
  - **Transposition cipher:** Here, letters in the plaintext are rearranged according to a regular system to produce the ciphertext. For example, “**CRYPTOGRAPHY**” when encrypted becomes “**AOYCRGPTYRHP**.” Examples include the rail fence cipher, route cipher, and Myszkowski transposition.

- **Modern Ciphers** <br>
  Modern ciphers are designed to withstand a wide range of attacks. They provide message secrecy, integrity, and authentication of the sender. A user can calculate a modern cipher using a one-way mathematical function that is capable of factoring large prime numbers.

  **Types of Modern ciphers**
  - **Based on the type of key used**
    - **Symmetric-key algorithms (Private-key cryptography):** Use the same key for encryption and decryption.
    - **Asymmetric-key algorithms (Public-key cryptography):** Use two different keys for encryption and decryption.

  - **Based on the type of input data**
    - **Block cipher:** Deterministic algorithms operating on a block (a group of bits) of fixed size with an unvarying transformation specified by a symmetric key. Most modern ciphers are block ciphers. They are widely used to encrypt bulk data. Examples include DES, AES, IDEA, etc. When the block size is less than that used by the cipher, padding is employed to achieve a fixed block size.
    - **Stream cipher:** Symmetric-key ciphers are plaintext digits combined with a key stream (pseudorandom cipher digit stream). Here, the user applies the key to each bit, one at a time. Examples include RC4, SEAL, etc

---
## Symmetric Encryption Algorithms 
The table below shows specified symmetric encryption algorithms, including information such as cipher type, key size, block size, and application areas.

I see you have provided two images containing information about various cryptographic algorithms. I'll combine the data from both into a single, comprehensive table in **GitHub-flavored Markdown** format.

| Algorithm | Cipher Type | Key Size (bits) | Block Size (bits) | Application Areas |
| :--- | :--- | :--- | :--- | :--- |
| **Data Encryption Standard (DES)** | Block | 56 bits | 64 bits | Legacy systems, early encryption standards |
| **Triple DES (3DES)** | Block | 112, 168 bits | 64 bits | Financial services, payment systems |
| **Advanced Encryption Standard (AES)** | Block | 128, 192, 256 bits | 128 bits | Secure communications, storage encryption, government standards |
| **RC4** | Stream | 40 to 2048 bits (variable) | - | Secure web traffic (HTTPS), Wi-Fi security (WEP/WPA), streaming encryption |
| **RC5** | Block | 0 to 2040 bits (variable) | 32, 64, 128 bits | Cryptographic libraries, secure communication |
| **RC6** | Block | 128, 192, 256 bits | 128 bits | Advanced encryption, AES competition finalist |
| **Blowfish** | Block | 32 to 448 bits (variable) | 64 bits | Replacement for DES, secure storage |
| **Twofish** | Block | 128, 192, 256 bits | 128 bits | File and disk encryption, open-source software |
| **International Data Encryption Algorithm (IDEA)** | Block | 128 bits | 64 bits | Secure email (PGP), data encryption |
| **Threefish** | Block | 256, 512, 1024 bits | 256, 512, 1024 bits | Disk encryption (Skein hash function) |
| **Serpent** | Block | 128, 192, 256 bits | 128 bits | High-security applications, AES competition finalist |
| **Camellia** | Block | 128, 192, 256 bits | 128 bits | Secure communications, Japanese encryption standard |
| **Tiny Encryption Algorithm (TEA)** | Block | 128 bits | 64 bits | Lightweight encryption, embedded systems |
| **CAST-128** | Block | 40 to 128 bits | 64 bits | Various software applications, secure communications |
| **CAST-256** | Block | 128, 160, 192, 224, 256 bits | 128 bits | Advanced encryption, cryptographic libraries |
| **ChaCha20** | Stream | 256 bits | - | Secure communications, modern encryption protocols |
| **Salsa20** | Stream | 256 bits | - | Secure communications, cryptographic protocols |

### Data Encryption Standard (DES) 
The Data Encryption Standard (DES) is a symmetric-key encryption method that uses the same secret key for both encryption and decryption. It operates on 64-bit blocks of data, where 56 bits of the key are used for encryption, and the remaining 8 bits are reserved for error detection. DES transforms plaintext into ciphertext through multiple rounds of complex substitutions and permutations, making it difficult to reverse without the correct key. As a block cipher, DES was widely used to secure sensitive data such as files and communications, and its design allowed efficient implementation in hardware for high-speed encryption.

Despite providing about 72 quadrillion possible key combinations, advances in computing power eventually made DES vulnerable to brute-force attacks. To strengthen its security, organizations adopted Triple DES (3DES), which applies the DES process three times using either two or three different keys. This greatly increased the encryption strength while maintaining compatibility with older systems. Although DES and 3DES are now considered outdated compared to modern algorithms like AES (Advanced Encryption Standard), they laid the foundation for many cryptographic techniques used in secure communications today.

### Triple Data Encryption Standard (3DES) 
Triple Data Encryption Standard (3DES) was developed as a temporary replacement for the original DES algorithm when it became too weak to protect sensitive information. Instead of creating an entirely new algorithm, 3DES strengthened DES by applying it three times in sequence using multiple keys. It uses three 56-bit keys—K1, K2, and K3—forming what’s called a “key bundle.” The encryption process first encrypts the data with K1, then decrypts it with K2, and finally encrypts it again with K3. This triple-layer process significantly increases security compared to single DES, making brute-force attacks much harder.

3DES can be implemented with three types of key configurations: using three unique keys, using two identical keys (where K1 and K3 are the same), or using one key repeated three times. The first setup, with three independent keys, provides the highest level of security, while using the same key for all three steps offers the least protection and is equivalent to regular DES. Though 3DES strengthened data security for many years, it is now considered outdated due to its slower performance and vulnerability to modern cryptographic attacks, leading to its gradual replacement by more advanced algorithms like AES.

### Advanced Encryption Standard (AES) 
The Advanced Encryption Standard (AES) is a National Institute of Standards and Technology (NIST) specification for the encryption of electronic data. It also helps to encrypt digital information such as telecommunications, financial, and government data. US government agencies have been using it to secure sensitive but unclassified material. 

AES consists of a symmetric-key algorithm: both encryption and decryption are performed using the same key. It is an iterated block cipher that works by repeating the defined steps multiple times. It has a 128-bit block size, with key sizes of 128, 192, and 256 bits for AES-128, AES-192, and AES-256, respectively. The design of AES makes its use efficient in both software and hardware. It works simultaneously at multiple network layers. 

#### AES Pseudocode
AES is a symmetric block cipher that transforms an input block into ciphertext by repeatedly mixing bytes and keys through a fixed number of rounds (Nr), where Nr depends on key size. Below is the original pseudocode followed by a short, plain explanation of each line with a tiny code-like snippet showing what each step does.
```txt
Cipher (byte in [4*Nb], byte out [4*Nb], word w[Nb*(Nr+1)]) begin
  byte state[4, Nb]
  state = in
  AddRoundKey (state, w)
  for round = 1 step 1 to Nr-1
    SubBytes(state)
    ShiftRows(state)
    MixColumns(state)
    AddRoundKey(state, w+round*Nb)
  end for
  SubBytes(state)
  ShiftRows(state)
  AddRoundKey(state, w+Nr*Nb)
  out = state
end
```

### RC4, RC5, and RC6 Algorithms 
Symmetric encryption algorithms developed by RSA Security are discussed below. 
- **RC4** <br>
  RC4 is a variable key-size symmetric-key stream cipher with byte-oriented operations, and it is based on the use of a random permutation. According to some analyses, the period of the cipher is likely to be greater than 10,100. Each output byte uses 8 to 16 system operations; thus, the cipher can run fast when used in software. RC4 enables safe communications such as for traffic encryption (which secures websites) and for websites that use the SSL protocol.

- **RC5** <br>
  RC5 is a fast and flexible symmetric-key block cipher created by Ronald Rivest for RSA Security. It allows variable block sizes (32, 64, or 128 bits), key sizes (up to 2,040 bits), and rounds (0–255), making it adaptable for different security needs. The algorithm works through three main routines: key expansion, encryption, and decryption. In key expansion, the secret key is extended to fill a key table used in both encryption and decryption. RC5’s encryption relies on three operations—integer addition, bitwise XOR, and data-dependent rotation—which together provide strong security while keeping the algorithm efficient.

  <p align="center">
    <img width="185" height="342" alt="image" src="https://github.com/user-attachments/assets/fdcf37ef-51dc-4327-a4bb-bff45624e69b" />
  </p>

- **RC6** <br>
  RC6 is a symmetric-key block cipher derived from RC5. It is a parameterized algorithm with a variable block size, key size, and number of rounds. Two features that differentiate RC6 from RC5 are integer multiplication (which is used to increase the diffusion, achieved in fewer rounds with increased speed of the cipher) and the use of four 4-bit working registers rather than two 2-bit registers. RC6 uses four 4-bit registers instead of two 2-bit registers because the block size of the AES is 128 bits.

### Blowfish 
Blowfish is a fast and secure symmetric block cipher used to replace older algorithms like DES. It encrypts data in 64-bit blocks using the same secret key for both encryption and decryption, with key sizes ranging from 32 to 448 bits. It’s a 16-round Feistel cipher that offers strong security and high performance, making it suitable for applications like password protection and online payment systems. The algorithm has two main parts: key expansion, which generates multiple subkeys from the main key using a P-array and S-boxes, and the encryption process that uses these subkeys to securely transform the data.

Key expansion is performed as follows: 
1. The first step is to initialize the P-array and S-boxes.
2. Then, XOR the P-array with the key bits. For example, P1 XOR (first 32 bits of the key), P2 XOR (next 32 bits of the key).
3. Use the above method to encrypt the all-zero string.
4. This new output is now P1 and P2.
5. Encrypt the new P1 and P2 with the modified subkeys.
6. This new output is now P3 and P4.
7. Repeat the process 521 times to calculate new subkeys for the P-array and the four S-boxes.

The round function splits the 32-bit input into four 8-bit quarters and uses the quarters as input to the S-boxes. The outputs are added modulo 2^32 and XORed to produce the final 32-bit output.

### Twofish
Twofish is a fast and flexible encryption algorithm developed by Bruce Schneier and his team as one of the finalists to replace DES. It’s a 128-bit block cipher that uses a single key (up to 256 bits) for both encryption and decryption. Based on the Feistel structure, Twofish is known for its efficiency on both hardware and software, making it suitable for various applications. Its design allows users to balance speed, memory, and hardware use, providing strong security with adaptable performance.

### Threefish 
Threefish was developed in 2008 and it is a part of the Skein algorithm. It was enrolled in NIST’s SHA-3 (hash function) contest. It is a large tweakable symmetric-key block cipher in which the block and key sizes are equal, i.e., 256, 512, and 1024. Threefish involves only three operations, i.e., ARX (addition-rotation-XOR), which makes the coding simple, and all these operations work on 64-bit words. Threefish blocks 256, 512, and 1024 involve 72, 72, and 80 rounds of computations, respectively, to achieve the final security goal. This algorithm does not use S-boxes to prevent cache timing attacks.

### Serpent 
Serpent is a symmetric-key block cipher developed by Ross Anderson, Eli Biham, and Lars Knudsen. It uses 128-bit data blocks and supports key sizes of 128, 192, or 256 bits. The algorithm performs 32 rounds of substitution and permutation operations using S-boxes that work in parallel, making it highly secure. However, Serpent is slower than Rijndael (the AES winner) due to its large number of rounds and complexity. Despite its slower speed, Serpent provides strong security and minimizes correlations between plaintext and ciphertext more effectively than Twofish or Rijndael.

### TEA 
The Tiny Encryption Algorithm (TEA) is a simple and fast symmetric encryption method developed in 1994 by David Wheeler and Roger Needham. It works as a Feistel cipher, usually running 64 rounds, and encrypts 64-bit data blocks using a 128-bit key. The key is divided into four 32-bit parts, and a special constant called *delta*—derived from the golden ratio—is used in each round to ensure variation. Instead of only using XOR operations like many ciphers, TEA also relies on modular addition and subtraction. In each round, the data block is split into two halves; one half is processed through a round function involving shifts, additions, and delta, then mixed with the other half through XOR before swapping for the next round. This process provides strong encryption with a compact and efficient design.

### CAST-128 
CAST-128, also known as CAST5, is a symmetric block cipher that encrypts data in 64-bit blocks using keys between 40 and 128 bits. It works through 12 or 16 Feistel rounds that combine operations like addition, subtraction, XOR, and key-dependent rotations. The cipher uses four large S-boxes and two types of keys — a masking key and a rotation key — to control encryption steps. CAST-128 is used in tools like GPG and PGP for secure communication. Its extended version, CAST-256, supports larger 128-bit blocks and keys up to 256 bits, offering stronger security.

<p align="center">
  <img width="396" height="266" alt="image" src="https://github.com/user-attachments/assets/ff7d3ab5-4904-404b-8bfe-5d84fd4379a5" />
</p>

### GOST Block Cipher 
The GOST block cipher, also known as Magma, is a Russian symmetric encryption algorithm that uses a 64-bit data block and a 256-bit key. It operates through 32 rounds of a Feistel network, where data is mixed and transformed for strong security. Each round adds a 32-bit subkey (from the main key) using modular addition, passes the result through substitution boxes (S-boxes), and rotates bits left by 11 positions. The 256-bit key is divided into eight 32-bit subkeys—used in sequence for the first 24 rounds and in reverse for the last 8 rounds. A modern version of GOST, called **Kuznyechik**, enhances it by using 128-bit data blocks for improved security.

### Camellia 
Camellia is a strong symmetric block cipher used for secure data encryption. It works on 128-bit data blocks and supports key sizes of 128, 192, or 256 bits. Like AES, it provides high performance and strong security. Camellia uses multiple rounds of Feistel structure, S-box substitutions, logical transformations, and key whitening to protect data from attacks. It’s also part of the TLS protocol, making it widely used for secure internet communication. Despite using 128-bit keys, it remains resistant to brute-force attacks and is considered as secure as AES.

---
## Asymmetric Encryption Algorithms 
The table below shows specified asymmetric encryption algorithms, including information such as key size and application areas.

| Algorithm | Key Size (bits) | Application Areas |
| :--- | :--- | :--- |
| **Rivest–Shamir–Adleman (RSA)** | Variable | Encryption, digital signatures, key exchange |
| **Digital Signature Algorithm (DSA)** | Variable | Digital signatures |
| **Diffie-Hellman** | Variable | Key exchange, secure communication |
| **Elliptic Curve Cryptography (ECC)** | 160–521 bits | Encryption, digital signatures, key exchange |
| **ElGamal** | Variable | Encryption, key exchange |

### DSA and Related Signature Schemes 
The Digital Signature Algorithm (DSA) is a standard method developed by NIST to create and verify digital signatures, ensuring message authenticity and data integrity. It’s part of the Digital Signature Standard (DSS) under FIPS 186. DSA uses mathematical rules and specific parameters to confirm that a message truly comes from the claimed sender and hasn’t been altered. It typically generates a 320-bit signature and supports key sizes from 512 to 1024 bits, making it suitable for secure and sensitive communications.

**Processes involved in DSA:**
- **Signature Generation Process:** The private key is used to know who has signed it.
- **Signature Verification Process:** The public key is used to verify whether the given digital signature is genuine.

DSA is a public-key cryptosystem, as it involves the use of both private and public keys. <br>

**Benefits of DSA:**
- Less chances of forgery compared with a written signature
- Quick and easy method of business transactions
- Fake currency problem can be mitigated considerably 

DSA Algorithm: Each entity A does the following: 
1. Select a prime number q such that 2159 < q < 2160
2. Choose t such that 0 ≤ t ≤ 8, and select a prime number p where 2511+64t<p< 2512+64t with the property that q divides (p-1)
3. Select a generator α of the unique cyclic group of order q in Z*p g  Z*p and then computing α = g(p−1)/q mod p until α ≠1
4. Select a random integer d such that 1 ≤ d ≤ q-1 5. Compute y = αd mod p 6. A’s public key is (p, q, α, y); A’s private key is d.

To sign a message m, A does the following: 
1. Select a random secret integer k, 0<k<q.
2. Compute r=(αk mod p)mod q
3. Compute k-1mod q
4. Compute s=k-1{h(m) + dr}mod q, where h is the Secure Hash Algorithm
5. A’s signature for m is the pair (r, s)

To verify A’s signature (r, s) on m, B should do the following: 
1. Obtain A’s authentic public key (p,q,α,y)
2. Verify that 0<r<q and 0<s<q; if not, then reject the signature
3. Compute w = s-1mod q and h(m)
4. Compute u1 = w*h(m) mod q and u2 = rw mod q
5. Compute v = (αu1yu2 mod p) mod q
6. Accept the signature if and only if v=r

### Rivest Shamir Adleman (RSA) 
RSA (Rivest–Shamir–Adleman) is a public-key encryption system developed by Ron Rivest, Adi Shamir, and Leonard Adleman. It secures data on the internet by using two large prime numbers and modular arithmetic to create a pair of keys — one public and one private. RSA is widely used for encryption and authentication in systems from companies like Microsoft, Apple, and Sun, as well as in hardware such as smart cards and secure communication devices. It remains one of the most trusted and standard methods for protecting digital information.

**RSA works as follows:**
1. Two large prime numbers are taken (a and b), and their product is determined (c = ab, where “c” is called the modulus).
2. RSA chooses a number “e” that it is less than “c” and relatively prime to (a-1)(b-1). Therefore, e and (a-1)(b-1) have no common factor except 1.
3. Furthermore, RSA chooses a number “f” such that (ef - 1) is divisible by (a-1)(b-1).
4. The values “e” and “f” are the public and private exponents, respectively.
5. The public key is the pair (c, e); the private key is the pair (c, f).
6. It is difficult to obtain the private key (c, f) from the public key (c, e). However, if someone can factor “c” into “a” and “b”, then that person can decipher the private key (c, f).

The security of the RSA system depends on the assumption that such factoring is difficult to carry out, making the cryptographic technique safe. 

> **How RSA works (in easy words):**
>
> Imagine you want to send secret messages that only you can read. RSA helps you do that using two special keys — one is **public** (you can share it with anyone), and the other is **private** (you keep it secret).
>
> 1. **Start with two secret numbers:** <br>
>     You choose two very large secret prime numbers (let’s call them **a** and **b**). A prime number is a number that can only be divided by 1 and itself (like 3, 5, 7, 11, etc.).
>
> 2. **Multiply them together:** <br>
>    You multiply these two prime numbers to get a new big number called **c**. This number **c** will be shared with everyone. But the two original numbers (**a** and **b**) must always be kept secret.
>
> 3. **Pick a small public number (e):** <br>
>    Now you choose another number called **e**, which works well with your secret numbers. This number **e** becomes part of your public key — it’s the one everyone can see and use to lock (encrypt) a message for you.
>
> 4. **Find your private number (f):** <br>
>   Next, you calculate another special number **f** using **a**, **b**, and **e**. This number is chosen in a way that only you (the owner) can use it to unlock (decrypt) messages that were locked using your public key. **f** is your private key and must never be shared.
>
> 5. **Create your keys:**
>
>    * **Public key:** (c, e) — anyone can use this to send you a secret message.
>    * **Private key:** (c, f) — you use this to read the message.
>
> 6. **How messages are locked and unlocked:**
>
>   * To **encrypt**, someone takes your public key and scrambles the message using it.
>   * To **decrypt**, you use your private key to unscramble it and read the original message.
>
> 7. **Why it’s safe:** <br>
>    The only way to figure out your private key is to break the big number **c** back into your two secret primes (**a** and **b**). For small numbers, that’s easy. But when **a** and **b** are extremely large (hundreds or thousands of digits), even the fastest computers in the world would take thousands of years to figure them out. That’s why RSA is secure.
>
>
> **Simple example (with small numbers):** <br>
> Let’s say you pick **a = 5** and **b = 11**, so **c = 55**. <br>
> You share 55 with everyone. <br>
> Then you choose a small public number **e = 3** and calculate your private number **f = 27** (that part is normally done by computer).
>
> * Public key = (55, 3) <br>
> * Private key = (55, 27) <br>
>
> Someone can send you a message using **(55, 3)** to lock it. <br>
> Only you can open it using **(55, 27)**. <br>
>
> So in short: <br>
> RSA is all about **making two special keys** from **two large secret primes**. <br>
>
> * One key **locks** (encrypts) messages. <br>
> * The other key **unlocks** (decrypts) them. <br>
> And it’s safe because **finding the secret key requires solving an almost impossible math problem.** <br>

#### An example of how cryptography uses RSA algorithms in a practical interchange is illustrated by the following sequence: 
1. The sender of a message encrypts it using a randomly chosen DES symmetric key. DES (Data Encryption Standard) is a relatively insecure symmetric-key system using 64-bit encryption (56 bits for key size, 8 bits for cyclic redundancy check) to encrypt data.
2. The sender will then look up the recipient’s public key and use it to encrypt the DES key using the RSA system.
3. The sender transmits an RSA digital envelope, consisting of a DES-encrypted message and an RSA-encrypted DES key, to the recipient.
4. The recipient will decrypt the DES key and then use the DES key to decrypt the message itself.

This system combines the high speed of DES with the key management convenience of the RSA system.

#### RSA Signature Scheme 
The RSA Signature Scheme is a cryptographic method used to verify the authenticity and integrity of a message. It uses two keys — a public key and a private key. The sender signs the message using their private key, creating a unique digital signature. When the receiver gets the message and the signature, they use the sender’s public key to verify it. If the verification succeeds, it proves that the message truly came from the sender and wasn’t changed. For example, John signs his document using his private key, and Alice confirms its authenticity with John’s public key.

#### RSA Key Generation 
RSA Key Generation The procedure for RSA key generation is common to all the RSA-based signature schemes. To generate an RSA key pair, i.e., both an RSA public key and the corresponding private key, each entity A should do the following:
- Generate two large distinct primes p and q arbitrarily, each with roughly the same bit length
- Compute n = pq and  = (p-1)(q-1)
- Choose a random integer e, 1 < e <such that gcd(e, ) =  GCD = Greatest Common Divisor
- Use the extended Euclidean algorithm to compute the unique integer d, 1 < d < such that ed ≡ 1 (mod)
- A’s public key is (n, e); A’s private key is d

Destroy p and q at the end of the key generation.

#### The RSA algorithm generates and verifies the RSA signature as follows way:
Entity A signs a message mM. Any entity B can verify A’s signature and recover the message m from the signature. 
1. **Signature Generation** <br>
   To sign a message m, entity A should do the following:
   - Compute m̃ = R(m), an integer in the range [0, n–1]
   - Compute s = m̃ d mod n
   - A’s signature form is s

2. **Signature Verification** <br>
  To verify A’s signature s and recover the message m, B should do the following:
  - Obtain A’s authentic public key (n, e)
  - Compute m̃ = se mod n
  - Verify that m̃ MR; if not, reject the signature
  - Recover m = R-1(m̃)

#### Example of RSA Algorithm 
The math underlying RSA public-key encryption is described below: 
1. Find P and Q, two large (e.g., 1024-bit) prime numbers.
2. Choose E such that E is greater than 1, E is less than PQ, and E and (P-1)(Q-1) are relatively prime, which means that they have no prime factors in common. E does not have to be prime, but it must be odd. (P-1)(Q-1) cannot be prime because it is an even number.
3. Compute D such that (DE - 1) is evenly divisible by (P-1)(Q-1). Mathematicians write this as DE = 1 (mod (P-1)(Q-1)), and they call D the multiplicative inverse of E. This is easy to do—simply find an integer X that causes D = (X(P-1)(Q-1) + 1)/E to be an integer and then use that value of D.
4. The encryption function is C = (T^E) mod PQ, where C is the ciphertext (a positive integer), T is the plaintext (a positive integer), and ^ indicates exponentiation. During the encryption of the message, T must be less than the modulus, PQ.
5. The decryption function is T = (C^D) mod PQ, where C is the ciphertext (a positive integer), T is the plaintext (a positive integer), and ^ indicates exponentiation.

Your public key is the pair (PQ, E). Your private key is the number D (do not reveal it to anyone). The product PQ is the modulus. E is the public exponent. D is the secret exponent.

You can publish your public key freely because there are no known easy methods of calculating D, P, or Q given only (PQ, E) (your public key). 

Given below is an example of the RSA algorithm: <br>
P = 61<= first prime number (destroy this after computing E and D) <br>
Q = 53<= second prime number (destroy this after computing E and D) <br>
PQ = 3233<= modulus (give this to others) <br>
E = 17<= public exponent (give this to others) <br>
D = 2753<= private exponent (keep this secret) <br>
Your public key is (E,PQ) <br>
Your private key is D <br>
**The encryption function is:** <br>
```
encrypt(T) = (T^E) mod PQ = (T^17) mod 3233
```
**The decryption function is:** <br>
```
decrypt(C) = (C^D) mod PQ = (C^2753) mod 3233
```
**To encrypt the plaintext value 123, do this:** <br>
```
encrypt(123) = (123^17) mod 3233 
= 337587917446653715596592958817679803 mod 3233 
= 855
```
**To decrypt the ciphertext value 855, do this:** <br>
```
decrypt(855) = (855*2753) mod 3233 = 123
```
One way to compute the value of `855^2753 mod 3233` is as follows <br>
Consider these powers of 855:
- 855^1 = 855 (mod 3233)
- 855^2 = 367 (mod 3233)
- 855^4 = 367^2 (mod 3233) = 2136 (mod 3233)
- 855^8 = 2136^2 (mod 3233) = 733 (mod 3233)
- 855^16 = 733^2 (mod 3233) = 611 (mod 3233)
- 855^32 = 611^2 (mod 3233) = 1526 (mod 3233)
- 855^64 = 1526^2 (mod 3233) = 916 (mod 3233)
- 855^128 = 916^2 (mod 3233) = 1709 (mod 3233)
- 855^256 = 1709^2 (mod 3233) = 1282 (mod 3233)
- 855^512 = 1282^2 (mod 3233) = 1160 (mod 3233)
- 855^1024 = 1160^2 (mod 3233) = 672 (mod 3233)
- 855^2048 = 672^2 (mod 3233) = 2197 (mod 3233) 

Given the above, we know the following: 
```
855^2753 (mod 3233) 
= 855^(1 + 64 + 128 + 512 + 2048) (mod 3233) 
= 855^1 * 855^64 * 855^128 * 855^512 * 855^2048 (mod 3233) 
= 855 * 916 * 1709 * 1160 * 2197 (mod 3233) 
= 794 * 1709 * 1160 * 2197 (mod 3233) 
= 2319 * 1160 * 2197 (mod 3233)
= 184 * 2197 (mod 3233) 
= 123 (mod 3233) 
= 123 
```

### Diffie–Hellman
It is a cryptographic protocol that allows two parties to establish a shared key over an insecure channel. It was developed and published by Whitfield Diffie and Martin Hellman in 1976. Actually, it was independently developed a few years earlier by Malcolm J. Williamson of the British Intelligence Service, but it was classified at that time. 

**Diffie–Hellman Algorithm** <br>
The system has two parameters called p and g
- Parameter p is a prime number
- Parameter g (usually called a generator) is an integer less than p, with the following property: for every number n between 1 and p-1 (both inclusive), there is a power k of g such that `n = g kmod p`

Many cryptography textbooks use the fictitious characters “Alice” and “Bob” to illustrate cryptography; we will do the same here as well:
- Alice generates a random private value a, and Bob generates a random private value b. Both a and b are drawn from the set of integers
- They derive their public values using parameters p and g and their private values. Alice's public value is ga mod p, and Bob's public value is gb mod p.
- They exchange their public values
- Alice computes gab = (gb)a mod p, and Bob computes gba = (ga)b mod p
- Since gab = g<sup>ba</sup> = k, Alice and Bob now have a shared secret key k

The Diffie–Hellman algorithm does not provide any authentication for the key exchange and is vulnerable to many cryptographic attacks. Nevertheless, it is the basis of many authentication mechanisms; for example, it provides forward secrecy in the TLS protocol’s ephemeral modes depending on the cipher spec.

### Elliptic Curve Cryptography (ECC) 
Elliptic Curve Cryptography (ECC) is a modern form of public-key cryptography that provides strong security using smaller keys. Unlike RSA, which needs large key sizes for protection, ECC uses mathematical elliptic curves to create secure and efficient encryption. This makes ECC faster, lighter, and more suitable for modern systems like mobile devices and IoT, while still offering the same or even better security than RSA.

The operational key sizes of both algorithms to achieve similar goals are listed below: 

| ECC Key size | RSA Key Size |
| :---: | :---: |
| 160-223 | 1024 |
| 224-255 | 2048 |
| 256-383 | 3072 |
| 384-511 | 7680 |
| 512+ | 15360 |

While RSA uses a key size of 1024 to encrypt the data, ECC provides equal security with a comparatively smaller key size ranging between 160 to 223. For high-level computing, RSA uses a key size of 7680 to implement security, whereas ECC can provide the same level of security with a key size ranging between 384 to 511.


### YAK
YAK is a public-key-based Authenticated Key Exchange (AKE) protocol. The authentication of YAK is based on public key pairs, and it needs PKI to distribute authentic public keys. YAK is a variant of the two-pass Hashed Menezes‐Qu‐Vanstone (HMQV) protocol using zero‐knowledge proofs (ZKP) for proving the knowledge of ephemeral secret keys from both parties. The YAK protocol lacks joint key control and perfect forward secrecy attributes. 

The YAK protocol implementation between two parties Alice and Bob is described as follows: 
1. Alice chooses a random number x such that x∈ R[0, q − 1], computes X = gx, and generates ZKP of x, denoted by KP{x}. Alice sends X and KP{x} to Bob.
2. Bob chooses a random number y such that y∈ R[0, q − 1], computes Y = gy, and generates ZKP of y, denoted by KP{y}. Bob sends Y and KP{y} to Alice.
3. Alice verifies the received KP{x} and computes the session key after verification as k = H ((Y.PKB)x + a), where H is a hash function.
4. Bob verifies the received KP{y} and computes the session key after verification as k = H ((X.PKA)y + b).
5. They authenticate each other, and both obtain the same session key k = H (g(x + a)(y + b)).

The YAK protocol can accomplish the following objectives: 
- Private key security
- Full forward secrecy
- Session key security

---
## Message Digest (One-way Hash) Functions 
Message Digest or One-way Hash Functions convert any size of data into a fixed-length string called a hash or digest. Even a tiny change in the input completely changes the output. These functions are one-way, meaning it’s nearly impossible to reverse or find two different files with the same hash. Though they don’t perform encryption or decryption, they are essential for verifying data integrity, creating digital signatures, and generating encryption keys from passwords. In short, hash functions ensure that data hasn’t been altered and are a fast, secure way to confirm authenticity in digital systems.

Widely used message digest functions include the following algorithms:
- MD5
- SHA
Note: Message digests are also called one-way hash functions because they cannot be reversed.

<p align="center">
  <img width="623" height="103" alt="image" src="https://github.com/user-attachments/assets/4598bb7b-80a4-4db4-98ec-42b4391a3e68" />
</p>

---
## Message Digest Functions 
The table below shows message digest functions, detailing their output size, internal state size, block size, maximum message size, rounds, operations, security level, and application areas:

| Algorithm   | Output Size (bits)           | Internal State Size (bits) | Block Size (bits) | Max Message Size (bits) | Rounds     | Operations                             | Security (bits) | Application Areas                                               |
|--------------|------------------------------|-----------------------------|-------------------|--------------------------|-------------|----------------------------------------|-----------------|------------------------------------------------------------------|
| **MD2**      | 128                          | 128                         | 128               | 2^64                     | 18          | Permutation, Substitution              | 128             | Legacy applications, checksum validation                       |
| **MD4**      | 128                          | 128                         | 512               | 2^64                     | 48          | Logical operations (AND, OR, XOR)      | 64              | Obsolete, early cryptographic hash functions                   |
| **MD5**      | 128                          | 128                         | 512               | 2^64                     | 64          | Logical operations (AND, OR, XOR)      | 64              | File verification, checksum, digital signatures                |
| **MD6**      | 224, 256, 384, 512           | 1024                        | 512               | Unlimited                | Variable    | Logical operations (AND, OR, XOR)      | 128–256         | Cryptographic applications, data integrity                     |
| **SHA-0**    | 160                          | 160                         | 512               | 2^64                     | 80          | Bitwise logical operations             | 0               | Obsolete, replaced by SHA-1                                    |
| **SHA-1**    | 160                          | 160                         | 512               | 2^64                     | 80          | Bitwise logical operations             | 80              | Legacy systems, software updates, TLS                          |
| **SHA-2**    | 224, 256, 384, 512           | 256, 512                    | 512, 1024         | 2^128                    | 64, 80      | Logical operations (AND, OR, XOR)      | 112–256         | Secure applications, digital signatures, SSL                   |
| **SHA-3**    | 224, 256, 384, 512           | 1600                        | 1088, 576         | Unlimited                | Variable    | Sponge construction                    | 112–256         | Secure applications, next-generation cryptographic functions   |
| **RIPEMD-160** | 160                        | 160                         | 512               | 2^64                     | 160         | Logical operations (AND, OR, XOR)      | 80              | Cryptographic applications, data integrity                     |
| **WHIRLPOOL** | 512                         | 512                         | 512               | 2^256                    | 10          | Matrix operations, substitution        | 256             | Secure hashing, cryptographic applications                     |
| **Tiger**    | 192                          | 192                         | 512               | Unlimited                | 24          | Logical operations (AND, OR, XOR)      | 192             | High-speed applications, checksum validation                   |
| **BLAKE2**   | 256, 512                     | 256, 512                    | 512, 1024         | Unlimited                | 10–14       | Logical operations (AND, OR, XOR)      | 128–256         | High-speed hashing, secure applications                        |
| **BLAKE3**   | 256                          | 256                         | 512               | Unlimited                | Variable    | Logical operations (AND, OR, XOR)      | 128             | High-performance cryptographic applications                    |

### Message Digest Function: MD5 and MD6
Message Digest algorithms like MD2, MD4, MD5, and MD6 are used to create a fixed-size digital fingerprint (128-bit) of any message, mainly for digital signatures and data integrity checks. MD2 was designed for older 8-bit systems, while MD4 and MD5 were made for 32-bit systems with similar structures. However, MD4 is now easily breakable, and MD5—though still used—is also vulnerable to collision attacks, meaning two different messages can produce the same hash. MD6, the improved version, uses a Merkle-tree structure that allows faster and more secure hashing, even for large data, and offers better resistance to modern attacks. In short, MD6 and newer algorithms like SHA-2 or SHA-3 are preferred for secure applications today.

The following are examples of minimally different message digests:
```bash
echo “There is CHF1500 in the blue bo” | md5sum
e41a323bdf20eadafd3f0e4f72055d36
```  
```bash
echo “There is CHF1500 in the blue box” | md5sum
7a0da864a41fd0200ae0ae97afd3279d
```
```bash
echo “There is CHF1500 in the blue box.” | md5sum
2db1ff7a70245309e9f2165c6c34999d
```
Even minimally different texts produce radically different MD5 codes.

<p align="center">
  <img width="632" height="185" alt="image" src="https://github.com/user-attachments/assets/8fefe86b-2b27-4db0-b095-5835031dd4c8" />
</p>

- **QuickHash-GUI** [https://www.quickhash-gui.org] <br>
  QuickHash-GUI is a graphical interface data hashing tool for Linux, Windows, and macOS. The tool is capable of hashing segments of text or dynamic hashing as you type into the text field.

### Message Digest Function: Secure Hashing Algorithm (SHA) 
The Secure Hash Algorithm (SHA) is a cryptographic hash function developed by NIST and published as FIPS PUB 180. It converts any input data into a fixed-size, unique hash value that cannot be reversed. SHA works like a digital fingerprint for data, ensuring integrity and security. It’s slower than MD5 but offers stronger protection against collision and brute-force attacks, making it more reliable for modern cybersecurity use.

SHA encryption is a series of five different cryptographic functions, and it currently has three generations: SHA-1, SHA-2, and SHA-3. 
- **SHA-0:** A retronym applied to the original version of the 160-bit hash function published in 1993 under the name SHA, which was withdrawn from trade due to an undisclosed “**significant flaw**” in it. It was replaced with a slightly revised version, namely SHA-1.

- **SHA-1:** It is a 160-bit hash function that resembles the former MD5 algorithm developed by Ron Rivest. It produces a 160-bit digest from a message with a maximum length of (264 − 1) bits. It was designed by the National Security Agency (NSA) to be part of the Digital Signature Algorithm (DSA). It is most commonly used in security protocols such as PGP, TLS, SSH, and SSL. As of 2010, SHA-1 is no longer approved for cryptographic use because of its cryptographic weaknesses.

- **SHA-2:** SHA2 is a family of two similar hash functions with different block sizes, namely SHA-256, which uses 32-bit words, and SHA-512, which uses 64-bit words. The truncated versions of each standard are SHA-224 and SHA-384.

- **SHA-3:** SHA-3 uses sponge construction in which message blocks are XORed into the initial bits of the state, which the algorithm then invertibly permutes. It supports the same hash lengths as SHA-2 but differs in its internal structure considerably from the rest of the SHA family.

### RIPEMD-160
RIPEMD-160 (RACE Integrity Primitives Evaluation Message Digest) is a 160-bit cryptographic hash function created by Hans Dobbertin, Antoon Bosselaers, and Bart Preneel. It was designed as a stronger version of the original RIPEMD, which had security flaws. The algorithm uses a complex compression function with 80 steps (five blocks executed 16 times each) that run twice and combine results using modulo 32 addition. RIPEMD-160 is considered secure and is mainly used for data integrity and digital signatures, though it isn’t based on any formal security standard.

### HMAC 
HMAC (Hash-based Message Authentication Code) is a security method used to verify both the integrity and authenticity of data. It combines a secret key with a cryptographic hash function, such as SHA-1 or MD5, to generate a unique code for each message. The process runs in two stages — first mixing the key and message to create an internal hash, and then hashing that result again with another key. Because it applies the hash function twice, HMAC is resistant to length extension attacks. Its security mainly depends on the strength of the hash function and the size of the secret key.

### GOST – Hash Function 
This hash algorithm was initially defined in the Russian national standard GOST R 34.11-94 “Information Technology - Cryptographic Information Security - Hash Function.” 

It produces a fixed-length output of 256 bits. The input message is broken up into chunks of 256-bit blocks. If a block is less than 256 bits, then the message is padded by appending as many zeros to it as are required to make the length of the message 256 bits. The remaining bits are filled with a 256-bit integer arithmetic sum of all previously hashed blocks. Then, a 256-bit integer representing the length of the original message, in bits, is produced.

---
## Message Digest Functions Calculators 
Message digest functions calculators that use different hash algorithms to convert plaintext into its equivalent hash value are discussed below.
- **MD5 Calculator** [https://www.bullzip.com] <br>
  MD5 Calculator is a tool used to generate the MD5 hash of a file to verify its integrity. It works by creating a unique digital fingerprint for any file, even large ones. After selecting a file, the tool shows its MD5 value, which you can copy or compare with another hash to confirm if the file has been modified or remains authentic.

  <p align="center">
    <img width="556" height="391" alt="image" src="https://github.com/user-attachments/assets/6bc35c8b-973e-47e9-bf2f-244aabee5c40" />
  </p>

- **HashMyFiles** [https://www.nirsoft.net] <br>
  HashMyFiles is a simple Windows tool used to generate MD5 and SHA1 hashes for files. These hashes help verify file integrity or detect tampering. You can easily access it from the Windows Explorer right-click menu to view, copy, or save the hash values in different formats for analysis or documentation.

  <p align="center">
    <img width="576" height="402" alt="image" src="https://github.com/user-attachments/assets/96dd053c-2464-4e3f-bc0b-df4d0dd74f4c" />
  </p>

Some additional MD5 and MD6 hash calculators are as follows:
- **MD6 Hash Generator** [https://www.browserling.com]
- **All Hash Generator** [https://www.browserling.com]
- **md5 hash calculator** [https://onlinehashtools.com]
- **Message Digester** [https://www.freeformatter.com]
- **MD6 Hash Generator** [https://www.atatus.com]

---
## Multilayer Hashing Calculators
Multilayer hashing, also known as nested hashing or recursive hashing, is a technique in which a hash function is applied multiple times to the input or output of a previous hash operation. This approach can enhance the security and create more complex hash structures. Tools such as CyberChef can be used to perform multilayer hashing. This multilayer hashing process can make it more difficult for attackers to reverse engineer the original input data from the hash value, as it adds an additional layer of complexity, which makes brute-force attacks more challenging.

### Working of Multilayer Hashing
- **Initial Hashing:** The original input data (e.g., a message or file) are hashed using a cryptographic hash function such as SHA-256, SHA-3, or MD5. The result is a fixed-size hash value that is typically a string of characters.
- **Subsequent Hashing:** The hash value obtained from the initial hashing step is again hashed using the same or different hash functions. This process can be repeated several times to create multiple hashing layers.
- **Final Hash Value:** After a predetermined number of hashing iterations, the final hash value is obtained. This value is used as the final output of the multilayer hashing process

### Steps to Perform Multilayer Hashing Using CyberChef
- **Step 1:** Create a sample file and open the CyberChef [https://gchq.github.io/CyberChef].
- **Step 2:** Click on the "Open file as input" option to upload the sample file.
- **Step 3:** Search for the desired hashing algorithm in the Operations panel (e.g., MD5), and drag and drop it into the Recipe panel. The output is shown in the Output panel.
- **Step 4:** Using the MD5 hash value as the input, select another hashing algorithm (e.g., SHA1) and drag and drop it into the Recipe panel.
- **Step 5:** Based on these requirements, select another hashing algorithm using the output of the SHA1 hash as the input and perform hashing recursively, as shown in the screenshot.

<p align="center">
  <img width="557" height="396" alt="image" src="https://github.com/user-attachments/assets/378535c5-6a4f-4dec-8c49-1a700a2585f5" />
</p>

---
## Hardware-Based Encryption 
Hardware-based encryption uses special computer hardware to handle the process of encrypting data instead of relying solely on software. By doing this, the encryption workload is shifted to dedicated hardware, freeing the system for other tasks. These devices securely store encryption keys in protected memory areas, making them tamper-resistant and preventing unauthorized code or software from running. Compared to software encryption, hardware encryption is faster, more secure, and resistant to attacks. Examples include wireless access points, Nitrokey devices, credit card terminals, and network bulk encryptors.

### Types of hardware encryption devices 
- **TPM** <br>
  Trusted Platform Module (TPM) is a crypto-processor or a chip that is present in the motherboard. It can securely store the encryption keys and perform many cryptographic operations. TPM offers various features such as authenticating platform integrity, providing full disk encryption capabilities, performing password storage, and providing software license protection.

- **HSM** <br>
  A hardware security module (HSM) is an additional external security device that is used in a system for crypto-processing, and it can be used for managing, generating, and securely storing cryptographic keys. HSM offers enhanced encryption computation that is useful for symmetric keys longer than 256 bits. High-performance HSM devices are connected to the network using TCP/IP. Some HSM devices include Thales Luna Network HSM, nSheild HSM, Utimaco HSM, and Cryptosec Dekaton PCI.

- **USB Encryption** <br>
  USB encryption is an additional feature for USB storage devices, which offers onboard encryption services. Encrypted USB devices need an on-device credential system or software-or hardware-based credentials from a computer. USB encryption provides protection against malware distribution over USB and helps in preventing data loss and data leakage. Some hardware USB-encrypted devices include Encrypted USB, Kingston Ironkey D300S, and diskAshur Pro.

- **Hard Drive Encryption** <br>
  Hard drive encryption is a technology whereby the data stored in the hardware can be encrypted using a wide range of encryption options. Hard drive encryption devices cannot use an on-device keyboard or fingerprint reader; instead, they need a TPM or an HSM. These devices can be installed as an internal drive on a computer. Some hard drive encryption devices include military-grade 256-bit AES Hardware Encryption and DiskCypher AES Sata Hard Drive Encryption.

---
## Quantum Cryptography 
Quantum cryptography is a modern way to secure data using the principles of quantum mechanics instead of traditional math-based encryption. Unlike normal cryptosystems that rely on binary digits (0s and 1s) and can be vulnerable to eavesdropping, quantum cryptography uses photons—tiny particles of light—that carry information. Each photon has a “spin” that changes as it passes through different filters, representing either a 0 or a 1. For example, vertical and backslash spins represent 1, while horizontal and forward slash spins represent 0. This method, known as quantum key distribution (QKD), ensures that any attempt to intercept or tamper with the data can be detected, making it highly secure against attacks like man-in-the-middle.

- Horizontal (–): 0
- Vertical (|): 1
- Backslash (/): 1
- Forward slash (\): 0

Attackers can eavesdrop on but cannot manipulate the data because the photons are transferred through arbitrary filters. To breach this mechanism, attackers must know the exact shape of the photons; if they fail to choose the right transmission, the photon polarization is distorted, and the receiver detects an error indicating the eavesdrop. 

---
## Other Encryption Techniques 

### Homomorphic Encryption 
Homomorphic encryption is a special type of encryption that allows data to stay encrypted even while it is being processed. Unlike regular encryption, where data must be decrypted before use, homomorphic encryption lets computations be done directly on the encrypted data. Only the key holder can decrypt the final result. This means sensitive information can be securely outsourced, for example, to cloud services, without exposing the data during processing. It ensures privacy while still enabling practical use of the data.

How homomorphic encryption differs from other encryption mechanisms: <br>
**In private key encryption:**
- Only keyholders can generate and decrypt ciphertexts using similar keys. <br>

**In public key encryption:**
- Only the public keyholder generates the ciphertext and the secret keyholder decrypts the ciphertext.

**In homomorphic encryption:** 
- The keyholder can generate the ciphertext and anyone can alter the ciphertext, but only the keyholder again can decrypt the data.

The reason for using this cryptography is that an untrusted entity can manipulate the data. Hence, this mechanism allows the sender himself/herself to encrypt and decrypt the data, allowing anyone to perform mathematical operations on the ciphertext with respect to the rules applied by the sender.

### Post-quantum Cryptography 
Post-quantum cryptography, also called quantum-resistant cryptography, is a type of encryption designed to stay secure even against attacks from quantum computers. Unlike traditional cryptography, which could be broken by powerful quantum algorithms, post-quantum cryptography uses advanced mathematical techniques to protect data, communications, and digital signatures. It can work with existing networks and protocols or act as a standalone system, ensuring secure online communication, secret-key management, and public-key encryption for sensitive activities like e-voting. Essentially, it’s a forward-looking solution to keep information safe in the era of quantum computing.

### Lightweight Cryptography
Lightweight cryptography is designed for devices with limited power and computing ability, like IoT sensors or RFID tags. Unlike traditional cryptography, which works well on powerful servers or desktops, lightweight algorithms aim to provide strong security while using minimal resources and energy. Researchers are also focusing on making these algorithms quantum-safe, ensuring they remain secure against future quantum computers. The goal is simple: protect data efficiently on small, low-powered devices without compromising security.

---
## Cipher Modes of Operation
Cipher modes of operation are techniques that allow block ciphers to securely encrypt data in fixed-size blocks. They use a secret key, and sometimes an initialization vector, to ensure that even identical blocks of plaintext produce different ciphertexts. These modes help maintain data confidentiality and authenticity. In practice, the client and server securely exchange a symmetric key, which is then used to encrypt data on the source side and decrypt it on the destination side. Essentially, cipher modes define how encryption and decryption work together to protect information during transmission.

### Electronic Code Book (ECB) Mode 
Electronic Code Book (ECB) mode is a basic way to encrypt and decrypt data using a block cipher and a secret key. In ECB, the plaintext is split into fixed-size blocks, and each block is encrypted separately using the key. Decryption works the same way, reversing the process block by block. The main problem with ECB is that identical plaintext blocks produce identical ciphertext blocks, making patterns visible and potentially exposing sensitive information to attackers. This makes ECB less secure for most real-world applications.

<p align="center">
  <img width="352" height="274" alt="image" src="https://github.com/user-attachments/assets/3c2758e1-1dc5-4368-87be-5b44491f9305" />
</p>

### Cipher Block Chaining (CBC) Mode
Cipher Block Chaining (CBC) is a secure way to encrypt data that improves on the simpler ECB method. In CBC, the plaintext is split into blocks, and each block is combined with an initialization vector (IV) or the previous ciphertext block using XOR before encryption with a secret key. This “chaining” ensures that identical plaintext blocks produce different ciphertext, making patterns harder to detect. During decryption, each ciphertext block is decrypted with the key and then XORed with the IV or the previous ciphertext block to recover the original plaintext. A drawback is that an error in one ciphertext block affects the decryption of the next block, causing error propagation.

<p align="center">
  <img width="412" height="253" alt="image" src="https://github.com/user-attachments/assets/5883ab94-09d0-472f-aab9-f94a7e920341" />
</p>

### Cipher Feedback (CFB) Mode 
Cipher Feedback (CFB) mode is a way of encrypting data where each ciphertext block influences the next one, making it harder to break. It starts with an initialization vector (IV) that is encrypted, and part of that output is XORed with the first plaintext block to create the first ciphertext block. For the next block, the previous ciphertext is shifted and used in the same way. Decryption works similarly, using the ciphertext and encryption output to recover plaintext. This mode adds security by chaining blocks together and using feedback, which also means some data loss can occur due to the shifting process.

<p align="center">
  <img width="423" height="274" alt="image" src="https://github.com/user-attachments/assets/c5b60fee-4a08-4edf-91ee-43a6b375ce46" />
</p>

### Counter Mode
Counter Mode (CTR) is a block cipher mode that turns a block cipher into a stream cipher. It works by combining a plaintext block with the encrypted value of a counter using XOR. The counter changes for each block, ensuring unique encryption. On the receiving side, the same counter and key are used to decrypt by XORing the encrypted counter with the ciphertext. CTR mode avoids error propagation since it doesn’t rely on previous ciphertext, but both sender and receiver must keep their counters perfectly synchronized.

<p align="center">
  <img width="388" height="381" alt="image" src="https://github.com/user-attachments/assets/818f6a3b-b542-4c3f-b054-bc70e27dd838" />
</p>

---
## Modes of Authenticated Encryption 
Authenticated Encryption (AE) ensures that data is both private and secure from tampering. Unlike regular encryption, which only hides the message, AE combines encryption with a Message Authentication Code (MAC). This means that even if an attacker tries to alter the ciphertext, the system can detect it and reject the message. By doing this, AE prevents attacks like chosen-ciphertext attacks, ensuring that only the correct, untampered data can be decrypted using the shared secret key.

### Authenticated encryption with Message Authentication Code (MAC)
A MAC is a value obtained by hashing a plaintext message using a shared secret key. It provides integrity for the message, and the receiver can verify the message using the hash value attached to it. The following are the three different ways of using a MAC while encrypting a message. 
- **Encrypt-then-MAC (EtM)** <br>
  In this approach, the plaintext is first encrypted using a secret key. For the obtained ciphertext, a hash value called message authentication code (MAC) is generated. The MAC is attached to the ciphertext and transmitted. This approach provides higher security for the transmitted message than other AE approaches.

- **Encrypt-and-MAC (E&M)** <br>
  In the E&M approach, a MAC is first generated for the plaintext, following which the plaintext is encrypted using a secret key. Finally, both the ciphertext and MAC are combined and transmitted.

- **MAC-then-encrypt (MtE)** <br>
  In the MtE approach, a MAC is first generated for the plaintext using the hash function, and the MAC is combined with the plaintext. The combination of the plaintext and MAC is encrypted with a secret key to produce ciphertext. The ciphertext contains the encrypted MAC.

### Authenticated Encryption with Associated Data (AEAD)
AEAD is another approach used to ensure the integrity and authenticity of a message that contains both encrypted and unencrypted data. This approach adds additional data to the ciphertext at certain places to thwart chosen ciphertext attacks. The message header is kept unencrypted so that the receiver can verify the source of the message, and the payload is encrypted to ensure confidentiality.

---
## Cryptography Tools 
You can use various cryptographic tools for encrypting and decrypting your information, files, etc. These tools implement different types of encryption algorithms. 

- **BCTextEncoder** [https://www.jetico.com] <br>
  The BCTextEncoder utility simplifies the encoding and decoding of text data. It compresses, encrypts, and converts plaintext data into text format, which the user can then copy to the clipboard or save as a text file. It uses public key encryption methods as well as password-based encryption. Furthermore, it uses strong and approved symmetric and public-key algorithms for data encryption.

  <p align="center">
    <img width="592" height="420" alt="image" src="https://github.com/user-attachments/assets/6346f8d1-804e-4e4d-841f-9ced3dab49af" />
  </p>

Some additional cryptography tools are as follows:
- **CryptoForge** [https://www.cryptoforge.com]
- **AxCrypt** [https://axcrypt.net]
- **Microsoft Cryptography Tools** [https://www.microsoft.com]
- **Concealer** [https://www.belightsoft.com]
- **SensiGuard** [https://www.sensiguard.com]
- **Cypherix** [https://www.cypherix.com]
