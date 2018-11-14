# Uploader

Uploader routing key structure: `uploader.video.{action-name}.{action-status}`

The Uploader micro-service can publish the following messages to RabbitMQ:

## Upload Succeeded

Published after a video was succeessfully uploaded to the defined storage.

Routing key: `uploader.video.upload.succeeded`

#### Message body
``` javascript
{
    id: string, // document id from db
    key: string, // video's unique key (Including file type)
}
```

## Upload Failed
Published after a video has failed to be uploaded to the defined storage.

Routing key: `uploader.video.upload.failed`

### Message body
``` javascript
{
    id: string, // document id from db
}
```

## Upload Canceled
Published after a user have canceled the upload of a video to the defined storage.

Routing key: `uploader.video.upload.canceled`

### Message body
``` javascript
{
    id: string, // document id from db
}
```