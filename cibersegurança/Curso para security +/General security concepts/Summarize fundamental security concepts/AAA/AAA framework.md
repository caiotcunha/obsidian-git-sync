- identification
- Authentication
	- Prove you are who you say you are
- Authorization
	- What access do you have?
- Accounting
	- Resources used: Login time, data sent and received, logout time

## Authenticating systems
- use certificate on the device
- Other business processes rely on the certificate

## Certificate authentication
- An organization has a trusted Certificate Authority (CA)
- The organization creates a certificate for a device and digitally signs the certificate with the organization's CA
- The certificate can now be included on a device as an authentication factor
	- The CA's digital signature is used to validade the certificate

## Authorization models
- Apply an authorization model
- Put an authorization model in the middle
	- Defined by roles, organizations, attributes, etc
- Add an abstraction
- Administration is streamlined