# User Service API

## POST

### /api/user/

Create a single user

#### Request
``` javascript
{
    body: {
        id: string, // Unique
        firstname: string,
        lastName: string,
        mail: string
    },
    headers: {
        Authorization: string // JWT token
    }
}
```
#### Response Body
``` javascript
{
    _id: string,
    id: string,
    firstname: string,
    lastName: string,
    name: string,
    mail: string,
    createdAt: string (Date),
    updatedAt: string (Date)
}
```

## PUT

### /api/user/:id

Update a single user

#### Request
``` javascript
{
    query: {
        id: string
    },
    body: {
        firstname?: string,
        lastName?: string,
        mail?: string
    },
    headers: {
        Authorization: string // JWT token
    }
}
```
#### Response Body
``` javascript
{
    _id: string,
    id: string,
    firstname: string,
    lastName: string,
    name: string,
    mail: string,
    createdAt: string (Date),
    updatedAt: string (Date)
}
```

## GET

### /api/user/:id

Get a single user

#### Request
``` javascript
{
    query: {
        id: string
    },
    headers: {
        Authorization: string // JWT token
    }
}
```
#### Response Body
``` javascript
{
    _id: string,
    id: string,
    firstname: string,
    lastName: string,
    name: string,
    mail: string,
    createdAt: string (Date),
    updatedAt: string (Date)
}
```

### /api/user/many

Get array of users

#### Request
``` javascript
{
    query: {
        firstName?: string,
        lastName?: ResourceType,
        mail?: ReactionType,
        startIndex?: number,
        endIndex?: number,
        sortOrder?: string,
        sortBy?: string
    }
    
}
```
#### Response
``` javascript
{
    [
        {
            _id: string,
            id: string,
            firstname: string,
            lastName: string,
            name: string,
            mail: string,
            createdAt: string (Date),
            updatedAt: string (Date)
        }
    ]
}
```

### /api/user/amount

Get amount of users.

#### Request
``` javascript
{
    query: {
        firstName?: string,
        lastName?: ResourceType,
        mail?: ReactionType,
        startIndex?: number,
        endIndex?: number,
        sortOrder?: string,
        sortBy?: string
    }
}
```
#### Response Body
``` javascript
number
```