---
title: Other Learning Projects
weight: 6
---

## Other Learning Projects

Aside from the exercises, kata, koan and other assorted bits and bytes, I'm also building a few of my own little projects to help sharpen my F# chops. My first foray was an Azure Function app that takes a URL and retrieves openGraph data from the targeted web page. There's also the [Fauxlemetry](https://github.com/houstonhaynes/Fauxlemetry) CLI project, which is a small applet I use to generate large sets of production-scaled event data.

I'm also learning how to use [Snowflaqe](https://github.com/Zaid-Ajaj/Snowflaqe), a meta-programming project from Zaid Ajaj. It's a fascinating microcosm into one of F#'s real super-powers - that it can be used to generate new, canonical code - so ***meta!*** I used it to generate a client that scraped GitHub's public GraphQL schema which then formed the structured types for a client interface library. The Types.fs file generated more than 3500 lines of error-free code that I would never have to look at other than to satisfy my curiosity. It's like magic. My goal was relatively mundane by comparison - to collect repository data, chart the relative growth of functional-friendly languages relative to other programming styles over the past 10 years. It's still in early stages but I'm hoping to complete the project end-to-end in F#/.NET and resist falling back to R.

But that's just the start. Right now the challenge is to maintain the core lessons (and the hardware project above) while not getting too distracted by the "new shiny" idea that pops into my head. It's the kind of problem I love to have.

## The Future is Functional

My vision of a path forward with F# is taking shape. Fable, Xamarin, Meadow, C#/.NET interop face *out* while Akka.NET, Kubernetes and Event Store provide the base for a reactive platform that's fast, flexible, resilient and maintainable. The clarity of this sits in stark contrast to those lessons in my career where poor early choices and tech fragmentation were a project's undoing. 


![fsharp_ecosystem.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659494196785/FTMS8vqPc.png align="left")

And the objective should not *only* be improved user experience or reduced burn rate but also a more sustainable operational framework. We as an industry must look beyond cost considerations to sustainability and reduction of carbon footprint. Bringing these intelligent tools together gives me a renewed sense that it's not only *possible* to create a solution greater than the sum of its parts, but that its inherent efficiency is also a more *responsible* approach. And so, the work continues...

* [What The F# is Next (original)](/perspectives/WTFSIN_1)
  * [Warehouse Full of Cannibals](/perspectives/WTFSIN_1/warehouse_full_of_cannibals.md)
  * [The Wrong Kind of DDD](/perspectives/WTFSIN_1/the_wrong_kind_of_DDD.md)
  * [A More Functional Approach](/perspectives/WTFSIN_1/a_more_functional_approach.md)
  * [Machine Learning](/perspectives/WTFSIN_1/machine_learning.md)
  * [Success and Kinesthetic Learning](/perspectives/WTFSIN_1/success_and_kinesthetic_learning.md)
  * [Akka.NET, Actor Model and the Reactive Manifesto](/perspectives/WTFSIN_1/akka_and_the_reactive_manifesto.md)
  * Other Learning Projects
  * [Coda - Microsoft, The Enterprise & The Open Source Balancing Act](/perspectives/WTFSIN_1/coda_open_source_balancing_act.md)