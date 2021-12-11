# Const and Ampersand in C++ 

## Const keyword:

Constant is something that doesn't change. In C++ we use the keyword const to make program elements constant. const keyword can be used in many contexts in a C++ program. It can be used with:
1. Variables
2. Pointers
3. Objects
4. Methods
5. Class Data members

Whenever const keyword is attached with any variable, pointer variable, method and with the object of a class it prevents that specific object/method()/variable to modify its data items value.

## 1. Constant Variables:

There are a certain set of rules for the declaration and initialization of the constant variables:
   
 - The const variable cannot be left un-initialized at the time of the assignment.
 - It cannot be assigned value anywhere in the program.
 - Explicit value needed to be provided to the constant variable at the time of declaration of the constant variable.


```ruby

    int main(){

    Const int i=10;

    Cont int j=i+10; //works fine

    i++; //leads to compile time error

    return 0;

    }

```
----------

## 2. Const Keyword With Pointer Variables:

When we use const with pointers, we can do it in three ways, which are as follows:
  
 1) When the pointer variable point to a const value:
   
- 
         const data_type* var_name; 
- 
         data_type const * var_name;

 2) When the const pointer variable point to the value:
      
-        data_type* const var_name;
The value that is stored in the pointer variable is modifiable, but the location that is pointed out by const-pointer variable where the value is stored aren’t modifiable.
```ruby     
        int x = 1;
        int* const w = &x;
```
Here, w is a pointer, which is const, that points to an int. Now we can't change the pointer, which means it will always point to the variable x but can change the value that it points to, by changing the value of x.
The constant pointer to a variable is useful where you want a storage that can be changed in value but not moved in memory.
 3) When const pointer pointing to a const variable:
- 
      const data_type* const var_name;

Here, the const pointer variable points to the const variable. So, you are neither allowed to change the const pointer variable nor the value stored at the location pointed by that pointer variable.\

```ruby
     int value = 5;         // non-const value
     const int *ptr_1 = &value;      // ptr_1 points to a “const int” value, so this is a pointer to a const value.
     int *const ptr_2 = &value;        // ptr_2 points to an “int”, so this is a const pointer to a non-const value.
     const int *const ptr_3 = &value;   // ptr_3 points to a “const int” value, so this is a const pointer to a const value.
```

---
## 3.Constant Objects:

+ When an object is declared or created using the const keyword, its data members can never be changed, during the object's lifetime.

+ An object declared as const can invoke only const member functions as these functions ensure not to modify the object.

+ Whenever an object is declared as const, it needs to be initialized at the time of declaration. However, the object initialization while declaring is possible only with the help of constructors.
  
```
     const Class_Name Object_name;
```
---
## 4.Constant Methods:

When a function is declared as const, it can be called on any type of object.
There are two ways of a constant function declaration:

 1. Ordinary const-function Declaration:

```ruby   
    const void foo(){}
    //void foo() const --> Not valid
    int main()
    {
    foo(x);
    }
```
 2. A const member function of the class:

A const member functions never modifies data members in an object.

```ruby
    class
    {
    return_type function_name() const;
    }
```

---
### Constant Function Parameters and Return Type:

```ruby
    void f(const int i){ 
     i++;    // error
    }
    const int g(){
     return 1;
    }
 ```
1.	For built in datatypes, returning a const or non-const value, doesn't make any difference.
2.	For user defined datatypes, returning const, will prevent its modification.
3.	Temporary objects created while program execution are always of const type.
4.	If a function has a non-const parameter, it cannot be passed a const argument while making a call.
5.	A function which has a const type parameter, can be passed a const type argument as well as a non-const argument.

---

## 5.Defining Class Data members as const
   These are data variables in class which are defined using const keyword. They are not initialized during declaration. Their initialization is done in the constructor.

---


# Ampersand(&):
1. & to declare a reference to a type

```ruby
int k = 0;
int& r = k;
//r is a reference to k
```

2. & to get the address of a variable

```ruby
int x;
void* p = &x;
```

3. & as a bit-wise operator

```ruby
int a = 3 & 1; // a = 1
```

4. && in a conditional expression

```ruby
int a=1, b=1 ;

if((a==1) && (b==1)) print(True); 

else print(False);
```

5. Pass an argument by reference to a function


```ruby
void foo(int& x);
//you pass x by reference

//if you modify x inside the function, the change will be applied to the original variable

//a copy is not created for x, the original one is used

//this is preffered for passing large objects
```
