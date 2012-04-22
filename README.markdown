
# Boutine.com Public REST API


## Authorization and Authentication

Request to Boutine API must be authorized using OAuth 2.0. 


For non-public data, like a user's cart and user information required for
checkout, 3-legged authentication is used.

The details of the authorization process, or flow, for OAuth 2.0 is the
following for 3-legged authentication:

1. When you create an application, you register it with Boutine. Boutine
   then provides you with a Consumer key and secret.
2. When your application needs to access Boutine API it asks for a token
   using any standard OAuth library (depending on the technology/language of your application)
3. Boutine displays an OAuth page to the user asking them to authorize
   your application to request some of their data
4. If the user approves the Boutine gives your application a short-lived
   access token.
5. Your application requests user data, attaching the access token to
   the request.
6. If Boutine determines that your request and token are valid, it
   returns the requested data.

For public data 2-legged authentication is to be used, in which your
application using Boutine API is given authorization on behalf of a
user. Only cosumer key and secret are used in that case for
identification of your application to Boutine and no user sign in is
requested in the flow.


## User resources (/users)


List of all the users

GET `http://www.boutine.com/api/v1/users/`

Result:

        [
          {
            "user": {
              "id":10,
              "first_name": Naina,
              "last_name":Madan,
              "username":"zitara",
              "url":"http://www.boutine.com/zitara"
            }
          },
          ...
        ]


Register a new user

POST `http://www.boutine.com/api/v1/users/`

Parameters:

  user: a JSON payload

Sample:

        {
          "user":{
            "first_name": <first name>
            "last_name": <last name>
            "email": <email address>
            "username": <user name>
            "password": <password>
          }
        }
 
Response:

        HTTP/1.1 200 OK


List of all the designers

GET `http://www.boutine.com/api/v1/users/designers/`

Result:

        [
          {
            "user": {
              "id":10,
              "first_name": Naina,
              "last_name":Madan,
              "username":"zitara",
              "url":"http://www.boutine.com/zitara"
            }
          },
          ...
        ]


List of all the stylists

GET `http://www.boutine.com/api/v1/users/stylists/`

Result:

        [
          {
            "user": {
              "id":10,
              "first_name": Naina,
              "last_name":Madan,
              "username":"zitara",
              "url":"http://www.boutine.com/zitara"
            }
          },
          ...
        ]


Details of a user

GET `http://www.boutine.com/api/v1/users/<ID>/`

Result:

        {
          "profile":{
            "id":10,
            "first_name":"Naina",
            "last_name":"Madan",
            "profile_url":"http://localhost:3000/zitara",
            "store_url":"http://localhost:3000/users/zitara/store"
          }
        }


User's shop

GET `http://www.boutine.com/api/v1/users/<ID>/store/`

Result:

        [
          {
            "product":{
              "id":147,
              "title":"Tapi",
              "description":"Wool cap sleeve",
              "price":360.0,
              "category_id":2,
              "images":
                [
                  {
                    "image":{
                      "normal":"https://..../normal.JPG?1323805109",
                      "small":"https://.../small.JPG?1323805109",
                      "square":"https://.../square.JPG?1323805109"
                    }
                  },
                  ...
                ],
              "stylists":
                [
                  {
                    "stylist":{
                      "id":158,
                      "username":"natasha",
                      "store_name":"Natasha's Store"
                    }
                  },
                  ...
                ],
              "designer":{
                "id":69,
                "username":"zitara",
                "store_name":"Zitara"
              },
              "sizes":
                [
                  {
                    "size":{
                      "quantity":-1,
                      "size_code":"19-rings-sizes-6"
                    }
                  },
                  ...
                ]
            }
          },
          ...
        ]




User's collections

GET `http://www.boutime.com/api/v1/users/<ID>/collections/`

Result:

        [
          {
            "collection":{
              "id":90,
              "title":"Black Bags",
              "description":"The classic black bag - goes with everything!"
              }
          },
          ...
        ]


User's followers

GET `http://www.boutine.com/api/v1/users/<ID>/followers/`

Result:

        [
          {
            "user": {
              "id":10,
              "first_name": Naina,
              "last_name":Madan,
              "username":"zitara",
              "url":"http://www.boutine.com/zitara"
            }
          },
          ...
        ]


Users following a user

GET `http://www.boutine.com/api/v1/users/<ID>/following/`

Result:

        [
          {
            "user": {
              "id":10,
              "first_name": Naina,
              "last_name":Madan,
              "username":"zitara",
              "url":"http://www.boutine.com/zitara"
            }
          },
          ...
        ]



Details of current user. This requires that a user is signed in through
OAuth.

GET `http://www.boutine.com/api/v1/users/me/`

Result:

        {
          "profile":{
            "id":10,
            "first_name":"Naina",
            "last_name":"Madan",
            "profile_url":"http://localhost:3000/zitara",
            "store_url":"http://localhost:3000/users/zitara/store"
          }
        }


## Category resources (/categories)


List of all the categories

GET `http://www.boutine.com/api/v1/categories/`

Result:

        [
          {
            "category":{
              "id":1,
              "name":"Clothing",
              "weight":100,
              "size_group_name":"",
              "categories":
                [
                  {
                    "category":{
                      "id":2,
                      "name":"Dresses",
                      "weight":9
                    }
                  },
                  ...
                ]
            }
          },
          ...
        ]

Details of a category and its sub categories

GET `http://www.boutine.com/api/v1/categories/<ID>/`

Result:

        {
          "category" : {
            "id" : 1,
            "name" : "Clothing",
            "weight" : 100,
            "size_group_name" : "",
            "categories": [
              {
                "category":{
                  "id":2,
                  "name":"Dresses",
                  "size_group_name":"small-medium-large",
                  "weight":9
                }
              },
              ...
            ]
          }
        }


