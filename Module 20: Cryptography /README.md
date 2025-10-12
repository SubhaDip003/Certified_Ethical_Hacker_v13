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

