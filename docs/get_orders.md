# GET /orders

Endpoint that returns a list of json objects with the data grouped by day of the order and its total value.

## Request

`curl -X GET "http://localhost:3000/orders"`

### Success

#### HTTP Status

200

#### Body

```json
[
    {
        "date": "2021-02-03",
        "totalAmount": "10000"
    }
]
```

### Internal Server Error

#### HTTP Status

500

#### Body

Internal Error.
