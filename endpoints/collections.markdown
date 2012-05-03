# Collection resources (/collections)

## Collection Index
* GET `http://www.boutine.com/api/v1/collections/`
* POST `http://www.boutine.com/api/v1/collections/`
* DELETE `http://www.boutine.com/api/v1/collections/<ID>/`
* GET `http://www.boutine.com/api/v1/collections/featured/`
* GET `http://www.boutine.com/api/v1/collections/<ID>/`
* GET `http://www.boutine.com/api/v1/collections/<ID>/products/`

---

**List of all the collections**

GET `http://www.boutine.com/api/v1/collections/`

Response:

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

---

**Create a collection of signed in user
*Requires that a user is signed in through OAuth.

POST `http://www.boutine.com/api/v1/collections/`

Parameters:

  collection: a JSON payload

Sample:

        {
          "title": <title>,
          "description", <description>,
          "live", true/false
        }

---

**Remove collection of signed in user
*Requires that a user is signed in through OAuth.

DELETE `http://www.boutine.com/api/v1/collections/<ID>/`

Response:
        HTTP/1.1 200 OK


---

**List of all featured collections**

GET `http://www.boutine.com/api/v1/collections/featured/`

Response:

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

---

**Details of a collection**

GET `http://www.boutine.com/api/v1/collections/<ID>/`

Response:

        {
          "collection":{
            "id":127,
            "title":"Singing In The Rain",
            "collection_url":"http://www.boutine.com/collections/singing-in-the-rain"
          }
        }

---

**Collection's products**

GET `http://www.boutine.com/api/v1/collections/<ID>/products/`

Response:

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

