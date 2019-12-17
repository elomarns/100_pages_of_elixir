### Guarding your functions

You can spice up your functions even more by giving guards to its clauses. A guard is just an extra expression which needs to evaluate to `true` so that clause can be executed. To add a guard to an anonymous function clause, just add `when` after its parameters, followed by one or more conditions:

```irb
iex(1)> old_enough_to_drink = fn
...(1)>   age when is_integer(age) and age >= 21 -> true
...(1)>   age when is_integer(age) -> false
...(1)>   _ -> "How about you give me an integer?"
...(1)> end
#Function<7.91303403/1 in :erl_eval.expr/5>
iex(2)> old_enough_to_drink.(21)
true
iex(3)> old_enough_to_drink.(18)
false
iex(4)> old_enough_to_drink.("seventeen")
"How about you give me an integer?"
```

But guards have its limitations. You can only use a small subset of all available functions and operators on your guards. You can see the [full list of guards on Elixir documentation](https://hexdocs.pm/elixir/Kernel.html#guards), but here is a brief summary of what you can use:

* Comparison operators:  `==`, `!=`, `===`, `!==`, `>`, `>`=, `<` and `<=`.
* Boolean operators: `and`, `or` and `not`.
* Arithmetic operators: `+`, `-`, `+` (unary), `-` (unary), `*` and `/`.
* List operators: `in` and `not in`.
* Functions that check data types: `is_atom/1`, `is_binary/1`, `is_bitstring/1`, `is_boolean/1`, `is_float/1`, `is_function/1`, `is_function/2`, `is_integer/1`, `is_list/1`, `is_map/1`, `is_number/1`, `is_pid/1`, `is_port/1`, `is_record/1`, `is_record/2`, `is_reference/1` and `is_tuple/1`.
* Functions that work with basic data types: `abs/1`, `div/2`, `mod/2`, `round/2`, `trunc/1`, `length/1`, among others.
