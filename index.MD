# const use cases of the `const` keyword ### constant variable `const` can be used to declare a variable that cannot be assigned a value anywhere in the program. the variable must be initialized at the time of declaration. ```cpp #include <iostream> using namespace std;
int main() { const int x; // compile time error x = 9; // compile time error
const int x = 10;
return 0;
} ``` ### pointer to a constant variable
```cpp #include <iostream> using namespace std;
int main() { int x = 10, y = 15; const int * i = &x; // the value of x can be changed but not through the pointer
x = 20; // valid *i = 20 // unvaild
// the pointer can be changed
i = &y;
return 0;
} ```
### constant pointer to a variable
```  cpp #include <iostream> using namespace std;
int main() { int x = 10, y = 15; const int * i = &x; // the pointer must be initialized // the value of x can be changed through the pointer
x = 20; // valid *i = 20 // vaild
// the pointer cannot be changed
i = &y; // unvalid
return 0;
} ```
### constant pointer to constant variable
neither the variable nor the pointer can be changed
```  cpp #include <iostream> using namespace std;
int main() { int x = 10, y = 15; const int * i = &x; // the pointer must be initialized x = 20; // unvalid *i = 20 // unvaild
// the pointer cannot be changed
i = &y; // unvalid
return 0;
} ```
### const object When an object is declared or created using the `const` keyword, its data members can never be changed, during the object's lifetime. ### const class method `const` methods never modifies data members of an object
### const function arguments we can make arguments of a function as  `const`. Then we cannot change any of them.
```cpp void f(const int i) { i++;    // error } ```
# ampersand(&) use cases of the `&` operator ### declare a reference to a type
if `&` is used in the left side of a variable declaration, it means that you expect to have a reference to the declared type. ```cpp std::string name1 = "my name"; std::string& name2 = name1; ``` Both name1 and name2 will have the same value and they will point to the same location in memory.
### getting the address of a variable it returns the address of the variable.
```cpp int x = 10; int * ptr = &x; ```
### bitwise and operator it takes two numbers as operands and does AND on every bit of two numbers. The result of AND is 1 only if both bits are 1.
```cpp #include <iostream>
using namespace std;
int main() { int a = 111, b = 101;
cout << (a & b); // the parentheses are mandatory
return 0;
} ```
output ``` 101 ```
### logical and(&&) operator ```cpp #include <iostream> using namespace std;
int main() { int a = 5; int b = 9;
// false && false = false cout << ((a == 0) && (a > b)) << endl;
// false && true = false cout << ((a == 0) && (a < b)) << endl;
// true && false = false cout << ((a == 5) && (a > b)) << endl;
// true && true = true cout << ((a == 5) && (a < b)) << endl;
return 0;
} ```
