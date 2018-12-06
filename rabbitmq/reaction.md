# Reaction Service

## Subscribe

The Reaction micro-service subscribes to the following queue: `reaction-action-queue`

with the following routing keys: 
`videoService.video.remove.succeeded`
`commentService.comment.remove.succeeded`

and the following messages:

#### Message body
``` javascript
{
    id: string, // id of removed resource
}
```
#### Message body
``` javascript
{
    ids: string[], // ids of removed resources
}
```

