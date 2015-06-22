{% import "macros/ork.jinja" as ork with context %}
Exercise 1: Printing
********************

The first program written in any language is the `Hello World` program. This allows you to see the basis of what is required to execute a program. In Pike, it is no different.

Type the following in the editor that you chose in Exercise 0:

{{ ork.code('code/ex1.pike|pyg') }}

And run it from the commandline using *pike code/ex1.pike*, you should see the following in your terminal.

::

  $ pike code/ex1.pike
  Hello World!


Let's break down your first program.

::

  int main ()

This first line sets the definition for the program, `main` is used to declare that this is the main part of the program and contains the functionality for the program, it is also called the main function or main method. `int` declares that at the end of the execution of the program an integer (a whole number) will be returned. The parenthesese are meant to declare arguments that are passed to this main function, here we do not specify arguments.

::

  {

This curly brace `{` opens the internal decleration of the main method, every thing from here until the closing curly bracket belongs to the main method.

::

    write("Hello World!\n");

Here the function `write` is called, this function writes to the screen. As you see this function takes an argument: `"Hello World\n"` The double quotes `"` tells you that this is a string value. A semi-colon `;` is used at the end of the statement to declare that this statement is finished.

::

    return 0;

At the end of this method the `return` statement is used to return a value. Above we declared that we expected an integer to be returned, by convention any non-zero integer indicates that an error happened. In this case, no error happened, so we return the value `0`.

::

  }

This closing curly brace says that we have completed the decleration of the function.


