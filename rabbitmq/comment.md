# Comment Service

Comment Service routing key structure: `commentService.comment.{action-name}.{action-status}`

The Comment micro-service can publish the following messages to RabbitMQ:

## Remove Succeeded

Published after a comment was succeessfully removed.

Routing key: `commentService.comment.remove.succeeded`

#### Message body
``` javascript
{
    id: string, // document id from db
}
```