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

