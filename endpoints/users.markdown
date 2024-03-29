# User resources (/users)

## User Index
* GET `http://www.boutine.com/api/v1/users/`
* POST `http://www.boutine.com/api/v1/users/`
* GET `http://www.boutine.com/api/v1/users/designers/`
* GET `http://www.boutine.com/api/v1/users/stylists/`
* GET `http://www.boutine.com/api/v1/users/<ID>/`
* GET `http://www.boutine.com/api/v1/users/<ID>/store/`
* GET `http://www.boutime.com/api/v1/users/<ID>/collections/`
* GET `http://www.boutine.com/api/v1/users/<ID>/following/`
* GET `http://www.boutine.com/api/v1/users/me/`
* POST `http://www.boutine.com/api/v1/users/forgot_password/`

---

**List of all the users**

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
---
**Register a new user**

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

---
**List of all the designers**

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

---
**List of all the stylists**

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

---
**Details of a user**

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

---
**User's shop**

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
**User's collections**

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

---
**User's followers**

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

---
**Users following a user**

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


---
**Details of current user.**
*This requires that a user is signed in through OAuth.*

GET `http://www.boutine.com/api/v1/users/me/`

Result:

        {
          "user":{
            "id":10,
            "first_name":"Naina",
            "last_name":"Madan",
            "profile_url":"http://localhost:3000/zitara",
            "store_url":"http://localhost:3000/users/zitara/store"
          }
        }


---
**Reset password of a user.**
*Email is sent to the user with his resetted password.*

POST `http://www.boutine.com/api/v1/user/forgot_password/`

Parameters:

  user: a JSON payload

Sample:

        {
          "user":{
            "email": <email address>            
          }
        }
 
Response:

        HTTP/1.1 200 OK



