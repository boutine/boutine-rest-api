# Category resources (/categories)

## Category Index
* GET `http://www.boutine.com/api/v1/categories/`
* GET `http://www.boutine.com/api/v1/categories/<ID>/`
* GET `http://www.boutine.com/api/v1/categories/<ID>/products/`

---

**List of all the categories**

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

---

**Details of a category and its sub categories**

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

---

**List of products in a category**

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

