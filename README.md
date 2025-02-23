# **Post-Quantum Cryptography (PQC) Implementation**  

## **Overview**  
This project explores solutions for **secure data storage** by implementing **post-quantum cryptographic techniques**. It ensures **confidentiality, integrity, and authenticity** through a combination of modern encryption, digital signatures, and secure key sharing mechanisms.  

## **Key Features**  
✔ Secure **key sharing** using **Kyber-KEM**  
✔ **AES-GCM encryption** for data confidentiality & authenticity  
✔ **SPHINCS+ digital signatures** for data integrity verification  
✔ **Encrypted file backups** stored securely on Google Drive  
✔ **User-based encryption** with separate keys for different users  

## **Cryptographic Methods Used**  

| Feature                | Algorithm Used   |
|------------------------|-----------------|
| **Key Management**      | Kyber-KEM       |
| **Data Encryption**     | AES (GCM Mode)  |
| **Digital Signature**   | SPHINCS+        |
| **Backup Storage**      | Google Drive    |

AES in **GCM mode** ensures **both encryption and authentication**, while **SPHINCS+ digital signatures** guarantee data integrity and prevent tampering.  

## **Installation & Dependencies**  
Before running the program, install the required dependencies:  

```bash
pip install kyber-py
pip install pyspx
pip install pycryptodomex==3.18.0
```

## **Usage**  

### **1. Key Sharing (Kyber-KEM)**
- Uses **Kyber512** to securely share encryption keys between two users.
- Each user generates a **public-private key pair**, exchanges public keys, and derives the same **shared key**.

### **2. File Encryption (AES-GCM)**
- Users can encrypt files using **AES-GCM** and a **unique key**.
- The encrypted file includes a **digital signature (SPHINCS+)** for integrity verification.
- Encrypted files are stored securely in a backup folder.

### **3. File Decryption**
- The recipient verifies the **digital signature** before decryption.
- If the data is **tampered**, the decryption process **fails**.
- Successfully decrypted files are stored locally.

### **4. Secure Backup on Google Drive**
- Encrypted files are stored on Google Drive.
- Users can later retrieve and decrypt files using their unique keys.

## **How to Run**  
1. **Mount Google Drive (if needed)**
    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```

2. **Run the Main Program**
    ```bash
    python main.py
    ```

## **References**  
- [Kyber-Py (Post-Quantum Key Exchange)](https://pypi.org/project/kyber-py/)  
- [SPHINCS+ Digital Signatures](https://github.com/sphincs/pyspx)  

