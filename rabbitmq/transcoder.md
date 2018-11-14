# Transcoder

## Transcode

### Transcode succeeded
Published by the `transcoder` microservice after video is succeessfully transcoded.

#### Event
The published event will be called `transcoder.video.transcode.succeeded`

#### Event body
``` javascript
{
    id: string, // document id from db
    contentPath: string, // trancoded mp4 video(81850287.mp4)
    thumbnailPath: string, // thumbnail of the video(81850287.png)
    previewPath: string, // preview of the video(81850287.gif)
}
```

### Transcode failed
Published by the `transcoder` microservice after video is failed transcoding.

#### Event
The published event will be called `transcoder.video.transcode.failed`

#### Event body
``` javascript
{
    id: string, // document id from db
    key: string, // video unique key from object-storage (81850287.mp4)
}
```
