### Atoms

An atom is a constant whose value is its own name. It must start with a colon (`:`), followed by UTF-8 letters, numbers, underscores, and at signs (`@`). However, the first character after the colon can't be a number or an at sign, and you can finish an atom with a `?` or `!`:

```irb
iex(1)> :i_am_an_atom!
:i_am_an_atom!
iex(2)> :_@m_i_an_atom_too?
:_@m_i_an_atom_too?
iex(3)> :yes_there_are_3_atoms_here
:yes_there_are_3_atoms_here
iex(4)> :4_if_you_include_me
** (SyntaxError) iex:4: unexpected token: ":" (column 1, code point U+003A)

iex(4)> :@atoms_are_great
** (SyntaxError) iex:4: syntax error before: atoms_are_great
```

An atom can also represent an operator:

```irb
iex(1)> :+
:+
iex(2)> :-
:-
iex(3)> :*
:*
iex(4)> :/
:/
```

Another way to create an atom is to surround its content with quotes. This way you can include anything that would break the rules described above:

```irb
iex(1)> :"1"
:"1"
iex(2)> :"@"
:@
iex(3)> :"now we can have some space"
:"now we can have some space"
```

One important thing to keep in mind is that atoms are not garbage collected, so you shouldn't create atoms dynamically based on the user's input. They are meant to be used as an efficient way to label concepts in code.
