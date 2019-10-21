# Packages

## GET Packages

<aside class="warning">
Under construction - Code gremlins currently turning caffeine into code
</aside>

> Response

```json
[
    {
        "name": "small",
        "description": "0 - 10 employees",
        "price": 199.0,
        "snacks": 10
    },
    {
        "name": "medium",
        "description": "11 - 50 employees",
        "price": 399.0,
        "snacks": 25
    },
    {
        "name": "large",
        "description": "51 - 100 employees",
        "price": 599.0,
        "snacks": 60
    },
    {
        "name": "mega",
        "description": ">100 employees",
        "price": 1999.0,
        "snacks": 100
    }
]
```

Again, if you can't figure this one out... idk what to do.

### Endpoint

`GET /packages`
