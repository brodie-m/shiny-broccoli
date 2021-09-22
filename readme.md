# Yellow Pages API

- Yellow Pages is a simple API for viewing people and houses in your neighbourhood.
- Hosted at https://yellow-pages-api.netlify.app/
- The documentation below describes the possible interactions with our API via GET and POST requests 
- Please Enjoy!

## Houses [/houses]

### List All Houses [GET]

List all the houses currently available in the database via a GET request to https://yellow-pages-api.netlify.app/houses


+ Response 200 (application/json)
    
        [
          {
            id: 1,
            owner: "",
            address: "",
            numOccupants: "",
          },
          {
            id: 2,
            owner: "",
            address: "",
            numOccupants: "",
          },
        ]
        
        

### Add New Houses [POST]

Add new houses to the database with a POST request to https://yellow-pages-api.netlify.app/houses, using the following request structure:



+ Response 201 (application/json)

    + Headers

            Location: /houses,
            Content-Type: application/json

    + Body

            [
              {
                id: 3,
                owner: "John Smith",
                address: "5 Something Way",
                numOccupants: "3",
              },
              {
                id: 4,
                owner: "Jane Smith",
                address: "10 Something Road",
                numOccupants: "5",
              },
            ]

## Houses By Owner [/houses?owner=ownername]

### Get House By Owner Name [GET]

Get all the houses in the database that have the specified owner.

+ Response 200 (application/json)

        [
          {
            "id": 1,
            "owner": "ownername",
            "address": "3 Something Road",
            "numOccupants": "1",
          }
          {
            "id": 32,
            "owner": "ownername",
            "address": "5 Something Else Way",
            "numOccupants": "2",
          }
        ]
        

<!--/servername/house?owner=ownername-->

## Addresses [/addresses/alladdresses]


### List All Addresses [GET]

List all the addresses in the database.

+ Response 200 (application/json)

        [
            {
                "postcode": "BR3 3AB",
                "streetAddress": "Fake Road"
            },
            {
                "postcode": "BR3 3AB",
                "streetAddress": "Fake Road"
            }
        ]

### Add New Addresses [POST]

Add a new address using the following POST request structure:

+ Response 201 (application/json)

    + Headers

            Location: /houses,
            Content-Type: application/json

    + Body

            [
              {
                "postcode": "SW7 9BA",
                "streetAddress": "Something Road"
              },
              {
                "postcode": "NE4 7AX",
                "streetAddress": "Something Else Road"
              },
            ]


<!--/servername/alladdresses-->

## People [/people]

People can only be added to the database for privacy reasons. 
Use the following POST request structure to add people.

### Add New People To Database [POST]

+ Response 201 (application/json)

    + Headers

            Location: /people,
            Content-Type: application/json

    + Body

            [
              {
                name: "John Smith",
                age: 31,
                numInHouseHold: 2,
              },
              {
                name: "Someone Smith",
                age: 34,
                numInHouseHold: 3,
              },
            ]

## Neighbourhoods By Age Range [/neighbourhoods/neighbourhood?name=name/range?min=x&max=y]


### Get People In Neighbourhood Within Age Range [GET]

Find all people in the neighbourhood by a range of ages.
The range is specified by a minimum and maximum integer value.

+ Response 200 (application/json)

        [
          {
            name: "John Smith",
            age: 31,
            numInHouseHold: 1,
          },
          {
            name: "John Smith Two",
            age: 32,
            numInHouseHold: 5,
          },
          {
            name: "Smith Smith",
            age: 33,
            numInHouseHold: 4,
          },
          {
            name: "Jane Smith",
            age: 32,
            numInHouseHold: 6,
          },
        ]

<!--/servername/range?min=x&max=y-->

## Neighbourhoods By Household Size [/neighbourhoods/sizes?min=x&max=y]

### Get People In Neighbourhood By Household Size [GET]

Find all people in the neighbourhood by a range of household sizes.
The range is specified by a minimum and maximum integer value.

+ Response 200 (application/json)

        [
          {
            name: "Barry Smith",
            age: 25,
            numInHouseHold: 2,
          },
          {
            name: "Dave Two",
            age: 40,
            numInHouseHold: 2,
          },
          {
            name: "Someone Smith",
            age: 51,
            numInHouseHold: 2,
          },
          {
            name: "Jane Smith",
            age: 21,
            numInHouseHold: 2,
          },
        ]

<!--/servername/sizes?min=x&max=y-->

