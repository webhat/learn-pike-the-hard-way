{% import "macros/ork.jinja" as ork with context %}
Exercise 3: Maths and Numbers
*****************************

A computer is a huge calculator and is very good at doing mathmatics.

The simplest kind is addition, this can be done by taking any two numbers and adding them using a `+`.

{{ ork.code('code/ex3a.pike|pyg') }}

::

  $ pike code/ex3a.pike
  2

Change the numbers in the example above to try adding different numbers.

We can also subtract numbers using the `-` sign as in this example:

{{ ork.code('code/ex3b.pike|pyg') }}

::

  $ pike code/ex3b.pike
  8

Again change the numbers to subtract different numbers.

It's also passible to multiply numbers, this is done using the `*`.

{{ ork.code('code/ex3c.pike|pyg') }}

::

  $ pike code/ex3c.pike
  20

And lastly it's possible to divide numbers using the '/' sign.

{{ ork.code('code/ex3d.pike|pyg') }}

::

  $ pike code/ex3d.pike
  5

Important to note that it is not possible to divide any number by zero, such as in this example.

{{ ork.code('code/ex3e.pike|pyg') }}

The code above will case the following error to be displayed:

::

  $ pike code/ex3e.pike
  Division by zero.
  Unknown program: `/(10,0)
  code/ex3d.pike:3: /main()->main()
