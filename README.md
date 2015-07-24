The World Wide Hack
-------------------

The World Wide Hack is an effort to re-imagine the craft of programming, with
inspiration from Bret Victor's [Learnable Programming](http://worrydream.com/LearnableProgramming/) and
with a focus on immediate feedback and frictionless collaboration.

Programming has become an extremely social activity. Environments like GitHub and Stack Exchange, 
woven together by Google, give us instant access to open-source libraries, sample code, and
discussions of techniques and problems.

Our tools have not kept up. Google is still our main portal to this social world. Most programmers,
if they are breaking new ground for themselves at all, use Google almost as heavily as they use
their IDEs or text editors. They Google constantly for libraries, API documentation, suggested 
approaches, and problem resolutions. But every search is a dumb text search, divorced from the
programmer's context. The programmer tosses in keywords to provide a little context -- the language
they are working in, the main package name that might be relevant, and so on. The search results
are workable because of Google's powerful general-purpose ranking, but they only tangentially 
attack the programmer's true goal: how would today's best programmers accomplish X in my language
and my immediate coding environment?

The idea of the World Wide Hack is to embrace the fact that constant reuse of code, techniques,
and problem resolutions has become the main point. Our editing environment should apply Bret 
Victor's ideas about "creating by reacting" and "recomposition" by automatically pulling in 
open-source code examples that meet the developer's needs, much as chess software pulls
in examples of public games that proceeded from the current position. The development environment 
will find or generate code to meet the developer's needs, much as chess software shows potential 
lines of play and their likely outcomes. For example, there might be a simple gesture that the 
developer uses in the context of their source code to search the open-source world for a suitable 
package, class, method, function, or code snippet for a particular purpose. We call this "Code Mining".
(For implementation direction, see the [codemining](https://github.com/WorldWideHack/codemining) repo.)

An Organizing Framework
-----------------------

As an organizing framework, we view software development as a collaborative search 
through the space of useful software components by people and machines who take on the following five roles:

- *Principal*: the primary author of a particular set of software components.

- *Peer*: creates software and information for his own purposes, but that may be useful to the
   Principal. (A Peer acts as a Principal from the perspective of his own projects.)

- *Freelancer*: assists the Principal in a "work for hire" capacity, such as by coding to a spec or
   generating test cases. (A Freelancer acts as a Principal from the perspective of the tasks that
   he takes on.)

- *Random*: a member of the crowd, which takes on tasks such as certain kinds of testing that do not
   require the attention of a Principal.

- *Machine Assistant* (MA): a software component that takes on tasks such as coding to a spec or
   generating test cases.

We want to extend existing and future development environments to facilitate each of these five
roles and the flow among them. The goal is a seamless interplay across creation, discovery, and
validation, and among highly skilled Principals, relatively unskilled Randoms, and sophisticated but
mechanical MAs.

For example, a Principal needs a UI component for creating a to-do item. She begins writing some
high-level documentation for this component. An MA integrated into her development environment
suggests an open source component (written by a Peer) with documentation textually similar to what
the Principal has written so far, and with quality scores and open-source license that meet the
Principal's filters. The Principal examines the open source component and decides that although it
doesn't perfectly fit her needs, it is a good starting point. She clones the component, edits its
documentation to describe a variation that she wants, flags it as needing assistance with 3
assistance value points, and moves on to something else. (She doesn't change the 12-hour deadline
that she uses as her default for assistance.)

A Freelancer who has worked with the original component before and who meets the Principal's
freelance reputation filter (and whose principal reputation filter was met by the Principal), is
alerted to this request. He checks the fee for the work (which was computed automatically from the
Principal's monthly budget, her assistance-value-point velocity, and the value points that she
assigned to this task) and decides it is worth his while. He claims the assistance flag. (This
Principal pays cash and this Freelancer prefers cash. Most work-for-hire deals are done in-kind on
WWH credits.)

The Freelancer creates a new version of the component that he believes matches its new
documentation, adds some entries to the new version's human-testing plan, and releases the
assistance flag. An MA notices that both the component and the human-testing plan have been
modified since the component was last tested, that the component has an unclaimed assistance flag,
and that the Principal has a cash budget. It creates a set of crowd-sourcing tasks to test the
modified component against the modified human-testing plan. These tasks are carried out by Randoms,
with multiple Randoms being assigned the same testing tasks so that the results can be
cross-checked. The level of redundancy depends on the reputations of the Randoms who do the work.

The Principal is alerted that the modified component is ready for her review. She examines the
diffs from the original, the updates to the human-testing plan, and the summarized test reports from
the Randoms. She accepts the work, which is then incorporated into her project. This triggers
payments to the Freelancer and the Randoms.

The Peer who created the original version of the component is alerted that a new version has been
implemented and tested. He sees that the Principal's open-source license allows him to incorporate
the changes, and he likes them, so he incorporates them into his own version.

Capabilities Neeeded
--------------------

Over time, the following capabilities will be needed to support the World Wide Hack:

environment, data, and workflow needed to support the World Wide Hack:

- Reputation management and quality scoring.
- Freelancing and crowd-sourcing.
- Micropayments.
- API contracts and testing.
- Publishing, versioning, and dependency management.
- Open-source license management.
- Searching for components and functions that work in a particular context.
- Development-mode capture and playback of component and function inputs and outputs.

The idea is to build these as open APIs supporting multiple languages, promoting the integration of those APIs into as many IDEs as feasible.

License
-------

All artifacts in this "manifesto" project (whether so marked or not) are Copyright (c) Dean Thompson and
MIT licensed.

History
-------
For background on the thought history of the World Wide Hack, and possibly some related ideas to
resurrect, see the [Cy repo](https://github.com/Cy-Hub/Cy).
