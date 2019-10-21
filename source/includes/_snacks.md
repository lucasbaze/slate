# Snacks

The snacks endpoint will return a paginated result of the snacks that are available

## GET Snacks

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

### Endpoint

`GET /snacks`

> Example Response

```json
{
    "first": "url to first level of snacks",
    "next": "url to next level of snacks",
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

### Response Description

| Property       | Description                                                                                            |
| -------------- | ------------------------------------------------------------------------------------------------------ |
| first          | url of the first level of snacks                                                                       |
| next           | url of the next level of snacks                                                                        |
| snacks/name    | Name of the snack.                                                                                     |
| snacks/brand   | Company brand of the snack.                                                                            |
| snacks/oum     | Unit of Measure. If the user changes the quantity, this is how much it will increment or decrement by. |
| snacks/img_url | A url for an unformatted picture of the snack.                                                         |
