---
title: "Warehouse Full of Cannibals"
weight: 1
---

I've written about my first software project outside of school building a warehouse management system for a small company that build physical products. We were building electronic musical instruments "from a cold start" as well as doing refurbishments of vintage electronic music gear. But we were staffing up and had grown beyond the ability for Bob (and myself, ostensibly) to go around with all of the parts and component information as a function of collective memory. The challenge was that with *so many* parts sources - including stripping operational parts out of otherwise-broken systems - meant tracking how much of something we *could* build was a major concern. Most of our work was standard off-the-shelf components but there was *just enough* of the boutique part tracing that it really required its own solution.

![Houston, Bob and Dave (Houston's first hire) - 1995](https://cdn.hashnode.com/res/hashnode/image/upload/v1659492388927/_02Au2kT7.jpg align="left")

We not only had to track the parts we ordered from suppliers, but we also had to calibrate for raw materials and lead time required to fabricate some of our own parts built in-house. And all of this was before we had to start cannibalizing out of a smorgasbord of defunct instruments sitting on the back shelves of the warehouse. In many ways it was a logistics nightmare, but the silver lining is that it was built to eventually include *some* predictive capabilities. Little did I know that it would be the kind of problem I'd be solving over and again for the next few decades.

## The Big Event & The Bigger Picture

Inventory management seems pretty mundane - and if you're lucky, it is. *But almost **no one** is so lucky*. There's the many-to-many relationships that emerge: multiple suppliers that can provide the same part, cost versus lead time considerations, it all factors in. And at that time there was no easy online search to find supplier part counts and delivery lead times. You had to get folks on the phone, which takes time and patience. And this system was as much about providing visibility into what's "out there" as what we had on hand. The good news is that once the information was "in the system" then a generalist - an office manager or other line worker - can do a lookup and have a meaningful conversation with nearly anyone in the supply chain. Up to that point, it was either Bob or myself that had to spend time "on the horn" and creating a fan-out for that group of tasks was a pretty sizable force multiplier.

It started with an accounting template, part of what Microsoft's Access plus Visual Basic offering. As I mentioned in my early years with Moog, his son worked at Microsoft and he sent us a beta of the product, and it shaped really well to our problem space. I expanded it in *two* directions - as mentioned we kept notes on sources for off-the-shelf parts, and I *also* built tables for various custom circuit boards and parts we assembled in the shop with the full *bill of materials* (BOM) that each would consume. The "fun" part was coding an optimizer that could give us a view into how many boards we could build before running out of certain key components. So instead of a surprise when looking into a nearly empty bin, we could run checks before setting up for an assembly run to see what we'd need to resupply ahead of time. And beyond the "0 checks" we also used it to show the "shape" that the bins we would be afterward, and provide a view into what we'd need to order to replenish stock before the next run. We had been burned enough times that the investment in a bespoke-ish system was certainly worth the effort. And once we had gotten the primitives in place, the portions that provided the higher level view was an easy add-on.

> It struck me that the folks who build event based systems and the folks who are consumed by byzantine analytics re-platforming ***never talk to each other*** because they're both busy solving similar problems, albeit for different reasons.

My next job was as a developer for an accounting company that provided electronic tax filing software for CPAs. So that wasn't merely dancing around an accounting mindset - this *was* accounting with a twist. We *also* had to deal with a variety of filing regulations with each state, plus US federal tax codes. And there were specific guidelines on how to note a preparer's overrides and all of the amendments and indemnifications that came with it. As it turns out, this was an unexpected early lesson in the winding path my career has taken since then. Here's a 2016 keynote from Greg Young - the person [who originally coined the term 'CQRS' and founder of EventStore DB](https://www.eventstore.com/blog/event-sourcing-and-cqrs), who sums up the event sourced landscape in this brief excerpt.

%[https://www.youtube.com/watch?v=I3uH3iiiDqY&t=355s]

* [What The F# is Next (original)](/perspectives/WTFSIN_1)
  * Warehouse Full of Cannibals
  * [The Wrong Kind of DDD](/perspectives/WTFSIN_1/the_wrong_kind_of_DDD.md)
  * [A More Functional Approach](/perspectives/WTFSIN_1/a_more_functional_approach.md)
  * [Machine Learning](/perspectives/WTFSIN_1/machine_learning.md)
  * [Success and Kinesthetic Learning](/perspectives/WTFSIN_1/success_and_kinesthetic_learning.md)
  * [Akka.NET, Actor Model and the Reactive Manifesto](/perspectives/WTFSIN_1/akka_and_the_reactive_manifesto.md)
  * [Other Learning Projects](/perspectives/WTFSIN_1/other_learning_projects.md)
  * [Coda - Microsoft, The Enterprise & The Open Source Balancing Act](/perspectives/WTFSIN_1/coda_open_source_balancing_act.md)