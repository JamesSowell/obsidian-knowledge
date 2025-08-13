

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



# Pointers
`int* ptr = &a`
you can move pointers to point to other reference.

You can *dereference* a pointer to CHANGE the value at that address. But be careful if the ptr is pointing to null. IN which case use
`if (ptr != nullptr) {}`


**Dynamic Arrays**
```c++
int n = 5;
int* arr = (int*)malloc(n * sizeof(int)); // allocate memory for 5 ints;

// because arr is of type int*, it scales by sizeof(int) for you!
for (int i = 0; i < n; i++){
	*(arr + i) = i * 10; // pointer aritmetic: arr[i] is same as *(arr + i)
}

for (int i = 0; i < n; i++){
	printf("%d", *(arr + i)); // 0 10 20 30 40
}

free(arr); 
```



**Lower Level bytes**
`int*` sizeof(int) bytes (*usually 4*)
`double*` sizeof(double) bytes (*usually 8*)
`char*` sizeof(charb) bytes (*usually 1*)

`(char*)arr + (i + sizeof(int)) // if you cast to char* (raw bytes)`

> atomic level: bytes not bits. The smallest *addressable unit* of memory is a **byte**

**Bonus: void**** 
you must cast because `void*` has no size!
```c++
// malloc returns a void* so you need to cast it anyways!
// sizeof() returns number of bytes that the type allocates!
void* raw = malloc(n * sizeof(int));
// casting to TRUE memory-sized pointer, ie int*
int* arr = (int*)raw;
*(arr + i);
```

`void*` I point to something, but I don't know what

**Chars are Tricky**
They can represent:
1. A character (like `A`) 
2. A raw byte (like `0xFF`)
3. Part of a larger type (like one byte of an `int`)

Chars in memory:
```c++
char c = 'A';
int x = 65;
```
```typescript
c: [41].     // 1 byte (hex 0x)
x: [41 00 00 0
```


# endianness?
Preface:
some data such as certain English characters can be represented by a single byte. 
Some datatypes require more than a *single* byte. **Endianess** is crucial for how these bytes are read and interpreted by computers.


**Big Endian**
stores the most significant byte (the 'big end') first. 
**Little Endian**
stores the *least* significant byte first.




[ 'samaj', ']


# Objects in memory
Still in the *memory sphere*, Like an array in that all the members of that object are in a *chunk* of memory


In C++, every `non-static member function` has access to a hidden pointer called `this`

`this` is a *pointer* to thte current object instance.

Therefore when you have a method that has `return *this` it returns the actual *instance* that the *this* pointer is pointing to.



Notes:
`C++ is is a semantic jungle: a language where syntax is a signal to the compiler, not just a sequence of instructions`