### Adding aliases

When you use multiple namespaces your modules can have really long names. For example:

```plaintext
Guessmoji.Accounts.User
Guessmoji.Media.Emoji
```

And as you must use the full module name when calling its functions, it can be tedious, and result in very long lines. To address this problem, you can use the directive `alias`:

```irb
iex(1)> alias Unnecessarily.Convoluted.Helper
Unnecessarily.Convoluted.Helper
iex(2)> Helper.imaginary_function()
```

Using it this way, you can use just the last part of the module name instead of the full name. But if you want anything different, even a completely new name, you can add the `as` option:

```irb
iex(1)> alias IO, as: MyImprovedIO
IO
iex(2)> MyImprovedIO.puts "It looks the same, but it's much better!"
It looks the same, but it's much better!
:ok
```
