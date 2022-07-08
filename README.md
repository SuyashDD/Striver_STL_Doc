C++ STL is divided in 4 parts -
1. Algorithms
2. Containers
3. Functions
4. Iterators

---
## **PAIR**

-> Pair resides in unitily library <br />
-> You can declare pair of any datatype <br />

e.g. 

``` c++
pair<int , int> p = {1,3}; // declaration
cout << p.first << " " << p.second; // access values
// pair<char , int> p = {'a',3}; -> This will also work
```
-> A pair of pairs :
 
 ``` C++
 pair<int , pair<int , int>> q = {1 , {2 , 3}};
 cout<< q.first << endl; // prints 1
 cout<< q.second.first << endl; // prints 2
 cout<< q.second.second << endl; // prints 3
 ```

-> An array of pairs : 

``` c++
pair<char , char> arr[] = { {'a' , 'b'} , {'p' , 'q'} , {'s' , 'w'}};
cout << arr[1].second; // prints 'q'
```
---
## **VECTOR**

-> Dynamic array i.e. size is flexible

``` C++
vector<int> v; // creates an empty container
v.push_back(1); // adds 1 in v
v.emplace_back(33); // similar as push_back
// emplace_back is faster and dynamically increases the vector size
cout<<v[0] << ", " << v[1] << endl; // prints - 1, 33
```

-> We can also declare a vector of pair data type

```C++
vector<pair<int , int>> vp;
vp.push_back({3,2});
vp.push_back(8,9); // This statement will generate an error (you can do the same using emplace_back)
vp.emplace_back(5,6); 
cout << vp[0].first << " " << vp[0].second << endl; // prints - 3 , 2
```

-> We can declare a vector will it's fields/values already filled <br />

**Format** : 
``` c++
vector<datatype> {size , value}

e.g. vector<int> {5 , 100} // -> This will create a vector of size 5 filled with value 100 -> {100, 100, 100, 100, 100}

e.g. vector<int> {5} // This will create a vector of size 5 field with either 0 or garbage values depending on the compiler
``` 

**Note** :
``` C++
vector<int> v(5); // This will create - {0, 0, 0, 0 ,0}
v.push_back(9); // So vector will be - {0, 0, 0, 0, 0, 9};
```

-> We can make a copy of new vector using :

``` c++
vector<int> v1(5, 100); // -> {100, 100, 100, 100, 100}

vector<int> v2(v1) // -> This will create a new vector v2 which will be a copy of vector v1 i.e. v2 = {100, 100, 100, 100, 100}
```

 -> One of the other methods to access vector is to use **iterator**
 
 ``` C++
 //Format -
 vector<datatype>::iterator it;

//e.g. -
vector<int> v = {10, 20, 30, 40, 50};

v.begin() //-> points to 10 i.e. stores the memory address of 10 -> points to the very first element in vector
v.end() //-> points to the address after 50. Hence if we need to access 50 then we need to do v.end()--;

cout << *(v.end()); // prints either 0 or garbage value
cout << *(--v.end()); // prints 50

v.back() //-> It is a ==function== which will return the last element of vector i.e. prints 50
```
















