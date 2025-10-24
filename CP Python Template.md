
# Graph algorithms
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