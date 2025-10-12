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

  


