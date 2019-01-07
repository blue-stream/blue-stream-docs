# Video Service API

``` javascript
    VideoStatus = 'UPLOADED' | 'PENDING' | 'FAILED' | 'READY';
```

## GET

### /api/video

Get all videos <b>(DEPRECATED - <small>will be replaced with <code>`/api/popular`</code></small>)</b>

#### Request
``` javascript
{
    query: {
        id?: string,
        title?: string,
        description?: string,
        owner?: string,
        status?: VideoStatus
    }
}
```

#### Response
``` javascript
[
    {
        id: string (ObjectID)
        status: VideoStatus,
        tags: string[],
        published: boolean,
        title: string,
        owner: string,
        createdAt: string (Date),
        updatedAt: string (Date),
        thumbnailPath?: string,
        contentPath?: string,
        previewPath?: string,
        originalPath?: string
    }
]
```

### /api/video/:id

Get video by id

#### Request
``` javascript
{
    params: {
        id: string
    }
}
```

#### Response Body
``` javascript
{
    id: string (ObjectID)
    status: VideoStatus,
    tags: string[],
    published: boolean,
    title: string,
    owner: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    thumbnailPath?: string,
    contentPath?: string,
    previewPath?: string,
    originalPath?: string
}
```

### /api/video/one

Get single video by filter

#### Response Body
``` javascript
{
    query: {
        id?: string,
        title?: string,
        description?: string,
        owner?: string,
        status?: VideoStatus
    }
}
```

#### Response
``` javascript
{
    id: string (ObjectID)
    status: VideoStatus,
    tags: string[],
    published: boolean,
    title: string,
    owner: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    thumbnailPath?: string,
    contentPath?: string,
    previewPath?: string,
    originalPath?: string
}
```

### /api/view/

Get user's viewed videos

### Request
``` javascript
{
    headers: {
        authorization: string // Contains user's jwt
    }
}
```

### Response Body
``` javascript
string[]
```

## POST

### /api/video

Create a video document

#### Request
``` javascript
{
    body: {
	    title: string
    }
}
```

#### Response Body
``` javascript
{
    id: string (ObjectID)
    status: VideoStatus,
    tags: string[],
    published: boolean,
    title: string,
    owner: string,
    createdAt: string (Date),
    updatedAt: string (Date),
}
```

### /api/view/:video

Increases video's `view`s amount.
User can increase `view` of video every 15 minutes (can be changed in configuration file)

#### Request
``` javascript
{
    params: {
        video: string (ObjectId)
    },
    headers: {
        authorization: string // required
    }
}
```

#### Response Status
200 - (Empty body)


## PUT 

### /api/video/:id

Update a single video document

#### Request 
``` javascript
{
    params: {
        id: string
    },
    body: {
        title?: string,
        description?: string,
        tags?: string[],
        published?: boolean
    }
}
```

#### Response Body
``` javascript
{
    id: string (ObjectID)
    status: VideoStatus,
    tags: string[],
    published: boolean,
    title: string,
    owner: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    thumbnailPath?: string,
    contentPath?: string,
    previewPath?: string,
    originalPath?: string
}
```

## DELETE

### /api/video/:id

Delete a <strong>single</strong> video document by id

#### Request
``` javascript
{
    params: {
        id: string
    }
}
```

#### Response 
``` javascript
{
    id: string (ObjectID)
    status: VideoStatus,
    tags: string[],
    published: boolean,
    title: string,
    owner: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    thumbnailPath?: string,
    contentPath?: string,
    previewPath?: string,
    originalPath?: string
}
```