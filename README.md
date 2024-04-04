# RESTful Booker API Testing with POSTMAN and NEWMAN

## Table of Contents

- [Introduction](#introduction)
- [Base URL](#baseurl)
- [API Endpoints](#apiendpoints)
  - [Get Booking](#getbooking)
  - [Auth](#auth)
  - [Create Booking](#createbooking)
  - [Update Booking](#updatebooking)
  - [Delete Booking](#deletebooking)
- [Running Tests](#runningtests)
- [HTML result file](#forgettinghtmlreport)
- [Result](#result)

## Introduction
This project contains API tests for the RESTful Booker service, showcasing the usage of Postman and Newman for testing various endpoints.

## Base URL

- [RESTful Booker](https://restful-booker.herokuapp.com)

## API Endpoints

### 1. Get Booking

- **Method:** GET
- **Endpoint:** `/booking/{id}`
- **Description:** Retrieves details of a booking by ID.
- **Example Response:**
   ```json
   {
    "firstname": "Sally",
    "lastname": "Brown",
    "totalprice": 111,
    "depositpaid": true,
    "bookingdates": {
      "checkin": "2013-02-23",
      "checkout": "2014-10-23"
    },
    "additionalneeds": "Breakfast"
  }

### 2. Auth - Create Token
- **Method:** POST
- **Endpoint:** /auth
- **Description:** Creates an authentication token.
- **Example Request:**

        {
        "username": "admin",
        "password": "password123"
       }

- **Example Response:**

        {
          "token": "abc123"
        }



### 3. Create Booking
- **Method:** POST
- **Endpoint:** /booking/
- **Description:** Creates a new booking.
- **Example Request:**
curl -X POST https://restful-booker.herokuapp.com/booking \

        -H 'Content-Type: application/json' \
        -d '{
          "firstname": "Jim",
          "lastname": "Brown",
          "totalprice": 111,
          "depositpaid": true,
          "bookingdates": {
            "checkin": "2018-01-01",
            "checkout": "2019-01-01"
          },
          "additionalneeds": "Breakfast"
        }'


- **Example Response:**

        {
          "bookingid": 1,
          "booking": {
            "firstname": "Jim",
            "lastname": "Brown",
            "totalprice": 111,
            "depositpaid": true,
            "bookingdates": {
              "checkin": "2018-01-01",
              "checkout": "2019-01-01"
            },
            "additionalneeds": "Breakfast"
          }
        }


### 4. Update Booking
- **Method:** PUT
- **Endpoint:** /booking/{id}
- **Description:** Updates details of a booking by ID.
- **Example Usage:**
curl -X PUT https://restful-booker.herokuapp.com/booking/{id} \


        -H 'Cookie: token=abc123' \
        -d '{
          "firstname": "James",
          "lastname": "Brown",
          "totalprice": 111,
          "depositpaid": true,
          "bookingdates": {
            "checkin": "2018-01-01",
            "checkout": "2019-01-01"
          },
          "additionalneeds": "Breakfast"
        }'


### 5. Delete Booking
- **Method:** DELETE
- **Endpoint:** /booking/{id}
- **Description:** Deletes a booking by ID.
- **Example Request:**

        curl -X DELETE https://restful-booker.herokuapp.com/booking/{id}


### Running Tests
**Postman**
-Install Postman.
-Import the provided collection file into Postman.
-Run the collection and observe the results.

**Newman**
-Install Newman using npm install -g newman.
-Run Newman in the command line


### For getting html result file run this in command line:
 
    newman run home_work.postman_collection.json -e homework.postman_environment.json -r cli,htmlextra

### Result









