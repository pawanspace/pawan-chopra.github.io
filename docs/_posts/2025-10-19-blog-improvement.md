---
layout: post
title: "The Inverse Relationship Between Impact and Complexity"
date: 2025-10-19 19:16:44 -0700
categories: engineering complexity
---

I've noticed something strange: the lower the impact of a project, the more engineers over-engineer it.

And I'm guilty of this too.

I've seen projects where the traffic is tiny, maybe 2 transactions per second, and yet the code looks like it was designed for NASA. Every possible design pattern is in use: factories, builders, strategy, decorators… you name it. Unit tests cover 100% of the code, but integration tests and smoke tests, the ones that actually matter, are minimal. There's linting, formatting, style enforcement, all kinds of "best practices," and yet, the service delivers almost no real business value.

To be clear: I'm not talking about necessary complexity. Distributed systems are hard. Real-time processing is hard. I'm talking about the complexity we choose to add, the patterns, abstractions, and "best practices" that don't solve any actual problem.


Contrast that with high-stakes systems, Tier 1 services handling millions of requests per second, where failures can have serious consequences. In those cases, the code tends to be simpler, more direct. Sure, these systems have their own necessary complexity, distributed transactions, careful state management, complex monitoring. But you won't find design patterns for the sake of design patterns. End-to-end tests, load tests, canaries, everything that adds real value is there. But the unnecessary abstractions get cut ruthlessly. Engineers skip stylistic debates and fancy patterns because they don't help reliability or performance.


So why does this happen?

I think it's partly human psychology. In low-impact projects, there's no real risk. If something breaks, it won't hurt anyone. Engineers know this, consciously or not, so we compensate by creating complexity for ourselves, a kind of fake difficulty. Unit tests, patterns, endless abstractions, all give a sense of purpose, mastery, or "serious engineering," even if it doesn't improve the product. It feels safer to debate code style than to confront the fact that maybe the project itself doesn't matter much.

But it's not just individual engineers. Often, low-impact projects suffer from unclear requirements or vague product direction. When you don't know what success looks like, you fill the void with technical sophistication. It's easier to add another abstraction layer than to ask "should we even be building this?"

And let's be honest: our industry rewards this behavior. Complex architectures look impressive in design docs. A repo with 100% test coverage and strict linting feels "professional." We've created a culture where technical sophistication sometimes matters more than actual impact.

High-impact projects flip the script. Complexity stops being impressive and starts being dangerous. When millions depend on your code, clever abstraction becomes a liability. At 3 AM during an outage, you want boring code you can fix in your sleep.

We could even write it as a simple formula:

> **C = (k × M) / I**
>
> Where:
> - **C** = Code complexity
> - **I** = Real impact
> - **M** = Mindset intensity (desire to feel challenged or sophisticated)
> - **k** = Constant multiplier

When impact is low and mindset is high, complexity explodes. When impact is high, complexity collapses naturally to what's necessary.

Complexity is rarely about technical necessity. It's about human perception and organizational dysfunction. Next time you're tempted to add another pattern or chase 100% unit test coverage, pause: Am I adding real value, or just keeping myself busy? Sometimes the hardest question isn't "how should we build this?" but "should we build this at all?"

The best engineers I know don't chase patterns; they chase impact. Sometimes that means keeping things simple. Sometimes it means asking if the project should exist at all.
