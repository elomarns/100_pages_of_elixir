### The answer comes from the past

Many years before the first CPU with multiple cores was developed, there was already a language with great support for concurrency: Erlang. At first, it was released internally at Ericson in 1986, with the goal of improving the development of telephony applications. So concurrency was not the goal, but it emerged as a requirement to fulfill the actual goal. Without concurrency, Erlang wouldn't be able to support the kind of applications it was designed to create. That's why Erlang has maybe the best concurrency model among all programming languages.

But to achieve its mission, Erlang also offers some other interesting features:

* High availability
* Fault tolerance
* Distributed computing
* Hot swapping

Functional programming was the chosen paradigm to implement all these features. It has all the tools to make it easier to build Erlang the way it was designed. It would be much harder to create it as a typical object-oriented language with mutable data structures, for example.

All these capabilities made Erlang a great language, and its age is also an advantage. It's much more mature than any other language with concurrency support, and its VM (BEAM) has been improving for more than 20 years.

But maybe you're wondering why such a fantastic language is not popular. These are the main reasons:

* Its syntax looks a little awkward.
* It has concepts most programmers are not used to.
* Its initial focus was a very specific domain: telephony applications.

So, unfortunately, even though Erlang has a huge potential, especially considering the problems we're facing today, it remains an obscure language.
