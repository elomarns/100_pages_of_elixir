### The match operator

Let's start by destroying one of the basis of programming: the operator `=`. You probably know it as the assignment operator, but Elixir calls it the match operator. And it's not just a fancy name to the same thing. It actually works differently:

```irb
iex(1)> age = 34
34
iex(2)> 34 = age
34
iex(3)> 18 = age
** (MatchError) no match of right hand side value: 34
```

In the code above I'm using the match operator to make an assertion that what's on the right side (the term) somehow matches what's on the left side (the pattern). That's pattern matching. And if Elixir can make the match works, the term on the right side is returned, otherwise, it raises an error.

If this sounds a little bit abstract, maybe it can be helpful to think about the `=` operator as you would in math. In equations, the `=` operator is used to assert the equality of two expressions. That's pretty much what happens in Elixir too. But how Elixir performs the matching depends on what's on both sides, so let's analyze the code above line by line to understand it better:

```irb
iex(1)> age = 34
34
```

This line of code may seem very simple but can easily mislead you. This is not an assigning, this is a pattern matching expression. In this case, the matching succeeds by simply binding the term (`34`) to the variable `age`. In cases like this, the match always succeeds, because Elixir always binds the term on the right to the variable on the left.

```irb
iex(2)> 34 = age
34
```

Here I did the opposite: I have a variable on the right side (`age`) and a term on the left side (`34`). As the variable is bound to a simple value (a number), and on the left side there's the same value, the match happens. However, it can be more complex with compound data structures, as you'll see a few chapters ahead.

```irb
iex(3)> 18 = age
** (MatchError) no match of right hand side value: 34
```

And now you can see when a matching fails. The variable `age` has the value `34`, which is not the same as `18`, so the match fails, and an error is raised.
