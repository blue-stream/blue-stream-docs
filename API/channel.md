# Channel Service API

```javascript
IChannel {
    id: string (ObjectID);
    user: string;
    name: string;
    description: string;
}
```

## POST

### /api/channel/

Create a single channel

#### Request
``` javascript
{
    body: {
        user: string, // Change to req.user.id
        description: string,
    },
    headers: {
        Authorization: string // User token
    }
}
```
#### Response Body
``` javascript
{
    id: string (ObjectID),
    user: string,
    name: string,
    description: string,
    createdAt: string (Date),
    updatedAt: string (Date)
}
```

## PUT

### /api/channel/:id

Update a channel using it's id

#### Request
``` javascript
{
    params: {
        id: string
    },
    body: {
        name: string,
        description: string
    }
}
```
#### Response Body
``` javascript
{
    id: string (ObjectID),
    user: string,
    name: string,
    description: string,
    createdAt: string (Date),
    updatedAt: string (Date)
}
```

## DELETE

### /api/channel/:id

Delete a single channel

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
    id: string (ObjectID),
    user: string,
    name: string,
    description: string,
    createdAt: string (Date),
    updatedAt: string (Date)
}
```

## GET

### /api/channel/:id

Get a single channel by it's id

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
    id: string (ObjectID),
    user: string,
    name: string,
    description: string,
    createdAt: string (Date),
    updatedAt: string (Date)
}
```

### /api/channel/many

Get array of channels

#### Request
``` javascript
{
    query: {
        user?: string,
        name?: string,
        description?: string,
        startIndex?: number,
        endIndex?: number,
        sortOrder?: '' | '-',
        sortBy?: 'name' | 'description' | 'user'
    }
    
}
```
#### Response
``` javascript
{
    [
        {
            id: string (ObjectID),
            user: string,
            name: string,
            description: string,
            createdAt: string (Date),
            updatedAt: string (Date)
        }
    ]
}
```

### /api/channel/amount

Get amount of channels.

#### Request
``` javascript
{
    query: {
        user?: string,
        name?: string,
        description?: string,
    }
}
```
#### Response Body
``` javascript
number
```