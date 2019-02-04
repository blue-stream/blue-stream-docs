# Classification Mocks

<small><b>All requests needs to have classification JWT in header</b></small>

## GET

### /classificationservice/api/classifications

Get all classifications

#### Response JSON
``` javascript
{
    [
        {
            "id": number,
            "name": string
        }
    ]
}
```

### /classificationservice/api/sources

Get all sources

#### Response JSON
``` javascript
{
    [
        {
            "id": number,
            "name": string,
            "Classification": number, // 0-11
            "LinkedClassificationId": number,
            "Layer": number // 0-4
        }
    ]
}
```

### /classificationservice/api/pps

Get all pps

#### Response JSON
``` javascript
{
    [
        {
            "id": number,
            "name": string,
            "type": string // a or b
        }
    ]
}
```

### /classificationservice/api/userPermissions

Get user permissions

#### Request
``` javascript
{
    query: {
        userName: string
    },
    headers: {
        Authorization: string // Classification JWT
    }
}
```

#### Response JSON
``` javascript
{
    "classification": number,
    "classificationsAllow": 
    [
        {
            "classificationId": number,
            "classificationLayer": number
        }
    ],
    "ppAllow": 
    [
        {
            "ppId": number,
            "ppType": string
        }
    ],
    "displayName": string
}
```