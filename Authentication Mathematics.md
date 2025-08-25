kkks
RS256

public key is composed of (n,e)
the private key is composed of (n,d)


d and e are the modular multiplicative inversese with respect to the *totient(n)*

e * d === 1 mod tot(n)
- which is why if you raise a signature to the public key, it serolves to just the message 
- And you raise the m^d you get a signature...

Therefore if you have a *e* and a *signed* token

Signed token (in math() the SHA256(encode(header).encode(payload))) are the message *m*
Then we apply RSA to this whole thing (RSA only works on numbers, not dataSet)

SHA256 is responsible for *crunching* the Data into a number for the *RSA* to perform on!

In the context of juts with rs a signatures, the server doesn't decrypt the signature and the traditional sense of turning it back into some readable message. Instead, it's about verification by transformation. The private key and public keys are inverses neither is above the other in this business context like it is for messages where the data matters...

# RSA256 is asymmetric (two keys, 1 public and 1 private)




