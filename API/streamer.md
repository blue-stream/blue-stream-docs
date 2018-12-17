# Streamer Service API

## GET

### /api/streamer/video/:path

Stream the whole video or a chunk of it (according to header) from S3 object storage

#### Request Parameters
Video file name stored in S3 with .mp4 suffix
``` javascript
    path: String
```

#### Request Header
``` javascript
    Range?: 'bytes=<start_byte>-<end_byte>'
```
<br />

The response is the actual video (mp4 format) or a chunk of it with the header:

#### Response Header
``` javascript
    Content-Type: 'video/mp4'
    Content-Length: '<video_size/chunk_size>'
    content-range?: 'bytes <start_byte>-<end_byte>'
```
#### Response
``` javascript
    videoFile.mp4
```
 <br />

### /api/streamer/thumbnail/:path

Get thumbnail of video (.png image) from S3 object storage

#### Request Parameters
Thumbnail file name stored in S3 with .png suffix
``` javascript
    path: String
```
 <br />
The response is the actual thumbnail (png format)

#### Response
``` javascript
    thumbnailFile.png
```
 <br />

### /api/streamer/preview/:path

Get preview of video (.gif file) from S3 object storage

#### Request Parameters
Preview file name stored in S3 with .gif suffix
``` javascript
    path: String
```
 <br />
The response is the actual preview (gif format)

#### Response
``` javascript
    previewFile.gif
```