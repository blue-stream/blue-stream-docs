# Video Service

## Publish

### Upload Succeeded

Published after a video was succeessfully uploaded.

Routing key:  `videoService.video.upload.succeeded`

#### Message body
```javascript
{
    id: string, // document id from db
    key: string // video unique key from object-storage
}
```

### Remove Succeeded

Published after a video was succeessfully removed.

Routing key: `videoService.video.remove.succeeded`

#### Message body
``` javascript
{
    id: string, // id of removed video
}
```
