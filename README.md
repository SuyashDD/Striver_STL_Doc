C++ STL is divided in 4 parts -
1. Algorithms
2. Containers
3. Functions
4. Iterators

---
### **Pair**

-> Pair resides in unitily library <br />
-> You can declare pair of any datatype <br />

e.g. 

``` c++
pair<int , int> p = {1,3}; // declaration
cout << p.first << " " << p.second; // access values
// pair<char , int> p = {'a',3}; -> This will also work
```
 -> A pair of pairs can also be declared
 
 ``` C++
 pair<int , pair<int , int>> q = {1 , {2 , 3}};
 cout<< q.first << endl; // prints 1
 cout<< q.second.first << endl; // prints 2
 cout<< q.second.second << endl; // prints 3
 ```
