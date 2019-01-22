# Reaction Service

## Exposed Procedures

The Reaction micro-service exposes the following procedure:

`getReactionsByResources`

which recives an array of resource's ids and returns the amount of reactions they have (for each reaction type)

#### Input
``` javascript
string[]
```
#### Output
``` javascript
[
    {
        resource: string,
        types: {
            <reaction-type>: number
        }
    }
]
```

### Output Example

``` javascript
[
    {
        "resource": "123456789112345678911233",
        "types": {
            "LIKE": 5,
            "DISLIKE": 3
        }
    },
    {
        "resource": "123456789112345678911234",
        "types": {
            "DISLIKE": 4,
            "LIKE": 2
        }
    },
    {
        "resource": "123456789112345678911231",
        "types": {
            "LIKE": 1
        }
    },
    {
        "resource": "123456789112345678911232",
        "types": {
            "DISLIKE": 1,
            "LIKE": 2
        }
    }
]
```

