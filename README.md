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

v.back() //-> It is a function which will return the last element of vector i.e. prints 50
```

-> Methods to loop through vector:
``` c++
vector<int> v(5) = {1,2,3,4,5};

for(vector<int>::iterator it = v.begin() ; it != v.end(); it++)
    cout << *it << " ";

for(auto it = v.begin() ; it != v.end() ; it++)
    cout << *it << " ";
    
for(auto a : v)
    cout << a << " "; // here a is not an address holder instead it will direct give you values in the vector
```
-> Erase a vector
``` c++
vector<int> v = {10, 20, 30, 40, 50, 60, 70, 80, 90};
v.erase(v.begin() + 1); erases 20 located at index 1

vector<int> v = {10, 20, 30, 40, 50, 60, 70, 80, 90};

// v.begin() + 1 points to 20 at index 1
// v.begin() + 4 points to 50 at index 4

v.erase(v.begin() + 1 , v.begin() + 4 );
// This will erase elements start index upto element before end index given
// Means {20, 30, 40} will be deleted.
// v will be = {10, 50, 60, 70, 80, 90}
```
-> Insert at Vector
``` C++
vector<int> (2 , 50); // {50, 50}

//v = {10, 20, 30, 40}
v.insert(v.begin() , 55); //  will insert at begin {55, 10, 20, 30, 40}
v.insert(v.begin() + 1 , 33); // {55, 33, 10, 20, 30, 40}
v.insert(v.begin() + 2 , 5 , 77) // This will insert 5 instances of 77 from position 2 -> {55, 33, 77, 77, 77, 77, 77, 10, 20, 30, 40} 

// v = {10, 20, 30, 40}
vector<int> vcopy(2, 11); // vcopy = {11, 11}
vcopy.insert(vcopy.begin() + 1 , v.begin() , v.end()); // insert elements/vector in vcopy from start index 1 and insert elements in v from v.begin() till v.end()
// Output : 
// v = {10, 20, 30, 40}
// vcopy = {11, 10, 20, 30, 40, 11}
```

-> Others 
``` c++
v = {1,2,3,4};

v.size(); // 4

v.pop_back() // deletes last element i.e. 4

v.empty() // return true if vector is empty

v.clear() // clears the entire vector i.e. makes it empty

v1 = {1 , 2};
v2 = {4 , 5};
v1.swap(v2); // This will swap v1 with v2
// O/P : 
v1 = {4 , 5};
v2 = {1, 2};
```

-> Insert in a vector is a costly operation because a singly linked list is maintained for a vector.

## **LIST**

-> Exactly similar as vector /br
-> The main difference is that you can perform operations from the front side also. /br
-> A doubly linked list is maintained for a List hence insertion is less costlier than vector. /br

``` C++
list<int> lst;
lst.push_back(1); //{1}
lst.emplace_back(2); //{1,2}

lst.push_front(9); // {9 , 1 , 2}
lst.emplace_front(10); // {10 , 9 , 1, 2}
```

-> All other functions are exactly similar as Vector 
``` c++
// {10,9,1,2}
cout << *(lst.begin()) << endl; // 10
cout << *(--lst.end()) << endl; // 2

cout << *(lst.rbegin()) << endl; //2
cout << *(lst.rend()) << endl; //10

// Swapping
list<int> new_lst = {5,4,3,2,1};
cout << "Before Swapping";
cout << "\nlst" <<endl;
for(auto i : lst)
    cout << i << " ";
cout << "\nnew_lst" <<endl;
for(auto i : new_lst)
    cout << i << " ";

lst.swap(new_lst);
cout << "\nAfter Swapping";
cout << "\nlst" <<endl;
for(auto i : lst)
    cout << i << " ";
cout << "\nnew_lst" <<endl;
for(auto i : new_lst)
    cout << i << " ";
// Output : 
//Before Swapping
//lst
//10 9 1 2 
//new_lst
//5 4 3 2 1 
//After Swapping
//lst
//5 4 3 2 1 
//new_lst
//10 9 1 2 
```









