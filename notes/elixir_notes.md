Created: 28032025

1 is an integer
1.0 is a float

`div(4, 2)` does integer division
so does `div 4, 2`

`rem 10, 3` gives the division remainder
`rem 10, 3` gives an output of 1
this is making sense now, since 3 + 3 + 3 + 1

Notice that Elixir allows you to drop the parentheses when invoking
functions that expect one or more arguments. This feature gives a cleaner
syntax when writing declarations and control-flow constructs. However,
Elixir developers generally prefer to use parentheses.

float numbers require a dot followed by at least one digit and also support `e`
for scientific notation

scientific notation looks like `1.0e-10`

floats in Elixir are 64-bit

`round(3.69)` rounds to 4
`trunc(3.69)` truncates to 3

`is_integer(1)` returns true
`is_integer(2.1)` returns false

we can use `true` and `false` as boolean values
`or`, `and`, `not` are boolean operators and expect to have something that evaluates
to a boolean as their first argument
`false or is_boolean(true)` returns true
1 and true would return an error, as 1 is not a boolean value that and can parse
as an argument

`or` and `and` are short-circuit operators that will only execute the right side
if the left side is not enough to determine the result

`true or raise("Hello World")` will return true

<<<<<<< HEAD:elixir-notes.md
Strings are created using double quotes

Interconnect two strings with `<>`

You can also do string interpolation

string = "world"
"hello #{string}!"
"hello world"
=======
!
!
!

!
!

> > > > > > > 1f55f11378e995db93d70edd33bcb4a5bea9b4bc:main-notes/elixir-notes.md
