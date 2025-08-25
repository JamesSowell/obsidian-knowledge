

# Convex Hull Trick
for the *jumping* problem, and you need to return *minCost(i)* to get to i for all i in A.
`dp(i) = dp(j) + A[i] * A[j]
AKA
*b + xm*
where finding *x* is given by the convex hull trick...


# Segment Trees (coordinate, driven)
same *o << 1 ^ 1* and `o << 1` for *actual* tree traversal. But this can remain as a *key*

(L, R) can be you're cognitive guide! *Therefore this option is great for debugging* (print(l,r))

All you need to be aware of is when `L == R` that means that you have reached a child! *(R is inclusive)*


instead of *full* updates on the entire tree, you can have a *maintain(o)* which is a one-liner of
```python
def maintain(o: int):
	# or whatever operator. The idea is that other recursive calls will run 
	# this after they have their 'children' update!
	tree[0] = max(tree[o << 1], tree[o << 1 ^ 1])
```