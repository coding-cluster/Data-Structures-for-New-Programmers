# <p align="center">How memory works</p>

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

# <p align="center">What is a pointer?</p>

Pointers are practically variables that store the address of another variable, so, let's
imagine that we want to store the address of a, well, we can do it like this:

```c
#include <stdio.h>

int main()
{
    int a;      // Variable to use
    int *p;     // Our pointer variable (it needs to have an asterisk before its name)
    p = &a;     // We declare that **p** equals **a** (it needs to have an & as that allows us to "point" to that memory address).
    a = 5;      // We initialize the variable
}
```

> [!IMPORTANT]
> **_Why is doing this (p = &a) necessary?_**
> 
> Because we are storing the address of a in p, without this, we can't point to that address.

Now, what happens if we try to print `p`:

```c
printf("%d\n", p);    // Prints memory address (e.g. 0xd145ffad4)
printf("%d\n", *p);   // Prints the value of the variable (e.g. 5)
printf("%d\n", &p);   // Prints memory address of p (e.g 0xd142bdfe4)
printf("%d\n", &a);   // Prints the memory address of the variable (e.g. 0xc142fcab4)
```
**<p align="center">Here's what the terminal prints:</p>**

<p align="center">
    <img src="https://github.com/coding-cluster/Data-Structures-for-New-Programmers/assets/108909645/0479748b-e475-4bec-903e-3d6583a80b19"
</p>

### Why does this happen?
1. Because p is a variable storing the address of a, when we print p we are actually printing a's memory address.
1. We are printing the value stored in the address of a, which is 5. This is called **dereferencing**.
1. We are referencing the memory address of p, which will result in printing its address.
1. We are referencing the memory address of a, which will result in printing its address.


> [!CAUTION]
> Be cautious: If you do not initialize the variable you are pointing to, you will
> get garbage values. So, make sure to initialize your variables before using them
> or printing them to the console! :D

These are just some of the basics of what pointers are, in the upcoming lessons, we will delve into more details.

**MUCH OBLIGED! 😎**
