# Actors can rule your DDD world by [Hannes Lowette](https://twitter.com/hannes_lowette)
When developers learn about DDD, they tend to find a way to work the principles into their codebase. After a while, they may end up with some form of event sourcing or CQRS. 

But often times, the possibilities of using an `actor model`, such as `Akka.NET`, are overlooked.

In this talk I will show you to all the things you need to know if you want to build such a system using .NET 6 and Akka.NET. Expect to see a lot of code!

An elementary knowledge of DDD principles is required to attend this session.

## Domain Driven Design
![Actor System](img/actors-in-ddd/ddd-nutshell.jpg)

## Sending beer is tricky
- What I want :
   - CQRS / ES
   - Clean aggregate
   - `Human readable tests`
- Akka.NET

![Actor System](img/actors-in-ddd/actor1.png)
![The Actor](img/actors-in-ddd/1.JPG)
- Guaranteed single thread
    - 1 thread per Actor

![The Actor system](img/actors-in-ddd/2.JPG)
![The Actor system in code](img/actors-in-ddd/3.JPG)

## Actors
- Actor hierarchy
   - Parent Actor
      -  Creating children
   - Supervision
      -  Action : Resume / Stop / Start / Escalate
      -  Strategy : OneforOne / OneforAll

![Actor System](img/actors-in-ddd/actor2.png)

## Aggregates and Actors
![The Actor system in code](img/actors-in-ddd/6.JPG)

- Aggregate Actor
   - Wrap aggregate in Actor
   - AggregateActor
- How our actors will be structured ?
   - `Aggregate manager`
      -  Takes connect req
      -  Creates aggregate actors if needed
      -  Uses Sender to send an IActorRef back
      -  1 aggregate actor per instance
   - `Command router`
      -  Takes in command
      -  Connects to agg
      -  Caches agg IActorRef
      -  Relays commands to Agg
      -  May become a bottleneck
   - `Projectors`
      -  Created at startup
      -  Subscribes to the Event Bus
      -  Updates the Read Storage (outside the ActorSystem)
      -  1 projector pet type 
   - Fold the event stream
      -  Created at startup
      -  Subscribes to the Event Bus
      -  Relays events to agg
      -  Events from other agg or outside systems
- Command Router
   - More actor than it can handle = problem
   - Pools / Groups
   - Routing strategy

## Persistence
![The Actor system](img/actors-in-ddd/4.JPG)
- Akka.persistence
   - Event source by default
   - Inherits from `ReceivePersistentActor`
   - Snapshot comes for free

## Pub / Sub
![The Actor system](img/actors-in-ddd/5.JPG)
- Internal Event Stream

## Clean Tests
![The Actor system](img/actors-in-ddd/7.JPG)


## Resources
![learning](img/actors-in-ddd/learning.jpg)


- AKKA .NET : https://getakka.net/
- Repo bootcamp : https://github.com/petabridge/akka-bootcamp
- Akka vs Orleans :https://github.com/akka/akka-meta/blob/master/ComparisonWithOrleans.md