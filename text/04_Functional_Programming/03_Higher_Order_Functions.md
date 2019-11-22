### High-order functions

Functions are first-class citizens in Elixir, which means they are a data type like any other. Because of that, Elixir has what is called high-order functions: functions that receive a function as an argument or has a function as its return value.

High-order functions are very useful because they allow you to create highly customizable functions where the caller can plug his code inside your function. For example, Elixir has a function called `each` which receives a collection and a function as arguments. Let's see it in action:

```irb
iex(1)> Enum.each([1, 2, 3, 4, 5], fn number -> IO.puts(number) end)
1
2
3
4
5
:ok
```

You don't need to understand everything it's happening here, it will make sense in the following chapters. For now just know that we call a function (`each`) passing a collection (`[1, 2, 3, 4, 5]`) and another function (`fn number -> IO.puts(number) end`). The function received as an argument was applied to every element in the collection, in this case writing all numbers on your terminal application. This concept is applied in many other functions provided by Elixir, and you can apply it in your functions too.
