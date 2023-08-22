---
title: "A More Functional Approach"
weight: 3
---

My path to embracing F# was not without its detours and diversions. It's not my first *or even my second* functional-friendly language. With my time at Siebel I picked up java and spent nearly a decade in that "family". While I had done quite a bit of java proper I also wrote quite a bit of production code with Groovy. Much of that time I felt like I was wrestling as much with the JVM as solving business problems. And between that and Spark/Scala later in the analytics phase of my consulting work I really grew frustrated with the java runtime and shifted focus to C#. Like most folks in analytics I dabbled a bit with Python, but found that [the inherent functional programming (FP) style of R](https://adv-r.hadley.nz/fp.html) along with its unique ability to efficiently process large observation sets made it a clear choice above Python. So from that time forward I was primarily working in C# or R, and only stepped out to Python when it was already present in Jupyter notebooks or other mixed code environments.

When I took a pause during the pandemic to reconsider my options as a systems architect, I kept stumbling across facets of event sourcing that resonated with functional programming. I thought it might be a form of survivor bias, since I had used a handful of FP languages and really like working with R. But then this last footnote from Greg really brought the point home.

%[https://www.youtube.com/watch?v=I3uH3iiiDqY&t=3226s]

So that put a floor under what my personal experiments were hinting at - I wanted to find a general-purpose functional language that had avenues for real-time operational and analytic workloads. I had taken a brief look at F# a few years ago, but it didn't stick. The story wasn't really cohesive, but now with an impressive portfolio of ports to or interop with .NET and the growing meta-programming libraries that extend F#, I thought it was time to consider it the *one language to rule them all*, at least for my own designs.

## To The Point

Unlike my prose, F# is succinct. So aside from being able to take advantage of "life in the .NET ecosystem" it also has the ability to pack a great deal of context into a relatively small block of code. I remember being resistant to that idea when going from java "proper" to Groovy, having grown acclimated to the former's more verbose syntax. And I hear similar comments from C# developers being perplexed with the terse structure of F# code. But with my exposure to Python and R, F# felt like the best of all worlds. You get the clarity of a composed structure using static typing with robust type inference and a compiler that really keeps you from going far astray. F# had a high quality REPL long before it was cool, and there is [hot module reload in the SAFE Stack](https://safe-stack.github.io/docs/recipes/developing-and-testing/using-hot-reload/) with a more general HMR implementation coming to .NET 6 later this year. From the perspective of supporting rapid development, it has the goods.

For an example of F#'s succinct syntax consider this sample from my [Low Code is Dead. Long Live Low Code!](https://h3tech.io/low-code-is-dead-long-live-low-code) blog post. The idea is to illustrate how an F# function extrapolates to C# and then the Intermediate Language that the .NET compiler uses to produce machine code. This isn't to say F# is better or worse than any other language, just that it has certain traits that make it advantageous for a direct form of expression.

## Meta Programming

The thing that really turned my head was [Fable](https://fable.io/). I found out about it after I had just rolled off of a project to build a streaming platform. In that project I had run into a brick wall with Blazor WebAssembly because of the inability to stream DRM protected content through the WASM sandbox. It was a road block that sent me scurrying back to Node and JavaScript, and while the polyglot life is the new normal is today's tech scene it was a point of frustration. Fable offers all of the type safety of TypeScript while rendering JavaScript that can run on any browser.

The real genius of it emerges with the [SAFE Stack](https://safe-stack.github.io/), where sharing allows a single code file to ***transpile* to *multiple* targets**. So you can create one definition that informs both the server interface and the client applications. I was pretty excited about the SAFE Stack because of my work in the R ecosystem - with R markdown, Shiny server and Blogdown's transpiling to HTML. So while I recognized the "meta" pattern I had seen in R, the SAFE Stack demonstrated clearly that F# could span domains in a way I hadn't seen before.

* [What The F# is Next (original)](/perspectives/WTFSIN_1)
  * [Warehouse Full of Cannibals](/perspectives/WTFSIN_1/warehouse_full_of_cannibals.md)
  * [The Wrong Kind of DDD](/perspectives/WTFSIN_1/the_wrong_kind_of_DDD.md)
  * A More Functional Approach
  * [Machine Learning](/perspectives/WTFSIN_1/machine_learning.md)
  * [Success and Kinesthetic Learning](/perspectives/WTFSIN_1/success_and_kinesthetic_learning.md)
  * [Akka.NET, Actor Model and the Reactive Manifesto](/perspectives/WTFSIN_1/akka_and_the_reactive_manifesto.md)
  * [Other Learning Projects](/perspectives/WTFSIN_1/other_learning_projects.md)
  * [Coda - Microsoft, The Enterprise & The Open Source Balancing Act](/perspectives/WTFSIN_1/coda_open_source_balancing_act.md)