## Basics
./john --wordlist=(path to wordlist) (path to file)

Para formatos específicos
./john --format=(format) --wordlist=(path to wordlist) (path to file)

**A Note on Formats:**

When you tell John to use formats, if you’re dealing with a standard hash type, you have to prefix it with `raw-` to tell John you’re just dealing with a standard hash type, though this doesn’t always apply

## Cracking windows authentication hashes
NThash is the hash format modern Windows operating system machines use to store user and service passwords. It’s also commonly referred to as NTLM, which references the previous version of Windows format for hashing passwords known as LM, thus NT/LM.

o formato é nt no john

## Cracking Hashes from /etc/shadow

unshadow (path to passwd) (path to shadow) > destin.txt

