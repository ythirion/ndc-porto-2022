# Managing Event Driven Architectures by [Ian Cooper](https://twitter.com/ICooper)
You should be careful what you wish for. Once you have succeeded in persuading your team to adopt an event-driven architecture for communication between your microservices, you hit the problem of how to manage that event-driven architecture.

![agenda](img/managing-event-driven-architectures/1.png)
![Endpoints](img/managing-event-driven-architectures/2.png)
![Bounded Context](img/managing-event-driven-architectures/3.png)
![Async Endpoints](img/managing-event-driven-architectures/4.png)
![Document the contract](img/managing-event-driven-architectures/5.png)
![Async API](img/managing-event-driven-architectures/6.png)
![Document structure](img/managing-event-driven-architectures/8.png)

- Example :
```yaml 
asyncapi: '2.2.0'
info:
  title: Account Service
  version: 1.0.0
  description: This service is in charge of processing user signups
channels:
  user/signedup:
    subscribe:
      message:
        $ref: '#/components/messages/UserSignedUp'
components:
  messages:
    UserSignedUp:
      payload:
        type: object
        properties:
          displayName:
            type: string
            description: Name of the user
          email:
            type: string
            format: email
            description: Email of the user
```

![async api result](img/managing-event-driven-architectures/13.png)

## Developer catalog @spotify
![spotify backstage](img/managing-event-driven-architectures/backstage1.png)
![spotify backstage](img/managing-event-driven-architectures/backstage2.png)
![spotify backstage](img/managing-event-driven-architectures/plugins.png)


![cupid](img/managing-event-driven-architectures/11.png)
![event catalog](img/managing-event-driven-architectures/12.png)

## Resources
- Brighter : https://www.goparamore.io/
- AsyncApi : https://www.asyncapi.com/
- Backstage : https://backstage.io/
- CloudEvents : https://cloudevents.io/
- EventCatalog : https://github.com/boyney123/eventcatalog