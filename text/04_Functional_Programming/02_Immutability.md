### Immutability

One of the defining features of functional programming is the immutability of data structures. You just can't change data. I know it sounds weird and even useless for a programming language, but it's not. It's actually a great feature. But first you need to be sure you really understand what immutability means, so let's analyze what's happening in this snippet of code:


```irb
iex(1)> name = "Elomar Nascimento dos Santos"
"Elomar Nascimento dos Santos"
iex(2)> String.upcase(name)
"ELOMAR NASCIMENTO DOS SANTOS"
iex(3)> name
"Elomar Nascimento dos Santos"
iex(4)> name = String.upcase(name)
"ELOMAR NASCIMENTO DOS SANTOS"
iex(5)> name
"ELOMAR NASCIMENTO DOS SANTOS"
```

Maybe you got it what happened here, but let's discuss line by line to make sure it's clear.

```irb
iex(1)> name = "Elomar Nascimento dos Santos"
"Elomar Nascimento dos Santos"
```

I start by creating a string and binding the variable `name` to it.

```irb
iex(2)> String.upcase(name)
"ELOMAR NASCIMENTO DOS SANTOS"
```

This line can spark some confusion. I'm not changing the original string, I'm creating a second string based on the first one.

```irb
iex(3)> name
"Elomar Nascimento dos Santos"
```

In this line, we can confirm that the first string wasn't changed.

```irb
iex(4)> name = String.upcase(name)
"ELOMAR NASCIMENTO DOS SANTOS"
```

Here I create a third string, again converting all characters in the first one to uppercase. But this time I bind the variable `name` to this new string.


```irb
iex(5)> name
"ELOMAR NASCIMENTO DOS SANTOS"
```

In this last line, I'm checking if the variable `name` is actually bound to the value we expect it to be: the string with all uppercase characters.

So, in the end, I have produced three independent strings, and after creation, they remain untouched. What changed was which one of them was bound to `name`. That's it. That's how you work with immutable data: you just bind variables to new data while the old data lies around. And if there's no other variable bound to the old data, the garbage collector will remove it.

Immutable data is good because it completely eliminates the dubious nature of function calls. With immutability, you won't ever ask yourself if you changing data or just getting new data based on a previous value. You're always getting new data. And it eliminates a problem other platforms have when doing concurrent programming: synchronizing shared data. You don't need to worry about data being shared by two different functions (concurrent or not), because none of them are modifying it, so you're safe. The data has exactly the same value it had when it was created.

Another big bonus resulting from immutability is the possibility to write pure functions. A pure function is a function with no side effect, as it doesn't change any data. So if you call a pure function multiple times with the same arguments, it will always have the same return value. Because of that, pure functions are much easier to write, understand and test. In a way, you can say pure functions are closer to mathematical functions.

But it's important to be aware that only Elixir/Erlang data structures are immutable. That doesn't apply to outside data your Elixir code may interact with. For example, if you're developing an application with any kind of external storage like a database or even a text file. This external storage is beyond the realm of Elixir, so it can be mutated. A function that interacts with this kind of external data may not be a pure function if it performs any IO operation in the external storage. So you need to be extra cautious when dealing with this kind of function. But at least the Elixir representation of the external data is immutable.
