### The match operator

Let's start by destroying one of the basis of programming: the operator `=`. You probably know it as the assignment operator, but Elixir calls it the match operator. And it's not just a fancy name to the same thing. It actually works differently:

```irb
iex(1)> age = 34
34
iex(2)> 34 = age
34
iex(3)> 18 = age
** (MatchError) no match of right hand side value: 34
iex(3)> [one, two, three] = [1, 2, 3]
[1, 2, 3]
iex(4)> one
1
iex(5)> two
2
iex(6)> three
3
```

In the code above I'm using the match operator to make an assertion that what's on the right side (the term) somehow matches what's on the left side (the pattern). That's pattern matching. And if Elixir can make the match works, the term on the right side is returned, otherwise, it raises an error.

If this sounds a little bit abstract, maybe it can be helpful to think about the `=` operator as you would in math. In equations, the `=` operator is used to assert the equality of two expressions. That's pretty much what happens in Elixir too. But how Elixir performs the matching depends on what's on each side, so let's analyze the code above in more detail:

```irb
iex(1)> age = 34
34
```

This seemingly simple line of code can easily mislead you. This is not an assignment, this is a pattern matching expression. In this case, the match succeeds by simply binding the term (`34`) to the variable `age`. In cases like this, the match always succeeds, because Elixir always binds the term on the right to the variable on the left.

```irb
iex(2)> 34 = age
34
```

Here I did the opposite: I have a variable on the right side (`age`) and a term on the left side (`34`). As the variable is bound to a simple value (a number), and on the left side there's the same value, the match happens. However, it can be more complex with compound data structures, as you're going to see a few lines below.

```irb
iex(3)> 18 = age
** (MatchError) no match of right hand side value: 34
```

Now you can see a match failing. The variable `age` has the value `34`, which is not the same as `18`, so the match fails, and an error is raised.

```irb
iex(3)> [one, two, three] = [1, 2, 3]
[1, 2, 3]
iex(4)> one
1
iex(5)> two
2
iex(6)> three
3
```

This is probably the most interesting piece of code in this section. The pattern on the left side has a list of variables, which matches the list of values on the right side. The first variable matches the first value, the second variable matches the second value, and so on. And as the values in the list on the right side are just numbers, the match succeeds by binding them to the corresponding variables. This is a great way to extract data from complex data structures, and it's not limited to lists.