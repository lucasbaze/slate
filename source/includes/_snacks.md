# Snacks

The snacks endpoint will return a paginated result of the snacks that are available

## GET Snacks

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

### Endpoint

`GET /snacks`

> Example Request
> `/snacks?page=2&limit=15`

> Example Response

```json
{
    "previous": {
        "page": 1,
        "limit": 15
    },
    "next": {
        "page": 3,
        "limit": 15
    },
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

> Example Request
> `/snacks?search=original`

```json
{
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

### Query Parameters

| Parameter | Default | Description                                                                                          |
| --------- | ------- | ---------------------------------------------------------------------------------------------------- |
| search    | ''      | The search query to search by name of snacks                                                         |
| page      | 1       | The start "page" to get snacks. Eg. Page = 2, Limit = 15: start at snack ID of 15 and go to Snack 30 |
| limit     | 20      | The number of snacks you want back                                                                   |

### Response Description

| Property       | Description                                                                                            |
| -------------- | ------------------------------------------------------------------------------------------------------ |
| previous/page  | The page number to get the previous limit number of snacks                                             |
| previous/limit | The same limit given or default of 20                                                                  |
| next/page      | The page number to get the next limit number of snacks                                                 |
| next/limit     | The same limit given or default of 20                                                                  |
| snacks/name    | Name of the snack.                                                                                     |
| snacks/brand   | Company brand of the snack.                                                                            |
| snacks/oum     | Unit of Measure. If the user changes the quantity, this is how much it will increment or decrement by. |
| snacks/img_url | A url for an unformatted picture of the snack.                                                         |
