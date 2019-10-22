# Users

The users endpoints are for users of a company but NOT the admins.

## GET User Info

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

Will only allow a user to request their own information. This is assuming that only admins will need to access all of the users and that can be done at `GET /company/{company_ID}/users`

> Example Response

```json
{
    "company_ID": 2,
    "company_name": "Lambda School",
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

## PUT User Info

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

> Example PUT request

```json
{
    "name": "Jimbo Fisher",
    "email": "jimbo@fisher.com",
    "img_url": "jimbos-fat-face.myfancyurl.com"
}
```

### Endpoint

`PUT /users/{user_ID}`

### Body Parameters

| Parameter | Required      | Description                                                         |
| --------- | ------------- | ------------------------------------------------------------------- |
| name      | String: true  | Must be at least 1 character long...                                |
| email     | String: true  | Must be a valid email address. Throw away emails will get rejected. |
| img_url   | String: false | Will be the url to their gravatar                                   |

## POST User Snacks

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

> Example Request URL: `/users/2/snacks/5`

> Example Response

```json
{
    "user_ID": 2,
    "snack_ID": 5
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

<aside class="success">
Live - Successfully turned caffeine into code
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

## DELETE User

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

This is permenantly delete the user from the database and remove the association from the company

### Endpoint

`DELETE /users/{user_ID}`
