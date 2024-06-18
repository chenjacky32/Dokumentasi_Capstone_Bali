# Capstone Bali API

> API untuk Pengerjaan Project Capstone Bali.

<h4 id="base-url">Base URL<h4>

[https://capstone-bali-api.my.id](#)

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
  - **`Authorization`**: **`Bearer <accessToken>`**
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

#### Get All Destinations

- URL:
  - **`/destinations`**
- Method:
  - GET
- Response:

```json
{
  "status": "Success",
  "message": "Get All Destinations success",
  "data": {
    "destinations": [
      {
        "id": "QvO6iWZFva",
        "name": "Jimbaran Beach",
        "description": "Pura Ulun Danu Batur, dibangun pada tahun 1926, merupakan kompleks pura terpenting kedua di Bali, setelah pura terbesar Besakih. Pura ini didedikasikan untuk Dewi Batari Ulun Danu, dewi danau dan sungai. “Ulun Danu” secara harfiah diterjemahkan sebagai “kepala danau”.\nSampai tahun 1926 Pura Ulun Danu dan Desa Batur terletak di bawah kaldera, di kaki gunung berapi Batur. Setelah gunung berapi meletus hebat pada tahun 1926, baik desa dan pura dihancurkan kecuali pura yang paling penting, meru 11 tingkat yang didedikasikan untuk Dewi Batari Ulun Danu. Penduduk desa pindah ke tepi kaldera tertinggi dan tertua dimana mereka membangun kembali desa dan pura mereka.\nSebenarnya Pura Ulun Danu adalah kompleks sembilan pura yang berbeda, yang berisi total 285 pura  yang didedikasikan untuk dewa dan dewi air, pertanian, mata air suci, seni, kerajinan, dll.",
        "img": "https://assets-global.website-files.com/63c7fcf9e64a0f1cdf40ec28/644e5ffe0dbcfab876cc61f6_where-to-live-in-canggu-cover.jpg",
        "location": "Bangli / Daya Tarik Wisata",
        "avgRating": 0
      },
      {
        "id": "06073a4c-e",
        "name": "GILIMANUK BAY",
        "description": "The bay of Gilimanuk is a bay of Ferry that connect to the island of Bali with the Java Island through strait of Bali. Gilimanuk bay is in a management of ASDP Indonesian Ferry. This bay is chosen by the tourists who want to go to Java Island using the land route. Everyday, there are thousands of Ferry trip carry away passengers and vehicles toward Java Island through Gilimanuk bay in Bali.\nLocation: Gilimanuk sub-district, Melaya district, Jembrana regency",
        "img": "https://www.majalahlintas.com/storage/2023/05/18-Mei-2023_Pengembangan-Pelabuhan-Gilimanuk_foto-ASDP-e1684384840788.jpeg",
        "location": "Jembrana",
        "avgRating": 0
      }
    ]
  }
}
```

#### Get Destinations By Id

- URL:
  - **`/destinations/{dest_id}`**
- Method:
  - GET
- Response:

```json
{
  "status": "Success",
  "message": "Get Destinations by id success",
  "data": {
    "id": "QvO6iWZFva",
    "name": "Jimbaran Beach",
    "description": "Pura Ulun Danu Batur, dibangun pada tahun 1926, merupakan kompleks pura terpenting kedua di Bali, setelah pura terbesar Besakih. Pura ini didedikasikan untuk Dewi Batari Ulun Danu, dewi danau dan sungai. “Ulun Danu” secara harfiah diterjemahkan sebagai “kepala danau”.\nSampai tahun 1926 Pura Ulun Danu dan Desa Batur terletak di bawah kaldera, di kaki gunung berapi Batur. Setelah gunung berapi meletus hebat pada tahun 1926, baik desa dan pura dihancurkan kecuali pura yang paling penting, meru 11 tingkat yang didedikasikan untuk Dewi Batari Ulun Danu. Penduduk desa pindah ke tepi kaldera tertinggi dan tertua dimana mereka membangun kembali desa dan pura mereka.\nSebenarnya Pura Ulun Danu adalah kompleks sembilan pura yang berbeda, yang berisi total 285 pura  yang didedikasikan untuk dewa dan dewi air, pertanian, mata air suci, seni, kerajinan, dll.",
    "img": "https://assets-global.website-files.com/63c7fcf9e64a0f1cdf40ec28/644e5ffe0dbcfab876cc61f6_where-to-live-in-canggu-cover.jpg",
    "location": "Bangli / Daya Tarik Wisata",
    "avgRating": 0
  }
}
```

### Bookmarks

#### AddBookmarks

- URL:
  - **`/destinations/{dest_id}/bookmarks`**
- Method:
  - POST
- Headers:
  - **`Authorization`**: **`Bearer <accessToken>`**
- Response:

```json
{
  "status": "success",
  "message": "Destinations Bookmarked",
  "data": {
    "id": "P82EaWRlT3",
    "user_id": "JgdL8hRvlX",
    "name": "jacky",
    "dest_id": "06073a4c-e",
    "dest_name": "GILIMANUK BAY",
    "isBookmark": true
  }
}
```

#### UnBookmarks

- URL:
  - **`/destinations/{dest_id}/unbookmarked`**
- Method:
  - POST
- Headers:
  - **`Authorization`**: **`Bearer <accessToken>`**
- Response:

```json
{
  "status": "success",
  "message": "Destinations unbookmarked",
  "data": {
    "id": "Y4wHRJf22j",
    "user_id": "zb9knyD0rr",
    "name": "admin",
    "dest_id": "Y4wHRJf22j",
    "dest_name": "Pulau Batur",
    "isBookmark": false
  }
}
```

#### GetDestinationBookmarks

- URL:
  - **`/destinations/bookmarks`**
- Method:
  - GET
- Headers:
  - **`Authorization`**: **`Bearer <accessToken>`**
- Response:

```json
{
  "status": "success",
  "message": "Destinations retrieved",
  "data": {
    "Bookmarks": [
      {
        "id": "tk6sXuzXjS",
        "user_id": "zb9knyD0rr",
        "name": "admin",
        "dest_id": "Y4wHRJf22j",
        "dest_name": "Pulau Batur",
        "isBookmark": true
      }
    ]
  }
}
```

#### GetDestinationUnbookmarks

- URL:
  - **`/destinations/unbookmarks`**
- Method:
  - GET
- Headers:
  - **`Authorization`**: **`Bearer <accessToken>`**
- Response:

```json
{
  "status": "success",
  "message": "Destinations retrieved",
  "data": {
    "Unbookmarked": [
      {
        "id": "tk6sXuzXjS",
        "user_id": "zb9knyD0rr",
        "name": "admin",
        "dest_id": "Y4wHRJf22j",
        "dest_name": "Pulau Batur",
        "isBookmark": false
      }
    ]
  }
}
```

### Ratings

#### AddRatings

- URL:
  - **`/destinations/{dest_id}/ratings`**
- Method:
  - POST
- Request Body:
  - `rating` as `number`
- Headers:
  - **`Authorization`**: **`Bearer <accessToken>`**
- Response:

```json
{
  "status": "success",
  "message": "Rating created successfully",
  "data": {
    "id": "sIqqV85eQQ",
    "rating": 7,
    "dest_id": "Y4wHRJf22j",
    "dest_name": "Pulau Batur",
    "user_id": "zb9knyD0rr",
    "name": "admin"
  }
}
```
