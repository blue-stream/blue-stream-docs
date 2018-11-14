# Video Service

## Call transcoding service

### Event
Routing key of the event will be `videoService.video.upload.succeeded`

### Event body
```javascript
{
    id: string, // document id from db
    key: string // video unique key from object-storage
}
```
