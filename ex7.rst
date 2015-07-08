{% import "macros/ork.jinja" as ork with context %}
Exercise 7 Strings
******************

A `string` accepts all the operators that an it accepts:

====
plus
====

::

  > "abcdef"+"a";

  Result: "abcdefa"


  > "this"+" is"+" an"+" example";

  Result: "this is an example"

=====
minus
=====

::

  > "abcdef"-"a";

  Result: "bcdef"


  > "abcdefabcdefabcdef"-"a";    

  Result: "bcdefbcdefbcdef"

========
multiply
========

::

  > "a"*10;

  (9) Result: "aaaaaaaaaa"


======
divide
======

::

  > "abcdef"/"";

  Result: ({ /* 6 elements */ "a", "b", "c", "d", "e", "f" })


  "abcdefabcdefabcdef"/"a";

  Result: ({ /* 4 elements */ "", "bcdef", "bcdef", "bcdef" })

  "abcdefabcdefabcdef"/4;
  Result: ({ /* 4 elements */ "abcd", "efab", "cdef", "abcd" }) // notice the absence of "ef"

  "abcdefabcdefabcdef"%4;
  Result: "ef"


==========
Comparison
==========

::

  a == b
  a != b
  a > b
  a >= b
  a < b
  a <= b


=================
Bitwise Operators
=================

::

  a << b
  a >> b
  ~ a
  a & b
  a | b
  a ^ b


========
Indexing
========

::

  a [ b ]
  a [ b ] = c	
  a [ b .. c ]
  a [ .. c ]
  a [ b .. ]

==========
Assignment
==========

::

  variable += expression  variable = variable + expression 
  variable -= expression  variable = variable - expression
  variable *= expression  variable = variable * expression
  variable /= expression  variable = variable / expression
  variable %= expression  variable = variable % expression
  variable <<= expression variable = variable << expressions
  variable >>= expression variable = variable >> expressions
  variable |= expression  variable = variable | expression
  variable &= expression  variable = variable & expression
  variable ^= expression  variable = variable ^ expression

As said in the `Exercise 5: Types Overview <ex5.html>`_ a `string` is an `array` of characters. And as it's an array it's possible to do many of the things with it that you can do with a `array`.


