# Company

The company endpoints will be used for most operations when the User that is logged in is the admin on the account.

## GET Company Info

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

> Example Response

```json
{
    "name": "Lambda School",
    "phone": "(123) 456-7890",
    "city": "Palo Alto",
    "state": "CA",
    "package_ID": 4,
    "company_ID": 32
}
```

### Endpoint

`GET /company/{company_ID}`

### URL Parameters

| Property   | Required  | Description                       |
| ---------- | --------- | --------------------------------- |
| company_ID | Int: true | Integer value of the company's ID |

## PUT Company Info

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

Updates the company's info, and is only allowed if the user is the admin, and associated with the same company. But I don't know what kind of voodoo magic the client or user may perform to screw that up.

> Example PUT Request

```json
{
    "name": "Gamma School",
    "phone": "(890) 765-4321",
    "city": "Salt Lake City",
    "state": "UT",
    "package_ID": 3
}
```

> Example Response

```json
{
    "name": "Gamma School",
    "phone": "(890) 765-4321",
    "city": "Salt Lake City",
    "state": "UT",
    "package_ID": 3
}
```

### Endpoint

`PUT /company/{company_ID}`

### Body Parameters

| Parameter  | Required      | Description                                                     |
| ---------- | ------------- | --------------------------------------------------------------- |
| name       | String: false | Company Name.                                                   |
| phone      | String: False | Must be at least a 10 character string.                         |
| city       | String: false | City the company is located at                                  |
| state      | String: false | State the company located at                                    |
| package_ID | Int: false    | Package ID which will only be 1, 2, 3, or 4, will default to 1. |

### URL Parameters

| Property   | Required  | Description                   |
| ---------- | --------- | ----------------------------- |
| company_ID | Int: true | Integer value of company's ID |

## GET Company Snacks

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

These are the snacks the company has selected to be delivered.

> Example Response

```json
{
    "name": "Lambda School",
    "snacks": [
        {
            "name": "Original Skittles",
            "brand": "Wrigley",
            "uom": "54 oz bag",
            "img_url": "https://images-na.ssl-images-amazon.com/images/I/71dHUI2QzEL._SX425_.jpg"
        },
        {
            "name": "Original Doritos",
            "brand": "Frito-Lay",
            "uom": "16 x 9oz bags",
            "img_url": "https://target.scene7.com/is/image/Target/GUEST_ac2b08b4-12e8-496c-ab09-dd530740da9c?wid=488&hei=488&fmt=pjpeg"
        }
    ]
}
```

### Endpoint

`GET /company/{company_ID}/snacks`

### URL Parameters

| Property   | Required  | Description                   |
| ---------- | --------- | ----------------------------- |
| company_ID | Int: true | Integer value of company's ID |

## POST Company Snacks

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

This will manifest the snack to the company's selected snacks.

It will automatically set the quantity to 1 for the snack.

> Example Response

```json
{
    "snack": "Original Doritos",
    "quantity": 1
}
```

### Endpoint

`POST /company/{company_ID}/snacks/{snack_ID}`

### URL Parameters

| Property   | Required  | Description                   |
| ---------- | --------- | ----------------------------- |
| company_ID | Int: true | Integer value of company's ID |
| snack_ID   | Int: true | Integer value of snack ID     |

## PUT Company Snacks

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

This will primarily update the quanitity requested on the users

> Example PUT Request

```json
{
    "quantity": 3
}
```

> Example Response

```json
{
    "snack": "Original Doritos",
    "quantity": 3
}
```

### Endpoint

`PUT /company/{company_ID}/snacks/{snack_ID}`

### Body Parameters

| Property | Required  | Description                             |
| -------- | --------- | --------------------------------------- |
| quantity | Int: true | Integer value of the quantity requested |

### URL Parameters

| Property   | Required  | Description                   |
| ---------- | --------- | ----------------------------- |
| company_ID | Int: true | Integer value of company's ID |
| snack_ID   | Int: true | Integer value of snack ID     |

## DELETE Company Snack

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

This will remove the specific snack ID from the company ID. Don't worry, it's not gonna delete any snacks from the database.

> Example Response

```json
{
    "snack": "Original Doritos",
    "message": "Successfully destroyed snacks existance from company"
}
```

### Endpoint

`DELETE /company/{company_ID}/snacks/{snack_ID}`

### URL Parameters

Basically the exact same as the POST

| Parameter  | Required  | Description |
| ---------- | --------- | ----------- |
| company_ID | Int: true | Company ID. |
| snack_ID   | Int: true | Snack ID.   |

## GET Company Suggested Snacks

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

These are the gooey yum yum's those employees desperately crave.

These are the snacks suggested by the company's users.

> Example Response

```json
{
    "name": "Lambda School",
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

`GET /company/{company_ID/suggested`

### URL Parameters

| Property   | Required  | Description                   |
| ---------- | --------- | ----------------------------- |
| company_ID | Int: true | Integer value of company's ID |

## GET Company Users

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

Retrieve all the users from the mainframe that are assocaited with the company

> Example Response

```json
{
    "name": "Lambda School",
    "users": [
        {
            "name": "Amanda Lane",
            "email": "amanda@lambdaschool.com",
            "user_ID": 1
        },
        {
            "name": "Elon Musk",
            "email": "elon@lambdaschool.com",
            "user_ID": 2
        },
        {
            "name": "George Washington",
            "email": "george@lambdaschool.com",
            "user_ID": 3
        }
    ]
}
```

### Endpoint

`GET /company/{company_ID}/users`

### URL Parameters

| Property   | Required  | Description                   |
| ---------- | --------- | ----------------------------- |
| company_ID | Int: true | Integer value of company's ID |

## DELETE Company User

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

Need to determine if I'm going to remove the user from teh database or just set a revoked flag onto the user.

If I set revoked, I'd have to unset flag to let them back in
If I delete it, then they can just add back in, but then the user would have to create another acccount.

### Endpoint

`DELETE /company/{company_ID}/users/{user_ID}`

### URL Parameters

| Property   | Required  | Description                   |
| ---------- | --------- | ----------------------------- |
| company_ID | Int: true | Integer value of company's ID |
| user_ID    | Int: true | Integer value of user's ID    |
