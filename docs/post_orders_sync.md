# POST /orders/sync

Endpoint used to synchronize the Pipedrive and Bling platforms. In case of success, an API can return two types of response.
Whether or not new orders were created.

## Request

`curl -X POST "http://localhost:3000/orders/sync"`

### Success

#### HTTP Status

200

#### Body

- Sync complete! New orders have been created.
- Sync complete! No orders were created.

### Internal Server Error

#### HTTP Status

500

#### Body

Internal Error.
