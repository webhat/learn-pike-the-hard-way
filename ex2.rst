{% import "macros/ork.jinja" as ork with context %}
Exercise 2: Comments
********************

Code isn't always clear and concise, and sometimes even relatively simple code can be confusing after the passage of time. Documentation can be added to your code to make it more clear for the people who read your code later, or for yourself to understand what is going on.

The single line comment starts from the `//` and ends at the end of the line

{{ ork.code('code/ex2a.pike|pyg') }}

The multi line comment starts at the `/*` and ends with `*/` and can span multiple lines.

{{ ork.code('code/ex2b.pike|pyg') }}
