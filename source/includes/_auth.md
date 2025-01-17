# Authentication

> To authorize, it is recommended to create an axios handler in a separete folder with the following:

```javascript
const axios = require('axios');
axios.defaults.withCredentials = true;
axios.defaults.baseURL = 'https://afternoon-tor-81402.herokuapp.com';
export const axiosInstance = axios;
```

Snackify utilizes express-sessions to maintain session information. In order to access any of the endpoints, you will need to login at [Snackify Register](http://snackify.zeit.io). <- will need to be replaced.

No need to save a token or anything client side. That's for node noobs. The server will send you a cookie that will be handled by your browser and returned by axios if setup as recommended.

## POST Register

> Example POST NON Admin request

```json
{
    "name": "Judge Judy",
    "email": "judy@lambdaschool.com",
    "password": "password",
    "company_id": "lambda-school-snackify-123"
}
```

> Example NON Admin Response

```json
{
    "user_ID": 15,
    "name": "Judge Judy",
    "email": "judy@lambdaschool.com",
    "img_url": "https://www.riteaid.com/shop/media/catalog/product/cache/1/image/9df78eab33525d08d6e5fb8d27136e95/0/4/041570030837.jpg",
    "company_ID": 4,
    "admin": false
}
```

> Example POST New Admin request

```json
{
    "name": "Dr. Frankenstein",
    "email": "frakenstein@lambdaschool.com",
    "password": "password"
}
```

> Example New Admin Response

```json
{
    "user_ID": 15,
    "name": "Dr. Frankenstein",
    "email": "frankenstein@lambdaschool.com",
    "company_ID": 4,
    "admin": true
}
```

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

This enpoint allows the user to register.

If the user does not have a company code, this will create a user account and an empty company account. The company ID is created if no company code matches an existing company;

If the company code doesn't exist, everything explodes. JK. But please don't let everything explode.

### Endpoint

`POST /auth/register`

### POST Register Body Parameters

| Parameter    | Required      | Description                                                                                                            |
| ------------ | ------------- | ---------------------------------------------------------------------------------------------------------------------- |
| name         | String: true  | Must be at least 1 character long...                                                                                   |
| email        | String: true  | Must be a valid email address. Throw away emails will get rejected.                                                    |
| password     | String: true  | Must be at least 8 characters long.                                                                                    |
| company_code | String: false | This is the server-side generated company code that is given to invited users. NOT users signing up for the first time |

## PUT Register Company

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

> Example PUT Request

```json
{
    "name": "Lambda School",
    "phone": "(123) 456-7890",
    "city": "Palo Alto",
    "state": "CA",
    "package_ID": 4
}
```

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

`PUT /auth/register/company/{company_id}`

### PUT Register Company Body Parameters

| Parameter  | Required     | Description                                                                                   |
| ---------- | ------------ | --------------------------------------------------------------------------------------------- |
| name       | String: true | Company Name.                                                                                 |
| phone      | String: true | Must be at least a 10 character string.                                                       |
| city       | String: true | City the company is located at                                                                |
| state      | String: true | State the company located at                                                                  |
| package_ID | Int: false   | Package ID which will only be 1, 2, 3, or 4, will default to 1. You can put this value later. |

## POST Login

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

> Example Post Request

```json
{
	"email": "amanda@lambadschool.com",
	"password: "********"
}
```

> Example Response

```json
{
    "user_ID": 1,
    "company_ID": 2,
    "company_name": "Lambda School",
    "name": "Amanda Lane",
    "email": "amanda@lambdaschool.com",
    "img_url": "https://www.riteaid.com/shop/media/catalog/product/cache/1/image/9df78eab33525d08d6e5fb8d27136e95/0/4/041570030837.jpg",
    "admin": true,
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

`POST /auth/login`

### POST Login Body Parameters

| Parameter | Required     | Description                         |
| --------- | ------------ | ----------------------------------- |
| email     | String: true | Must be a valid email address.      |
| password  | String: true | Must be at least 8 characters long. |

## GET Logout

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

If you can't figure this one out, I can't help you.

> Response

```json
{
    "message": "You're leaving? Already? But we were just getting to know each other."
}
```

### Endpoint

`GET /auth/logout`
