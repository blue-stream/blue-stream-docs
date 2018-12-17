# Video Service API

## POST

### /api/upload/

Upload a single video

#### Request
``` javascript
{
    videoFile: File
}
```

The response is the key (name of file in storage) of the video with the file type at the end
#### Response Body
``` javascript
{
    string
}
```