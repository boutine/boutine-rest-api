# Product resources (/products)

## Products Index
* GET `http://www.boutine.com/api/v1/products/`
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
