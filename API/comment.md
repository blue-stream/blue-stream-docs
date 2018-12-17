# Comment Service API

## POST

### /api/comment/

Create a single comment

#### Request
``` javascript
{
    body: {
        resource: string,
        parent?: string,
        text: string,
        user: string
    }
}
```
#### Response Body
``` javascript
{
    parent: string | null,
    resource: string,
    text: string,
    user: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    id: string (ObjectID)
}
```

## PUT

### /api/comment/:id

Update comment's text using it's id

#### Request
``` javascript
{
    params: {
        id: string
    },
    body: {
        text: string
    }
}
```
#### Response Body
``` javascript
{
    parent: string | null,
    resource: string,
    text: string,
    user: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    id: string (ObjectID)
}
```

## DELETE

### /api/comment/:id

Delete a single comment

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
    parent: string | null,
    resource: string,
    text: string,
    user: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    id: string (ObjectID)
}
```

## GET

### /api/comment/:id

Get a single comment by it's id

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
    parent: string | null,
    resource: string,
    text: string,
    user: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    id: string (ObjectID)
}
```

### /api/comment/one

Get a specific comment by providing a comment filter (Partial<Comment>).

#### Request
``` javascript
{
    query: {
        resource?: string,
        parent?: string,
        text?: string,
        user?: string
    }
}
```
#### Response Body
``` javascript
{
    parent: string | null,
    resource: string,
    text: string,
    user: string,
    createdAt: string (Date),
    updatedAt: string (Date),
    id: string (ObjectID)
}
```

### /api/comment/many

Get array of comments

#### Request
``` javascript
{
    query: {
        resource?: string,
        resourceType?: ResourceType,
        type?: commentType,
        user?: string,
        startIndex?: number,
        endIndex?: number
    }
    
}
```
#### Response
``` javascript
{
    [
        {
            parent: string | null,
            resource: string,
            text: string,
            user: string,
            createdAt: string (Date),
            updatedAt: string (Date),
            id: string (ObjectID)
        }
    ]
}
```

### /api/comment/amount

Get amount of comments.

#### Request
``` javascript
{
    query: {
        resource?: string,
        parent?: string,
        text?: string,
        user?: string
    }
}
```
#### Response Body
``` javascript
number
```

### /api/comment/:parent/replies

Get replies of a specific comment by it's id

#### Request
``` javascript
{
    params: {
        parent: string (ObjectID)
    }
}
```
#### Response
``` javascript
{
    [
        {
            parent: string,
            resource: string,
            text: string,
            user: string,
            createdAt: string (Date),
            updatedAt: string (Date),
            id: string (ObjectID),
            repliesAmount: number
        }
    ]
}
```


### /api/comment/root

Get array of root comments (comment's without a parent) of a specific resource

#### Request
``` javascript
{
    query: {
        resource: string,
        startIndex?: number,
        endIndex?: number
    }
}
```
#### Response
``` javascript
{
    [
        {
            parent: null,
            resource: string,
            text: string,
            user: string,
            createdAt: string (Date),
            updatedAt: string (Date),
            id: string (ObjectID)
        }
    ]
}
```