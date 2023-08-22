---
title: Akka.NET, Actor Model and the Reactive Manifesto
weight: 6
tags:
- Petabridge
---

## Akka.NET, Actor Model and the Reactive Manifesto

This is where I'll catch some flack from both mathematicians and  computer scientists. But my personal opinion is that serverless apps - both stateless and *durable* functions - are really a rehash of the actor model, which has been around for decades. I had some early brushes with the concept while in school, but it really sunk in when I started looking for ways to make operational systems more elastic and reactive. It turns out that I'm not alone in this, and actor model in Akka.NET (the name being an approved homage to the original Akka implementation) brings event-driven systems shoulder-to-shoulder with event sourced architectures. To many software engineers event *driven* and event *sourced* are distinct from one another, so it's worthwhile to consider each on their own before you find where they might overlap in a given domain.

Here is a clip from a presentation by Aaron Stannard, co-creator of Akka.NET and CTO of [Petabridge](https://Petabridge.com/). They cover a few highlights of the Akka.NET actor system.

%[https://www.youtube.com/watch?v=ozelpjr9SXE&t=1204s]

Actor systems are a form of orchestrated ephemeral compute that can very efficiently create a cohesive reactive application surface. There are many of these systems showing up across tech stacks well beyond public cloud serverless planes or Akka and Akka.NET. The [reactive manifesto](https://www.reactivemanifesto.org/) was authored in 2014 and serves as a common point of departure for many, and from my perspective is at least partly responsible for the renewed interest in the actor pattern. I count myself as both early *and* late to this party. Given [the dilution that has undercut the agile manifesto](https://h3tech.io/how-agile-jumped-the-shark-into-a-zombie-apocalypse), I'll be curious to see how ***this*** manifesto ages. While I think that in some ways it doesn't go far enough, I added my signature to show solidarity with its most high-minded goals.

The part of Akka.NET that really has my attention is that Petabridge has provided [an entire site on learning how to implement Akka.NET step-by-step](https://Petabridge.com/bootcamp/), and it's ***free***. I'm definitely adding that site to my list of online learning resources. While it's written in and around C#, I'm looking forward to embracing and bring over Scott Wlaschin's "railway" pattern in F#. I had a sense I would need to maintain and even sharpen my C# chops if I was going dive into F# with increased momentum. From early on I had a sense that leaning on R would only get me so far down the road, but this new ground is exciting.

## Beyond Reactive with Wilderness Labs & Xamarin

I lump mobile apps and IoT with automotive telematics because they're all compute at the edge receiving and producing data in exchange with a remote backplane. I also mention them here because the ***same*** folks who created [Wilderness Labs](https://www.wildernesslabs.co/), a .NET embedded IoT solution, also created the original [Xamarin](https://dotnet.microsoft.com/apps/xamarin) framework, a cross-platform stack targeting apps for Android, iOS and beyond. I'm working on a Meadow F7 custom sensor driver that's part of a stealth project. But Wilderness Labs just released an update that included an F# project template and direct .NET Standard 2.1 support. So expect more on this, as it will be a showcase on how F# can support a variety of applications, even microcontroller workloads.

![meadow-project.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1659494034118/vpmcClf_z.jpg align="left")

* [What The F# is Next (original)](/perspectives/WTFSIN_1)
  * [Warehouse Full of Cannibals](/perspectives/WTFSIN_1/warehouse_full_of_cannibals.md)
  * [The Wrong Kind of DDD](/perspectives/WTFSIN_1/the_wrong_kind_of_DDD.md)
  * [A More Functional Approach](/perspectives/WTFSIN_1/a_more_functional_approach.md)
  * [Machine Learning](/perspectives/WTFSIN_1/machine_learning.md)
  * [Success and Kinesthetic Learning](/perspectives/WTFSIN_1/success_and_kinesthetic_learning.md)
  * Akka.NET, Actor Model and the Reactive Manifesto
  * [Other Learning Projects](/perspectives/WTFSIN_1/other_learning_projects.md)
  * [Coda - Microsoft, The Enterprise & The Open Source Balancing Act](/perspectives/WTFSIN_1/coda_open_source_balancing_act.md)
