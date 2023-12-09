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

# What is a ponter?

Pointers are practically variables that store the address of another variable, so, let's
imagine that we want to store the address of a, well, we can do it like this:

```int a;``` <- Variable to use

```int *p;``` <- Our pointer variable (it needs to have an asterisk before it's name)

```p = &a;``` <- We declare that **p** equals **a** (it needs to have an & as that allows
us to "point" to that memory address).
