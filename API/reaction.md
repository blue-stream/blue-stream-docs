# Reaction Service API

``` javascript
ResourceType = 'COMMENT' | 'VIDEO';
ReactionType = 'LIKE' | 'DISLIKE';
```

## POST

### /api/reaction/

Create a single reaction

#### Request
``` javascript
{
    body: {
        resource: string,
        resourceType: ResourceType,
        type: ReactionType,
        user: string
    }
}
```
#### Response Body
``` javascript
{
    _id: string,
    resourceType: ResourceType,
    user: string,
    resource: string,
    type: ReactionType,
    updatedAt: string
}
```

## PUT

### /api/reaction/

Update a single reaction

#### Request
``` javascript
{
    query: {
        resource: string,
        user: string
    },
    body: {
        type: ReactionType
    }
}
```
#### Response Body
``` javascript
{
    _id: string,
    resourceType: ResourceType,
    user: string,
    resource: string,
    type: ReactionType,
    updatedAt: string
}
```

## DELETE

### /api/reaction/

Update a single reaction

#### Request
``` javascript
{
    query: {
        resource: string,
        user: string
    },
}
```

#### Response Body
``` javascript
boolean
```


## GET

### /api/reaction/one

Get a specific reaction by providing a resource and a user.

#### Request
``` javascript
{
    query: {
        resource: string,
        resourceType: ResourceType
    }
}
```
#### Response Body
``` javascript
{
    _id: string,
    resourceType: ResourceType,
    user: string,
    resource: string,
    type: ReactionType,
    updatedAt: string
}
```

### /api/reaction/many

Get array of reactions

#### Request
``` javascript
{
    query: {
        resource?: string,
        resourceType?: ResourceType,
        type?: ReactionType,
        user?: string
    }
    
}
```
#### Response
``` javascript
{
    [
        {
            _id: string,
            resourceType: ResourceType,
            user: string,
            resource: string,
            type: ReactionType,
            updatedAt: string
        }
    ]
}
```

### /api/reaction/amount

Get amount of reactions.

#### Request
``` javascript
{
    query: {
        resource?: string,
        resourceType?: ResourceType,
        type?: ReactionType,
        user?: string
    }
}
```
#### Response Body
``` javascript
number
```

### /api/reaction/:resource/amount

Get an array of {type, amount} that represents the amount of each type of reaction a specific resource has.

#### Request
``` javascript
{
    params: {
        resource: string
    }
}
```
#### Response
``` javascript
{
    [
        {
            type: ReactionType,
            amount: number
        }
    ]
}
```

