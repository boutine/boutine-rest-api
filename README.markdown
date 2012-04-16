
# Boutine.com Public REST API


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
          "first_name": <first name>
          "last_name": <last name>
          "email": <email address>
          "username": <user name>
          "password": <password>
        }
  


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
              "id":310,
              "title":"Silver Flat Mod Ball Ring",
              "description":"Handwoven around a sterling silver shape band.
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
            "category": {
              "id" : 17,
              "name" : "Necklaces",
              "weight" : 3,
              "size_group_name" : "small-medium-large"
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
            "children": [
              {
                "ancestry":"0/1",
                "id":2,
                "name":"Dresses",
                "size_group_name":"small-medium-large",
                "slug":"dresses",
                "weight":9
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
            "product" : {
              "id" : 147,
              "title":"Tapi",
              "description":"Wool cap sleeve princess cut dress."
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
              "id":1157,
              "title":"Vinyl Coat W/Geometrical Detailing",
              "description":"Transparent, pink vinyl coat."
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
              "id":200,
              "title":"Twist back Tank"
            }
          },
          ...
        ]


Details of a product


GET `http://www.boutine.com/api/v1/products/<ID>/`

Result:

        {
          "product":{
            "id":208,
            "title":"Aphrodite 56",
            "price":114.0,
            "description":"Hammered drop hoop wrapped with vessonite",
            "category_id":39,
            "designer_id":115,
            "product_url":"http://www.boutine.com/products/aphrodite-56"
          }
        }

