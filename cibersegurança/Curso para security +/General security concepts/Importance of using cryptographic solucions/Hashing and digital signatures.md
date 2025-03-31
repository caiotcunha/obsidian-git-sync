## hashes
- Represent data as a short string of text
- one-way trip
- not encryption
- verify a downloaded document is the same as the original
- Can be a digital signature
- sha256 hash for exemple
- hash functions take an input of any size and create a fixed size string
- the hash should be unique
	- if its not is collision
	- MD5 has collision
- password storage
	- use salt to randomize the hash
	- everyuse gets their own random salt
	- Rainbow tables won't work with salted hashes

## Digital signatures
- prove the message was not changed
	- integrity
- prove the source of the message authentication
	- authentication
- Make sure the signature isn't fake
	- Non-repudiation
- Sign with the private key
	- the message doesn't need to be encrypted
	- nobody else can sign this
- Verify with the public key
	- any change invalidates
- 