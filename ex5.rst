{% import "macros/ork.jinja" as ork with context %}
Exercise 5 Types
****************

In pike there are basic types, container types and reference types.

In the following examples we will be examining the variables with `sprintf` and writing them to the screen using `write`.

`sprintf` takes one or more arguments, the first is a string which contains the format containing a combination of text and operators which begin with a percent sign `%`. The next argument or arguments are the values which will be replacing the operators.

Sound complicated? Here's an example:

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%d\n", 0));
  0

In the above example we have the format string set to `"%d\n"`. `%d` means integer, and as you know `\n` is a new line. `sprintf` now expects the second argument to be an integer, in this case it's the integer `0`. `sprintf` is a way of safely printing out values as strings.

If we were simply using `write` to write out the integer 0 we would get the following error:

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(0);
  HilfeError: Error while outputting data.
  Division on different types.
  Unknown program: `/(0,"\n")

Even assigning it to a variable would not help:

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > int x = 0;
  > write(x); 
  Compiler Error: 1: Bad argument 1 to safe_write.
  Compiler Error: 1: Expected: array(string) | string.
  Compiler Error: 1: Got     : int.

So we need a way to safely print the value so our program doesn't break.

Basic Types
***********

===
int
===

The first basic type, which we saw in the previous exercise is the Integer `int`. An Integer is any whole number, positive or negative. And as you saw above we can use `%d` as a way to examine it in `sprintf`.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > int x = 0;
  > write(sprintf("%d\n", x));      
  0
  > x = 2;                    
  > write(sprintf("%d\n", x));
  2
  > x = 2 - 1;                
  > write(sprintf("%d\n", x));
  1

*****
float
*****

A `float` stands for floating point, which is any number with a period in it: `0.3`, `10.0` or `3.14`. Floating points are not always accurate up to a very deep level.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > float f = 2.3;
  > write(sprintf("%f\n", f));  
  2.300
  > write(sprintf("%.2f\n", f));
  2.30

The `sprintf` modifier is `%f`.

=========
character
=========

A character is not strictly a basic type in pike, a char is a way of looking at an integer. All strings are built up our of characters, for example the integer `66` is the character `B`. Character values are surrounded by sincle quotes `'`.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%d\n", 'B'));
  66
  > write(sprintf("%c\n", 66)); 
  B

As you see above the operator that `sprintf` uses for characters is `%c`.

Enclosing more that one character between single quotes will throw the following error.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%d\n", 'BA'));
  Compiler Error: 1: Unterminated character constant.
  Compiler Error: 1: syntax error, unexpected TOK_IDENTIFIER, expecting ')'
  Compiler Error: 1: Unterminated character constant.
  Compiler Error: 1: syntax error, unexpected ';', expecting ')'
  Compiler Error: 1: Missing ')'.

======
string
======

A `string` value is build up out of characters.

====
bool
====

A `bool` is a boolean value, it is either `true` (`1`) or `false` (`0`).

Container Types
***************

Container types are types collections of types, dive in to get some examples. The `sprintf` operator you can use to examine any of the container types is `%O`.

=====
array
=====

An `array` is a numbered list of values which is shown as:

::

  ({ 1, 2, 3, 4, 5})

The array above is an array of `int` values, each element can be refenced by the position it has in the `array`.  You can always tell that something is an array because the values cantained in it are surrounded by `({})`.


::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%d\n", ({ 1, 2, 3, 4, 5})[0]));
  1

Indexes on `array` values start from `0` for the first element in the array, `1` for the second element, `2` ... etc.

Above you see we ask for the element at the first position `({ 1, 2, 3, 4, 5})[0]` to be printed. This prints `1` on the screen.

The best example of an `array` is the `string`, indeed a `string` is an array of `int` values. In memory the string `"Hello World!"` is stored as the following value:

::

  ({
    72,
    101,
    108,
    108,
    111,
    32,
    87,
    111,
    114,
    108,
    100,
    33
  })

As it is an array you can also use an index on a `string` to access a character or integer value of the character in the string.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%d\n", "Hello World!"[0]));
  72
  > write(sprintf("%c\n", "Hello World!"[0]));
  H


=======
mapping
=======

A `mapping` is like an `array`. Rather than the indexes that are ordered by the order they were placed in the `array`, a `mapping` is ordered by the hashed value of the index.

Sound complicated? It isn't really.

::

  (["index":"value"])

A `mapping` with one element looks like this, the mapping has an index of `"index"` and a value of `"value"`.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%s\n", (["index":"value"])["index"]));     
  value

Using `sprintf` we can see what we get when we inspect the value that's being held in the `mapping` at the index `"index"`.


========
multiset
========

The `multiset` is probably the easiest to understand, it is simply an unordered list of values.

::

  (<"foo", "bar">)

This looks like an `array`, but unlike an `array` the order is NOT guarenteed.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%d\n", (<"foo", "bar">)["bar"]));
  1
  > write(sprintf("%d\n", (<"foo", "bar">)["boe"]));
  0

With the square brackets we are no longer extracting the value from the container type, we are merely testing whether the value we pass in in the `multiset`. In the first example `"bar"` is in the `multiset` so we get a `true`, in the second we get `false`.


Reference Types
***************
