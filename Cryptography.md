
Ed25519 is based on an elliptic curve called **Curve25519**, over a finite field.
Instead of multiplying numbers, we’re **adding points on a curve**.


# RSA Euler's Totien Realization...
this time was different. I wanted to learn more about the *totient*

Amazing. So much from being intellectually primed from my recent *group theory* mindset. I don't know how else I could've learned about the `a^totien(n) === 1 mod n` where `gcd(a, n) == 1`


Knowing what `gcd(a, n) == 1` is the same as knowing that the *element* a has an *inverse* mod n is EVERYTHING. If there is an inverse that you can undo stuff to it!

From there I had to unpack the *totient* function. Don't see it as some *lawful* function, and more as a *defined* set..

From there when I learned that `U(n) := { x element of {0,...,n-1} | gcd(x,n) == 1`
is just Euler thinking like a progammer and wants more *manipulative* power, and to do that we need the elements that are in fact *invertible*

from there, by picking some numeber from that U(n) you can multiply it to all of them! from there you know that after ` mod n` you can just factor out the `a`s, in which there are `totient(n)` of them! from there since you know that since the *invertible* numbers are a *group*, implies that any operation on them is **Symmetrical** (meaning that the output is another element of the set!)

From there you can use the *congruence*, and perform the *inverse* to both sides and are left with *Euler's theorem*

`a^totient(n) === 1 mod n`

from there. The *algebraic* brain works well with the RSA encryption. Such that you can find the more powerful coprime number *e* which is coprime to *totien(n)* (otherwise you wouldn't get it to cancel out to ONE! the inverse!)

from there you get the *inverse* of d mod n. and using the above totient

All you need is
`S === m^e mod n`
and the *server* just needs to see this original signed *message* and cross verify
`S^d === 1 mod`, but plugging everything in one you get `m^(d*e) === m mod n`!

when raised to the exponent in either order it outdoes the other!!!!!







Modular Arithmetic]]




# HS256
is a *symmetric* encryption algorithm, that RELIES oin the servers to be FEW and required to BE **FAST**.

The tradeoff, vs RS256 is if the key is stolen, that could be catastrophic as they could *pose* as an *issuer* for tokens!

# Block Chaining
*CBC* = "cipher block chaining"



