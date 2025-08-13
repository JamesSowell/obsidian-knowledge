

Iterators
```c++
struct IntRange {
    struct Iter {
        int cur;  // current value
        int operator*() const { return cur; } // dereference
        Iter& operator++() { ++cur; return *this; } // pre-increment
        bool operator!=(const Iter& other) const { return cur != other.cur; }
    };
    int L, R;
    Iter begin() const { return Iter{L}; }
    Iter end()   const { return Iter{R}; }
};

IntRange r{5, 10};
for (int x : r) std::cout << x << ' ';
```


`for( int x : r) ` will use the `*` on the iterator, which goes to the `std::cout << x << ' '`

After words it accesses the `++` to get to the next 'x'.

The range-based for loop calls:
	auto it = r.begin();
	auto end = r.end();
	While it != end:
		int x = *it;
		++it;




#  references 
Syntactically speaking, *behave* like *variables*
```c++
int a = 1;
int& ref = a;
int b = 10

ref = b // does not rebind ref (it is not a pointer), it reassigns 
```

```C++
int& getElement(int app[], int index){
	return arr[index]	
}

int nums[3] = { 1, 2, 3};
getElement(nums, 1) = 42; // modifies nums[1] directly
```

**Fluent Chaining**
```c++
class Counter {
	int value;
	public: 
		Counter& increment(){
			value++;
			return *this;
		}
}

Counter c;
c.increment().increment();
```


**Buy n Large:** references are useful for more *efficient* variable usage, less *copying* of variables under the hood will be *faster* and are *safer* than *pointers* because you ASSIGN once and only once.

# Objects in memory
Still in the *memory sphere*, Like an array in that all the members of that object are in a *chunk* of memory



