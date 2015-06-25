{% import "macros/ork.jinja" as ork with context %}
Exercise 6 Integers
*******************

In `Exercise 3 Maths and Numbers <ex3.html>`_ we covered some basic arithmatic you can do with numbers. This section goes a little further.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > int i = 0;
  > float f = 10.567;
  > int i = 2;       
  > write(sprintf("%f\n", i+f));
  12.567

You can do arythmatic with `float` and `int` variables, the output automatically becomes a float.

`float` and `int` are not interchangable, to be able to use a `float` in the place of an `int` you need to cast it by putting `(int)` in front. This simply drops everything of from behind the decimal point, as you see below.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > float f = 10.567;
  > write(sprintf("%d\n", (int)f));
  10

It's also possible to cast an `int` to a `float`, using `(float)`

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > int i = 2;       
  > write(sprintf("%f\n", (float)i));
  2.000

For floating points accuracy is important, although this accuracy doesn't always need to be on display. Using a modifier for `sprintf` allows you to limit the decimal places you display. For one decimal place this would be `%.1f`, for 2 decimal places `%.2f`, for 3 `%.3f`, etc.

::

  Pike v7.8 release 700 running Hilfe v3.5 (Incremental Pike Frontend)
  > write(sprintf("%.2f\n", f));
  2.30


