# GET /histories

Endpoint used to retrieve the date and time for each integration. It is basically a new collection in the mongo that contains the timestamp of the integrations made by the cron or the endpoint.

## Request

`curl -X GET "http://localhost:3000/histories"`

### Success

#### HTTP Status

200

#### Body

```json
{
    "timestamps": [
        "2020-02-03 08:00:00",
        "2020-02-03 09:36:23"
    ]
}
```

### Internal Server Error

#### HTTP Status

500

#### Body

Internal Error.
