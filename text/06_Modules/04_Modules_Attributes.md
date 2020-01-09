### Module attributes

You can add annotatations to your modules using attributes. To create a module attribute, just declare a value using a identifier starting with `@`:

```irb
iex(1)> defmodule RandomMovieSuggestion do
...(1)>   @movies ["The Squid and the Whale", "Goodfellas"]
...(1)> 
...(1)>   IO.puts @movies
...(1)> 
...(1)>   @movies ["Pan's Labyrinth", "The Shawshank Redemption"]
...(1)> 
...(1)>   IO.puts @movies
...(1)> end
The Squid and the WhaleGoodfellas
Pan's LabyrinthThe Shawshank Redemption
```

After its declaration, you can use a module attribute inside that module's functions, and even in the module's body. And you always get the value at the point you're using it, as you can change it later.

Module attributes are mostly used to annotate your modules with data to be used by the compiler or the user, and also to have something similar to constants in other programming languages. However, it's important to keep in mind that module attributes exist only during compilation.
