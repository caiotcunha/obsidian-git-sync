- Protect data on storage devuces
- Full-disk and partition/volume encryption
	- Bitlocker,FileVault
- File encryption
	- EFS

## Database encryption
- Protecting stored data
- Transparent encryption

## Transport encryption
- Protect data in move
- Encrypting in the application
- VPN: creating an encrypting tunnel
	- ssl/tls

## Encryption algorithms
- There are many diffetent ways to encrypt data
- Both sides must use the same
- There are advantages and disadvantages between algoritms
- The cryptographic process algoritm is well know
- key lenghts
	- adquate key lenghts protect against brute force
	- large keys are more secure
- key stretching
	- make a key stronger by performing multiple processes

## Key exchange
- a logistical challenge
- out-of-band: transfer without using the network
- in-band key exchange
	- It's on the network
	- Protect the key with additional encryption
	- Use asymmetric encryption to deliver a symmetric key
- Real-time encryption/decryption
	- There's a need for fast security
	- implements session keys carefully
		- unpredictable
		- ephemeral
- Use public and private key cryptography to create a symmetric key
	- key exchange algoritms