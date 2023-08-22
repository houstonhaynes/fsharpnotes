---
title: The Wrong Kind of DDD
weight: 2
---

But the road to this realization was full of detours. While event sourcing and event-driven systems are often associated with domain driven design (DDD) the next decade or so of my career was subsumed with another DDD - ***database* driven development**. I spent some time with IBM Global Services and managing their partner e-commerce DBs around the globe. And that actually had some event sourcing functions as we were correcting and re-loading data in preparation for Y2K. But when I went to Siebel Systems we built out a lab with more than a dozen application and database based systems to simulate various workloads. That was when DBAs - database *architects* ruled the world. Because databases were often the greatest concentration of compute and storage (and therefore expense) it tended to also be the place where business logic would reside. And as anyone who's led a "digital transformation" project will tell you the industry is still living with that legacy imbalance in enterprise n-tier systems to this day.

## You're Projecting

Fast forward to my first Microsoft Gold Partner assignment, a state level court system data warehousing project. They wanted to have a complete history for all court documents, but the old source system didn't record deletes. Well - to be specific they ***actually removed records*** instead of simply marking them with a 'deleted' indicator in the table. This was a vestige of the *precious* mentality of limited storage and compute available in databases from a bygone era. There had been plenty of opportunities to fix that *omission by subtraction*, but no one went to the trouble to do so in the intervening years. So they assumed that it could be magically *fixed* in the new data warehouse as though the information could be generated out of thin air. I eventually found a hybrid solution which could create a differential from monthly backups, loaded as snapshots for comparison. The re-built record delete indicators were only accurate to the end of the month in which they were deleted, but it was better than nothing. The process was tremendously time-consuming and very expensive, but as I've found over the years most analytics systems are the "later" choice of most *"pay now or pay later"* decision-making processes.

%[https://www.youtube.com/watch?v=I3uH3iiiDqY&t=355s]

What I found since that time is that most "digital transformation" analytics projects are in-effect forensically reconstructing event sourcing from legacy operational systems, so that it could *then be **re-projected** into an analytic work product*. I make a passing reference to the inherent fallacy of "digital transformation" in my post about [agile patterns and practices](https://h3tech.io/how-agile-jumped-the-shark-into-a-zombie-apocalypse) and this is another facet of the same argument. Here again Greg Young articulates the problem space succinctly.

%[https://www.youtube.com/watch?v=I3uH3iiiDqY&t=3174s]

I don't want this article to preach the gospel of all things event sourced. There are plenty of those around the web. But it struck me that the folks who build event based systems and the folks who are consumed by byzantine analytics re-platforming ***never talk to each other*** because they're both busy solving similar problems, albeit for different reasons. So while Greg's keynote presentation was certainly educational on its own merits - it's also a message in a bottle to folks drowning in technical debt created by others (as I was) when trying to extract analytic value out of legacy operational systems that are fundamentally ill-suited to their task.

Toward the end of my tenure as a Microsoft Gold Partner consultant I had lunch with an exec that was trying to convince me to stay on a project. My argument was that "digital transformation" was a double lie, because it wasn't transforming *anything* - and was also a lie of omission because we were failing a duty to inform that client of the costs of maintaining the burden of that technical debt. I referred to it as "affirmative corporate gaslighting", a form of positive toxicity. His answer? It's not so much a lie as a fact that needs ample opportunity to become true. It was said with a wry smile and I laughed at the joke, but it definitely was a signal that I was in the wrong part of the technology business.

* [What The F# is Next (original)](/perspectives/WTFSIN_1)
  * [Warehouse Full of Cannibals](/perspectives/WTFSIN_1/warehouse_full_of_cannibals.md)
  * The Wrong Kind of DDD
  * [A More Functional Approach](/perspectives/WTFSIN_1/a_more_functional_approach.md)
  * [Machine Learning](/perspectives/WTFSIN_1/machine_learning.md)
  * [Success and Kinesthetic Learning](/perspectives/WTFSIN_1/success_and_kinesthetic_learning.md)
  * [Akka.NET, Actor Model and the Reactive Manifesto](/perspectives/WTFSIN_1/akka_and_the_reactive_manifesto.md)
  * [Other Learning Projects](/perspectives/WTFSIN_1/other_learning_projects.md)
  * [Coda - Microsoft, The Enterprise & The Open Source Balancing Act](/perspectives/WTFSIN_1/coda_open_source_balancing_act.md)