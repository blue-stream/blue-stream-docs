# Comment Service

## Publish

Comment Service routing key structure: `commentService.comment.{action-name}.{action-status}`

The Comment micro-service can publish the following messages to RabbitMQ:

### Remove Succeeded

Published after a comment was succeessfully removed.

Routing key: `commentService.comment.remove.succeeded`

#### Message body
``` javascript
{
    ids: string[], // ids of removed comments
}
```

## Subscribe

The Comment micro-service subscribes to the following queue: `comment-action-queue`

with the following routing key: `videoService.video.remove.succeeded`

and expects the following message:

#### Message body
``` javascript
{
    id: string, // id of removed video
}
```

