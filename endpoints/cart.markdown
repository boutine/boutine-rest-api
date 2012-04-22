# Cart resources (/cart)

## Cart Index
* GET 'http://www.boutine.com/api/v1/cart/'

---

**Details of the current items in cart.**
*Requires user to be signed in through 3-legged OAuth.

GET `http://www.boutine.com/api/v1/cart/`

        {
          "cart":{
            "id":91534,
            "items":
              [
                {
                  "item":{
                    "id":800,
                    "shipping_price":0.0,
                    "quantity":1,
                    "designer_id":69,
                    "unit_price":"98.0",
                    "unit_shipping":5.0,
                    "size_code":"small",
                    "product":{
                      "id":144,
                      "category_id":19,
                      "image":{
                        "normal":"https://.../normal.png?1332186019"
                      }
                    },
                    "stylist":{
                      "id":158,
                      "username":"natasha"
                    }
                  }
                }
              ]
           }
        }


**Add item to cart.**
*Requires user to be signed in through 3-legged OAuth. In case a product is already in the cart, its quantity is incremented.


POST `http://www.boutine.com/api/v1/cart/item/`


Example item:

        {
          "item":{
            "product_id":144, 
            "quantity":1,
            "stylist_id":42,
            "size_code":"small",
            "color_id":123
          }
        }

Response:

        HTTP/1.1 200 OK


**Remove item from cart.**
*Requires user to be signed in through 3-legged OAuth.


DELETE `http://www.boutine.com/api/v1/cart/item/<ID>`


Response:

        HTTP/1.1 200 OK
