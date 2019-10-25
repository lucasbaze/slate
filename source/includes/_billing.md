# Billing

The snacks endpoint will return a paginated result of the snacks that are available

## POST Stripe

> Example Request

```json
{
	"price": 199.00,
	"token": <token>
}
```

> Example Success Response

```json
{
    "message": "Successfully charged the user"
}
```

> Example Failue Response

```json
{
    "message": "Application shit the bed"
}
```

<aside class="success">
Live - Successfully turned caffeine into code
</aside>

### Endpoint

`POST billing/stripe`

### Body Description

| Property | Required     | Description                                          |
| -------- | ------------ | ---------------------------------------------------- |
| price    | Float: true  | The price to charge the user                         |
| token    | String: true | The token returned by stripe to authorize the charge |
