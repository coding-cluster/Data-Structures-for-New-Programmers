# How memory works

When we talk about program execution, we mostly talk about the RAM (Random Access Memory)
and it can be thought of as a big array of bytes. Each of these bytes represent one space
in memory, and each of them has an address. So, when we declare variables in C or C++, we
are storing these bytes in memory, and we are giving them an address. Of course, the amount
of bytes we take up in memory, depends on the data type (e.g. int and float take up to 4
bytes, and char takes up to 1 byte).

Let's take a look at the following example:

```int a;``` <- This is an integer a, and it takes 4 bytes in memory (i.e. if this variable
is declared in the space 203, because each integer takes up to 4 bytes, it will be stored in
the space 203, 204, 205, 206).

# What is a pointer?

Pointers are practically variables that store the address of another variable, so, let's
imagine that we want to store the address of a, well, we can do it like this:

```cpp
#include <iostream>

int main()
{
    int a;      // Variable to use
    int *p;     // Our pointer variable (it needs to have an asterisk before its name)
    p = &a;     // We declare that **p** equals **a** (it needs to have an & as that allows us to "point" to that memory address).

    /*
    Why is doing this (p = &a) necessary?
    
    Because we are storing the address of a in p,
    without this, we can't point to that address.
    */

    a = 5;      // We initialize the variable
}
```

Now, what happens if we try to print `p`
> [!NOTE]
> We'll play a bit with pointers, so we'll print **p** using three properties and **a** in one special way

```cpp
    std::cout << p << std::endl;    // Prints memory address (e.g. 0xd145ffad4)
    std::cout << *p << std::endl;   // Prints the value of the variable (e.g. 5)
    std::cout << &p << std::endl;   // Prints memory address of p (e.g 0xd142bdfe4)
    std::cout << &a << std::endl;   // Prints the memory address of the variable (e.g. 0xc142fcab4)
```

### Why does this happen?
1. Because p is a variable storing the address of a, when we print p we are actually printing a's memory address.
1. We are printing the value stored in the address of a, which is 5. This is called **dereferencing**.
1. We are referencing the memory address of p, which will result in printing its address.
1. We are referencing the memory address of a, which will result in printing its address.

These are just some of the basics of what pointers are, in the upcoming lessons, we will delve into more details.

**MUCH OBLIGED! 😎**
