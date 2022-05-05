# Event Sourcing - what could possibly go wrong? by [Andrzej Ludwikowski](https://twitter.com/aludwikowski)
Yet another presentation about Event Sourcing? Yes and no. Event Sourcing is a really great concept. Some could say it’s a Holy Grail of the software architecture.

![What is ES ?](img/es-go-wrong/1.png)
![Why ES ?](img/es-go-wrong/2.png)
![ES & CQRS level 1](img/es-go-wrong/3.png)
![ES & CQRS level 1 pros and cons](img/es-go-wrong/4.png)
![ES & CQRS level 2](img/es-go-wrong/5.png)
![ES & CQRS level 2 pros and cons](img/es-go-wrong/6.png)
![ES & CQRS level 3](img/es-go-wrong/7.png)
![ES & CQRS level 3 pros and cons](img/es-go-wrong/8.png)
![Alternatives](img/es-go-wrong/9.png)
![application](img/es-go-wrong/10.png)
![domain](img/es-go-wrong/11.png)
![domain](img/es-go-wrong/12.png)
![domain](img/es-go-wrong/13.png)

- Carefully choose ES lib/framework
    - Take your time to POC and make your choice
- Think about serialization / deserialization
- There is no perfect database for event sourcing
- Understand event/command/state schema evolution
- Eventual consistency is your friend
    - Understand deeply what is it
    - How it can help you achieve your objectives

![domain](img/es-go-wrong/14.png)
- Orchestration vs Choreography

## Resources
- Slides : https://www.slideshare.net/AndrzejLudwikowski/event-sourcing-what-could-possibly-go-wrong-devoxx-pl-2021