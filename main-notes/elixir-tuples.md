Created: 13052025

Type: [[elixir]], [[data-structures]]

Elixir's data structures are immutable.

    List operators never modify the existing list. Concatenating to or removing elements from a list returns a new list. We say that Elixir data structures are immutable. One advantage of immutability is that it leads to clearer code. You can freely pass the data around with the guarantee no one will mutate it in memory - only transform it.

Take this example:

Say we have a tuple that we define as follows

`tuple == {:test, "hello}`
`{:test, "hello"}`

If we were to list the first element of the tuple with the `elem` command

`elem(tuple, 1)`

we would get this output

`"hello"`

`elem` returns the elements of a specified data structure, and takes an argument
of what number element you want listed

You can put an element in a tuple at a particular point using the `put_elem`
command

`put_elem(tuple, 2, "world"_
`{:test, "hello", "world"}`

Now, let's list the originally defined tuple again

`tuple`
`{:test, "hello"}`

Note how it did not change even after we put the `world` element in the tuple.

	The original tuple stored in the tuple variable was not modified. Like lists, tuples are also immutable. Every operation on a tuple returns a new tuple, it never changes the given one.

