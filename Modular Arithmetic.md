

[[Group Theory]]

group of elements x, p when $gcd(x,p) = 1$

$i \in \Sigma$



*inverse*: $a*a^{-1} \equiv 1 \mod p$ 

> this is the key for all the proofs because to apply multiplations and division we need invertablity

# fermat's little theorem
$a^{p-1} \equiv 1 \mod p$
Another way of saying this in group theoretical terms is:
$a * a^{p-2} \equiv 1 \mod p$

As you an see, the *multiplicative inverse mod p* is that same number raised to the *p-1* power.


When *using* fermat's little theroem is more so in reducing SMALLER exponents...

$a^k \mod p \equiv a^{k \mod p - 1} \mod p$

The above is shorthand after you know that, $a^k$, let's try and get *p-1* in there somewhere!
$k = q(p-1) + r$ where $r \in \{0,...,p-1\}$

as you know p-1 is just some scalar with q, and need *r* to reach *k*

$(a^{p-1})^q * a^r  \mod p$
from here we can apply *fermat's little theorem*

$(1^{p-1})^q * a^r  \mod p \equiv a^r \mod p$

Therefore as long as you have `mod p` then you can just get the remainder, remember the *remainder* from $q * (p-1)$


in **Competetive Progamming**:
for a `prefixProduct`, if you want the usual `prefix[r+1] - prefix[l]`
you need the *multiplicative inverse* in this case to GET just the range that yuo want assuming that you are `% MOD`

you know that 






# Chinese Remainder Theorem (CRT)
just tells us that for *some* system of modular system, there is a CERTAIN *x* that satisfies ALL of the different *modular* wheels for each one!










# Group theory inversese
All elements in the group MUST have EXACTLY *one* inverse element to REACH the identity matrix.


for a number that you want to DIVIDE 

# What Makes Invertibility?

A one to one BIJECTION ON the elements in the set under the operation....
the identity element `e`'s own *inverse* element it is itself e * e = e

BUT $\mod 7$, *6* is an involution! meaning that it's *inverse* element is itself.
$6 * 6 \equiv 1 \mod 7$






	​

 notatio






