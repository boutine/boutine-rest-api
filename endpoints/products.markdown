# Product resources (/products)

## Products Index
* GET `http://www.boutine.com/api/v1/products/`
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
