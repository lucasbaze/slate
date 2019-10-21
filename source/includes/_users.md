# Users

The users endpoints are for users of a company but NOT the admins.

## GET User Info

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

> Example Response

```json
{
    "company_ID": 2,
    "name": "Amanda Lane",
    "email": "amanda@lambdaschool.com",
    "snacks": [
        {
            "name": "Smokehouse Almonds",
            "brand": "Blue Diamond",
            "uom": "16 oz bag",
            "img_url": "https://www.riteaid.com/shop/media/catalog/product/cache/1/image/9df78eab33525d08d6e5fb8d27136e95/0/4/041570030837.jpg"
        },
        {
            "name": "Original Skittles",
            "brand": "Wrigley",
            "uom": "54 oz bag",
            "img_url": "https://images-na.ssl-images-amazon.com/images/I/71dHUI2QzEL._SX425_.jpg"
        }
    ]
}
```

### Endpoint

`GET /users/{user_ID}`

### URL Parameters

| Property | Required  | Description                   |
| -------- | --------- | ----------------------------- |
| user_ID  | Int: true | Integer value of the users ID |

## POST User Snacks

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

> Example Response

```json
{
    "status": true,
    "message": "Successfully manifested suggested snack to company's suggested snacks"
}
```

### Endpoint

`POST /users/{user_ID}/snacks/{snack_ID}`

### URL Parameters

| Property | Required  | Description                    |
| -------- | --------- | ------------------------------ |
| user_ID  | Int: true | Integer value of the users ID  |
| snack_ID | Int: true | Integer value of the snacks ID |

## DELETE User Snacks

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

Will remove the specific user's suggested snacks.

> Example Response

```json
{
    "status": true,
    "message": "Successfully destroyed suggested snack from user and user's suggested snacks"
}
```

### Endpoint

`DELETE /users/{user_ID}/snacks/{snack_ID}`

### URL Parameters

| Property | Required  | Description                    |
| -------- | --------- | ------------------------------ |
| user_ID  | Int: true | Integer value of the users ID  |
| snack_ID | Int: true | Integer value of the snacks ID |
