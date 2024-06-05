# Capstone Bali API

> API untuk Pengerjaan Capstone Bali.

<h4 id="base-url">Base URL<h4>

[http://localhost:3000](#)

<h4 id="endpoints">Endpoints<h4>

### Users

#### Register User

- URL:
  - **`/register`**
- Method:
  - POST
- Request Body:
  - `name` as `string`
  - `email` as `string`
  - `password` as `string`, must be at least 6 characters
- Response:

```json
{
  "status": "success",
  "message": "User Created",
  "data": {
    "id": "U9lFEoWjq3",
    "name": "Ricky",
    "email": "Ricky32@gmail.com",
    "password": "f6319ca0990347af47037dea7a9a640d9dbd7222772a62818154e1181344f212"
  }
}
```

### Login User

- URL:
  - **`/login`**
- Method:
  - POST
- Request Body:
  - `email` as `string`
  - `password` as `string`
- Response:

```json
{
  "status": "success",
  "message": "User Logged successfully",
  "data": {
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiJVOWxGRW9XanEzIiwiaWF0IjoxNzE3NTcwNjczLCJleHAiOjE3MTc1NzQyNzN9.RhPm6prC5ihOauUyrQAWPmLF9TuIWctaevOTpjXkpEA"
  }
}
```

### Get User Login

- URL:
  - **`/users/me`**
- Method:
  - GET
- Headers:
  - **`Authorization`**: **`Bearer <token>`**
- Response:

```json
{
  "status": "success",
  "message": "User retrieved",
  "data": {
    "id": "U9lFEoWjq3",
    "name": "Ricky",
    "email": "Ricky32@gmail.com"
  }
}
```

### Destinations

#### Add Destinations

- URL:
  - **`/destinations`**
- Method:
  - POST
- Headers:
  - **`Authorization`**: **`Bearer <token>`**
- Request Body:
  - `name` as `string`
  - `description` as `string`
  - `img` as `string`
  - `location` as `string`
- Response:

```json
{
  "status": "success",
  "message": "Destination Created successfully",
  "data": {
    "id": "LsJGEVRsFP",
    "name": "Testing",
    "description": "ini Testing",
    "img": "imgTesting",
    "location": "Ubud-Bali"
  }
}
```

#### Get All Destinations

- URL:
  - **`/destinations`**
- Method:
  - GET
- Response:

```json
{
  "status": "Success",
  "message": "Get All Destination success",
  "data": {
    "Destination": [
      {
        "id": "LsJGEVRsFP",
        "name": "Testing",
        "description": "ini Testing",
        "img": "imgTesting",
        "location": "Ubud-Bali"
      }
    ]
  }
}
```

#### Get Destinations By Id

- URL:
  - **`/destinations/<destinationId>`**
- Method:
  - GET
- Response:

```json
{
  "status": "success",
  "message": "Get Destinations by id success",
  "data": {
    "id": "LsJGEVRsFP",
    "name": "Testing",
    "description": "ini Testing",
    "img": "imgTesting",
    "location": "Ubud-Bali"
  }
}
```

#### Delete Destinations

- URL:
  - **`/destinations/<destinationId>`**
- Method:
  - DELETE
- Headers:
  - **`Authorization`**: **`Bearer <token>`**
- Response:

```json
{
  "status": "success",
  "message": "Destination has been deleted"
}
```
