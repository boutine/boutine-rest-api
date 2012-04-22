# Cart resources (/cart)

## Cart Index
* GET 'http://www.boutine.com/api/v1/cart/'

---

**Details of the current items in cart.**
*Requires user to be signed in through oauth.

GET 'http://www.boutine.com/api/v1/cart/'

        {
          "cart":{
            "id":91510,
            "items":
              [
                "item": {
                  "product_id": 47,
                  "stylist_id": 42,
                  "quantity": 1,
                  "shipping_price":10.0
                },
                ...
              ]
          }
        }
