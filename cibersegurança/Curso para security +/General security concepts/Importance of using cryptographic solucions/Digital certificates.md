- A public key certificate
	- binds a public key with a digital signature
	- And other details about the key holder
- A digital signature adds trust
	- PKI uses Certificate Authorities for additional trust
	- Web of Trust adds other users for additiona trust
- Certificate creation can be built into the OS
	- Part of windows domain services
	- 3rd-party options
- Certificate details
- X.509 standard format

## Root of trust
- Everything associated with IT security requires trust
- Refer to the root of trust
	- an inherently trusted component

## Certificate authorities
- Need a good way to trust an unknown entity
	- use trusted third-party
	- An authority
- Certificate authority (CA) has digitally signed the website certificate
	- trusted CA trusted website
	- realtime verification
- built-in to your browser
- Purchase your website certificate
- CA is responsible for vetting the request

## Certificate signing requests
- Create a key pair, then send the public key to the CA to be signed
	- A certificate signing request (CSR)
- The CA validates the request

## Private certificate authorities
- Internal certificates don't need to be signed by a public CA
- build your own CA
- Install the CA certificate/trusted chain on all devices

## wildcard certificates
- subject alternative name
- lists additional identification information
- Allows a certificate to support many different domains
- wildcard domain
	- help to create certificates for multiple services

## Key revocation
- Certificate Revocation List (CRL)
	- Maintained by CA
	- Can contain many revocations in a large file
- Many different reasons

## OSCP stapling
- Online certificate status protocol
- The certificate holder verify their own status
- OCSP status ir stapled into the ssl/tls handshake
	- Digitally signed by the CA
- not all browser supports

