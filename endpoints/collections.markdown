# Collection resources (/collections)

## Collection Index
* GET `http://www.boutine.com/api/v1/collections/`
* POST `http://www.boutine.com/api/v1/collections/`
* GET `http://www.boutine.com/api/v1/collections/<ID>/`
* GET `http://www.boutine.com/api/v1/collections/<ID>/products/`

**List of all the collections**

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




**Details of a collection**

GET `http://www.boutine.com/api/v1/collections/<ID>/`

Result:

        {
          "collection":{
            "id":127,
            "title":"Singing In The Rain",
            "collection_url":"http://www.boutine.com/collections/singing-in-the-rain"
          }
        }

**Collection's products**

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

