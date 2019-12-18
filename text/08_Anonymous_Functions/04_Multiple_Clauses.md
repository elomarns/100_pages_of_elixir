### Multiple clauses

Elixir functions have a very special feature: they can have multiple clauses. This means a single function can have multiple bodies, each one of them associated with different parameters:

```irb
iex(1)> favorite_book? = fn 
...(1)>   "100 Pages of Elixir" -> true
...(1)>   _ -> false
...(1)> end
#Function<7.91303403/1 in :erl_eval.expr/5>
iex(2)> favorite_book?.("100 Pages of Elixir")
true
iex(3)> favorite_book?.("Twilight")           
false
```

The anonymous function bound to the variable `favorite_book` has 2 clauses. When you call a function with multiple clauses, Elixir tries to match your argument with each clause, in the order they were defined, and the first to match is executed. So the first call above executes the first clause, as `100 Pages of Elixir` matches the same string in the first clause. `Twilight` in the second call matches `_`, since `_` matches anything, so the second clause is executed.

When no clause matches, an error is raised:

```irb
iex(1)> double = fn
...(1)>   1 -> 2
...(1)>   2 -> 4
...(1)>   3 -> 6
...(1)> end
#Function<7.91303403/1 in :erl_eval.expr/5>
iex(2)> double.(2)
4
iex(3)> double.(4)
** (FunctionClauseError) no function clause matching in :erl_eval."-inside-an-interpreted-fun-"/1   
```

3 clauses were defined for the function above, but none of them matches `4`, so a `FunctionClauseError' was raised.

It's also important to know that all clauses of a function must have the same number of parameters:

```irb
iex(1)> add = fn
...(1)>   a, b -> a + b 
...(1)>   a, b, c -> a + b + c
...(1)> end
** (CompileError) iex:1: cannot mix clauses with different arities in anonymous functions
```

In case you're confused about the error message, the arity of a function or clause is the number of arguments it accepts.
