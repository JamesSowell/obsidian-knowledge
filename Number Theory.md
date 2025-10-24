
[[Modular Arithmetic]]

# LCM and GCD as set theoryy

when seeing an integer as set of prime factors (including duplicates):

**GCD:** is the *intersection* of the *primes*
**LCM**: is the *union* of the *primes*

*gcd* takes the MINIMUM *power* of the primes in both sets. Whilst *lcm* takes the *maximum* prime among EACH of the sets!

$lcm(a, b) = \frac{a \cdot b}{gcd(a,b)}$

GCD extracts common factors.
Multiplying then dividing by GCD throws out the overlap, leaving the union of prime powers.

That “union of prime powers” is exactly the definition of LCM

**GCD is more universal**: using the *"Euclidean Algorithm"* to find the GCD, LCM isn't as trivial, which is why we write

$lcm(a, b) = \frac{a \cdot b}{gcd(a,b)}$
OR
$gcd(a,b) \cdot lcm(a, b) = a \cdot b$

```python
# hierHolzer's algorithm
st = [0]
while st:
	node = st.pop()
	if g[node]:
		stack.extend([nei for nei in g[node]])
	else:
		sol.appendleft(node)
return sol
```




