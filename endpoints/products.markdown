# Product resources (/products)

## Products Index
* GET `http://www.boutine.com/api/v1/products/`
* POST `http://www.boutine.com/api/v1/products/`
* DELETE `http://www.boutine.com/api/v1/products/<ID>`
* POST `http://www.boutine.com/api/v1/products/<ID>/images/`
* DELETE `http://www.boutine.com/api/v1/products/<ID>/images/<IMAGE_ID>`
* GET `http://www.boutine.com/api/v1/products/featured/`
* GET `http://www.boutine.com/api/v1/products/<ID>/`

---

**List of all the products**

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
                      "original":{
                        "url":"https://.../uploaded_images/3978/original.jpg?1332358109",
                        "height":345,
                        "width":567
                      },
                      "normal":{
                        "url":"https://.../uploaded_images/3978/normal.jpg?1332358109",
                        "height":420,
                        "width":560
                      },
                      "small":{
                        "url":"https://.../uploaded_images/3978/small.jpg?1332358109",
                        "height":150,
                        "width":110
                      },
                      "square":{
                        "url":"https://.../uploaded_images/3978/square.jpg?1332358109",
                        "height":50,
                        "width":50
                      }
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


---

**Add a product**
*This requires that the user is signed in. The user of the product is the one who is signed in.
POST `http://www.boutine.com/api/v1/products/`

Parameters:
  A product JSON payload

Sample:

        {
          "product":{
            "title":"Product1",
            "description":"Great product",
            "price": 100.0,
            "in_stock": true,
            "live": true,
            "weight": 1,
            "category_id": 123
          }
        }

---

**Remove a product**
*This requires that the user is signed in. Only products of signed in user can be deleted.

DELETE `http://www.boutine.com/api/v1/products/<ID>/`
  
Response:
        HTTP/1.1 200 OK

---

**Add image to a product**
*This requires that the user is signed in. Image can added only to a product of the signed in user.
POST `http://www.boutine.com/api/v1/products/<ID>/images/`

Parameters:
  A form can be submitted with "image" as the name of file field.


---

**Remove image of a product**
*This requires that the user is signed in. Only images of products of signed in user can be removed.

DELETE `http://www.boutine.com/api/v1/products/<ID>/images/<IMAGE_ID>`

Response:
        HTTP/1.1 200 OK

---


**List of all the featured products**

Top 10 featured products are returned against this call.

GET `http://www.boutine.com/api/v1/products/featured/`

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
                      "original":{
                        "url":"https://.../uploaded_images/3978/original.jpg?1332358109",
                        "height":345,
                        "width":567
                      },
                      "normal":{
                        "url":"https://.../uploaded_images/3978/normal.jpg?1332358109",
                        "height":420,
                        "width":560
                      },
                      "small":{
                        "url":"https://.../uploaded_images/3978/small.jpg?1332358109",
                        "height":150,
                        "width":110
                      },
                      "square":{
                        "url":"https://.../uploaded_images/3978/square.jpg?1332358109",
                        "height":50,
                        "width":50
                      }
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

---

**Details of a product**


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
                     "original":{
                       "url":"https://.../uploaded_images/3978/original.jpg?1332358109",
                       "height":345,
                       "width":567
                     },
                     "normal":{
                       "url":"https://.../uploaded_images/3978/normal.jpg?1332358109",
                       "height":420,
                       "width":560
                     },
                     "small":{
                       "url":"https://.../uploaded_images/3978/small.jpg?1332358109",
                       "height":150,
                       "width":110
                     },
                     "square":{
                       "url":"https://.../uploaded_images/3978/square.jpg?1332358109",
                       "height":50,
                       "width":50
                     }
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
