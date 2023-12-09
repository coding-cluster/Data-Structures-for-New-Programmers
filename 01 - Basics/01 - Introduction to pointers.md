# <p align="center">Introduction to pointers</p>
## <p align="center">How memory works</p>

When we talk about program execution, we mostly talk about the RAM (Random Access Memory)
and it can be thought of as a big array of bytes. Bytes are the basic units of 
information in computer storage, they consist of eight binary digits. Each of these bytes
represent one space in memory, and each of them has an address. So, when we declare variables
in C or C++, we are storing these bytes in memory, and we are giving them an address. Of
course, the amount of bytes we take up in memory, depends on the data type (e.g. int and
float take up to 4 bytes, and char takes up to 1 byte).

Let's take a look at the following example:

```int a;``` <- This is an integer a, and it takes 4 bytes in memory (i.e. if this variable
is declared in the space 203, because each integer takes up to 4 bytes, it will be stored in
the spaces 203, 204, 205, 206).

## <p align="center">What are pointers?</p>

Pointers are practically variables that store the address of another variable, so, let's
imagine that we want to store the address of `a`, well, we can do it like this:

```c
#include <stdio.h>

int main()
{
    int a;      // Variable to use
    int *p;     // Our pointer variable (it needs to have an asterisk before its name, this is what we call "dereferencing")
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

## <p align="center">Referencing and Dereferencing?</p>

You might know by now that a reference allows you to refer or "point" to the data stored in a variable,
as well as its memory address and data type, but, **what is a dereference?** Well, dereferencing something
means, that instead of just refering or pointing to that datum (the information stored), you are actually
manipulating or accessing to the datum of that variable.

The importance of knowing the difference of both is, that when you dereference, you are able to do as you
please with what's contained in the variable pointed, which is something that we'll explore a bit more in
the next lesson.

## <p align="center">Recap</p>

1. Information is stored in bytes in your memory, and every byte has an address, hence information has too
1. Pointing allows you to refer to the datum or information stored in a specific memory location
1. A reference points to the data stored as well as the memory address
1. A dereference lets you manipulate the data refered

These are just some of the basics of what pointers are, in the upcoming lessons, we will delve into more details.

**SEE YOU IN THE NEXT LESSON!**

## More resources

If you want to delve a bit more in the topic, you can visit the next resources!

[WIKIPEDIA]
https://en.wikipedia.org/wiki/Reference_(computer_science)#:~:text=In%20computer%20programming%2C%20a%20reference,is%20called%20dereferencing%20the%20reference.

[TUTORIALS POINT]
https://www.tutorialspoint.com/what-does-dereferencing-a-pointer-mean-in-c-cplusplus

[W3Schools]
https://www.w3schools.com/c/c_pointers.php
