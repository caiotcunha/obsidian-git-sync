## Trusted Plataform module (TPM)
- A specification for cryptographic functions
	- cryptography hardware on a device
- Cryptographic processor
	- Random number generator, key generators
- Persistent memory
	- unique keys burned in during manufactorin
- Versatile memory
- Password protected

## Hardware Security Module (HSM)
- used in large environments
	- Clusters,redundant power
	- Securely store thousands of cryptographic keys
- High-end cryptographic hardware
	- Plug-in card or separate hardware device
- Key backup
	- Secure storage in hardware
- Cryptographic accelerators
	- Offload that CPU overhead from other devices

## Key management system
- Services are everywhere
	- on-premises, cloud-based
	- many different keys form many different services
- Manage all keys from a centralized manager
	- Often provided as a third-party software
	- Separate the encryption keys from the data
- All key management from one console
	- Create keys for a specific service or cloud provider
	- Associate keys with specific users
	- Rotate keys on regular intervals
	- Log key use and important events

## Keeping data private
- Our data is located in many different places
- Attackers are always finding new techniques
- Our data is changing constantly

## Secure enclave
- A protected area for our secrets
- provides extensive security features
	- has its own boot rom
	- monitors the system boot process
	- True random number generator
	- Real-time memory encryption
	- Root cryptographic keys