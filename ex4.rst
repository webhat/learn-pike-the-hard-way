{% import "macros/ork.jinja" as ork with context %}
Exercise 4 Variables
********************

Variables are containers in which you can store values, these usually refer to containers whose value can change.

Variables come in different types, we'll cover most in the next exercises, they can be created like this:

::

  int x;

This instruction starts with the type `int` and signifies that the variable `x` is an Integer. Creating a variable without assigning it a value means pike sets the value to an empty value. In the case of as integer this is zero `0`. However, in the case of a string this is also zero `0`.

Try the following in your pike console:

::

  string x;
  Stdio.stdout.write(x);

You should get an error similar to the following error:

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > string x;                          
  > Stdio.stdout.write(x);             
  Bad argument 1 to Stdio.File->write()(). Expected string|array(string).
  Unknown program: Stdio.File->write()(0)
  -:1: write(0)
  -:1: Stdio.FILE("stdout", 0, 777 /* fd=1 */)->write()
  /usr/local/pike/7.8.700/lib/modules/Stdio.pmod/module.pmod:1979: Stdio.FILE("stdout", 0, 777 /* fd=1 */)->write(0)


Common practise in many programming languages is to assign a value to a variable when it's instantiated using an equal sign `=`. Below we assign an empty string `""` to the variable `emptystring`.

::

  string emptystring = "";


It's possible to overwrite this value by using the equal sign `=` to assign a new value, in this case `"not empty"` to the variable `emptystring`.

::

  string emptystring = "";
  emptystring = "not empty"

We immediately see an important issue with variables, it's not always clear what it contains unless you examining it. Naming things is hard, so it may not always contain what it says it contains.

Constants
*********

Constants are much like variables with one exception, once they are set to a value that value can no longer be changed.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > constant x = 0;
  > x = 10;        
  Compiler Error: 1: Illegal lvalue.
  > 