List of products in a category

GET `http://www.boutine.com/api/v1/categories/<ID>/products/`

Result:

        [
          {
            "product":{
              "id":147,
              "title":"Tapi",
              "description":"Wool cap sleeve",
              "price":360.0,
              "category_id":2,
              "images":
                [
                  {
                    "image":{
                      "original":"https://..../original.JPG?1323805109",
                      "normal":"https://..../normal.JPG?1323805109",
                      "small":"https://.../small.JPG?1323805109",
                      "square":"https://.../square.JPG?1323805109"
                    }
                  },
                  ...
                ],
              "stylists":
                [
                  {
                    "stylist":{
                      "id":158,
                      "username":"natasha",
                      "store_name":"Natasha's Store"
                    }
                  },
                  ...
                ],
              "designer":{
                "id":69,
                "username":"zitara",
                "store_name":"Zitara"
              },
              "sizes":
                [
                  {
                    "size":{
                      "quantity":-1,
                      "size_code":"19-rings-sizes-6"
                    }
                  },
                  ...
                ]
            }
          },
          ...
        ]


## Collection resources (/collections)

List of all the collections

GET `http://www.boutine.com/api/v1/collections/`

Result:

        [
          {
            "collection":{
              "id":127,
              "title":"Singing In The Rain",
              "description":"Let it rain, let it pour!"
            }
          },
          ...
        ]


POST `http://www.boutine.com/api/v1/collections/`


Parameters:

  collection: a JSON payload

Sample:

        {
          "title": <title>
        }
  



Details of a collection

GET `http://www.boutine.com/api/v1/collections/<ID>/`

Result:

        {
          "collection":{
            "id":127,
            "title":"Singing In The Rain",
            "collection_url":"http://www.boutine.com/collections/singing-in-the-rain"
          }
        }

Collection's products

GET `http://www.boutine.com/api/v1/collections/<ID>/products/`

Result:

        [
          {
            "product":{
              "id":147,
              "title":"Tapi",
              "description":"Wool cap sleeve",
              "price":360.0,
              "category_id":2,
              "images":
                [
                  {
                    "image":{
                      "original":"https://..../original.JPG?1323805109",
                      "normal":"https://..../normal.JPG?1323805109",
                      "small":"https://.../small.JPG?1323805109",
                      "square":"https://.../square.JPG?1323805109"
                    }
                  },
                  ...
                ],
              "stylists":
                [
                  {
                    "stylist":{
                      "id":158,
                      "username":"natasha",
                      "store_name":"Natasha's Store"
                    }
                  },
                  ...
                ],
              "designer":{
                "id":69,
                "username":"zitara",
                "store_name":"Zitara"
              },
              "sizes":
                [
                  {
                    "size":{
                      "quantity":-1,
                      "size_code":"19-rings-sizes-6"
                    }
                  },
                  ...
                ]
            }
          },
          ...
        ]


## Product resources (/products)

List of all the products

GET `http://www.boutine.com/api/v1/products/`

Parameters:

  page: page number

Example:

  http://www.boutine.com/api/v1/products/?page=5

Result:

        [
          {
            "product":{
              "id":147,
              "title":"Tapi",
              "description":"Wool cap sleeve",
              "price":360.0,
              "category_id":2,
              "images":
                [
                  {
                    "image":{
                      "original":"https://..../original.JPG?1323805109",
                      "normal":"https://..../normal.JPG?1323805109",
                      "small":"https://.../small.JPG?1323805109",
                      "square":"https://.../square.JPG?1323805109"
                    }
                  },
                  ...
                ],
              "stylists":
                [
                  {
                    "stylist":{
                      "id":158,
                      "username":"natasha",
                      "store_name":"Natasha's Store"
                    }
                  },
                  ...
                ],
              "designer":{
                "id":69,
                "username":"zitara",
                "store_name":"Zitara"
              },
              "sizes":
                [
                  {
                    "size":{
                      "quantity":-1,
                      "size_code":"19-rings-sizes-6"
                    }
                  },
                  ...
                ]
            }
          },
          ...
        ]


Details of a product


GET `http://www.boutine.com/api/v1/products/<ID>/`

Result:

          {
            "product":{
              "id":147,
              "title":"Tapi",
              "description":"Wool cap sleeve",
              "price":360.0,
              "category_id":2,
              "images":
                [
                  {
                    "image":{
                      "original":"https://..../original.JPG?1323805109",
                      "normal":"https://..../normal.JPG?1323805109",
                      "small":"https://.../small.JPG?1323805109",
                      "square":"https://.../square.JPG?1323805109"
                    }
                  },
                  ...
                ],
              "stylists":
                [
                  {
                    "stylist":{
                      "id":158,
                      "username":"natasha",
                      "store_name":"Natasha's Store"
                    }
                  },
                  ...
                ],
              "designer":{
                "id":69,
                "username":"zitara",
                "store_name":"Zitara"
              },
              "sizes":
                [
                  {
                    "size":{
                      "quantity":-1,
                      "size_code":"19-rings-sizes-6"
                    }
                  },
                  ...
                ]
            }
          }

## Cart resources (/cart)

Details of the current items in cart. Requires user to be signed in
through 3-legged OAuth.

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

Add item to cart. Requires user to be signed in
through 3-legged OAuth. In case a product is already in the cart, its
quantity is incremented.


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


Remove item from cart. Requires user to be signed in
through 3-legged OAuth.


DELETE `http://www.boutine.com/api/v1/cart/item/<ID>`


Response:

        HTTP/1.1 200 OK

