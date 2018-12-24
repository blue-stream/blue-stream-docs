# Channel Service

## Publish

Channel Service routing key structure: `channelService.channel.{action-name}.{action-status}`

The Channel micro-service can publish the following messages to RabbitMQ:

### Remove Succeeded

Published after a channel was succeessfully removed.

Routing key:  `channelService.channel.remove.succeeded`

#### Message body
```javascript
{
    id: string, // channel id
}
```