# NodeJS-RESTful-API-Learning

****

# User API Spec

## Register User API

Endpoint: POST /api/users

Request Body :

```json
{
  "username": "ff",
  "password": "rahasia",
  "name": "Firya Faturahman"
}
```

Response Body Success :

```json
{
  "data": {
    "username": "ff",
    "name": "Firya Faturahman"
  }
}
```

Response Body Error :

```json
{
  "errors": "Username already registered"
}
```

## Login User API

Endpoint: POST /api/users/login

Request Body :

```json
{
  "username": "ff",
  "password": "rahasia"
}
```

Response Body Success :

```json
{
  "data": {
    "token": "unique-token"
  }
}
```

Response Body Error :

```json
{
  "errors": "Username or password wrong"
}
```

## Update User API

Endpoint: PATCH /api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "name": "New Firya Faturahman ", // optional
  "password": "new password" // optional
}
```

Response Body Success :

```json
{
  "data": {
    "username": "ff",
    "name": "New Firya Faturahman"
  }
}
```

Response Body Error :

```json
{
  "errors": "Name length max 100"
}
```

## Get User API

Endpoint GET /api/users/current

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": {
    "username": "ff",
    "name": "Firya Faturahman"
  }
}
```

Response Body Error :

```json
{
  "errors": "Unauthorized"
}
```

## Logout User API

Endpoint : DELETE /api/users/logout

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :

```json
{
  "errors": "Unauthorized"
}
```
****

# Contact API Spec

## Create Contact API

---

Endpoint : POST /api/contacts

Headers :

- Authorization : token

Request Body :

```json
{
  "first_name": "firya",
  "last_name": "faturahman",
  "email": "firya@ff.com",
  "phone": "212121212121"
}
```

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "first_name": "Firya",
    "last_name": "Faturahman",
    "email": "firya@ff.com",
    "phone": "212121212121"
  }
}
```

Response Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## Update Contact API

---

Endpoint : PUT /api/contacts/:id

Headers :

- Authorization : token

Request Body :

```json
{
  "first_name": "firya",
  "last_name": "faturahman",
  "email": "firya@ff.com",
  "phone": "212121212121"
}
```

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "first_name": "Firya",
    "last_name": "Faturahman",
    "email": "firya@ff.com",
    "phone": "212121212121"
  }
}
```

Response Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## Get Contact API

---

Endpoint : GET /api/contacts/:id

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "first_name": "firya",
    "last_name": "faturahman",
    "email": "firya@ff.com",
    "phone": "212121212121
  }
}
```

Response Body Error :

```json
{
  "errors": "Contact is not found"
}
```

## Search Contact API

---

Endpoint : GET /api/contacts

Headers :

- Authorization : token

Query params :

- name : Search by first_name or last_name, using like, optional
- email : Search by email using like, optional
- page : Number of page, default 1
- size : size per page, default 10

Response Body Success :

```json
{
  "data":
  [
    {
      "id": 1,
      "first_name": "Firya",
      "last_name": "Faturahman",
      "email": "firya@ff.com",
      "phone": "212121212121
    },
    {
      "id": 2,
      "first_name": "Firya",
      "last_name": "Faturahman",
      "email": "firya@ff.com",
      "phone": "212121212121
    },
  ],
  "paging":{
    "page": 1,
    "total_page": 3,
    "total_item": 30
  }
}
```

Response Body Error :

## Remove Contact API

---

Endpoint : DELETE /api/contacts/:id

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :
{
"errors": "Contact is not found
}

****
# Address API Spec

## Create Address API
---

Endpoint : POST /api/contacts/:contactId/address

Headers :

- Authorization : token

Request Body :

```json
{
  "street": "jalan madrasah nomor 17",
  "city": "jakarta barat",
  "province": "dki jakarta",
  "country": "indonesia",
  "postal_code": "11550"
}
```

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "street": "jalan madrasah nomor 17",
    "city": "jakarta barat",
    "province": "dki jakarta",
    "country": "indonesia",
    "postal_code": "11550"
  }
}
```

Response Body Error :

```json
{
  "errors": "country is requred"
}
```

## Update Address API

---

Endpoint : PUT /api/contacts/:contactId/address/:addressId

Headers :

- Authorization : token

Request Body :

```json
{
  "street": "jalan madrasah nomor 17",
  "city": "jakarta barat",
  "province": "dki jakarta",
  "country": "indonesia",
  "postal_code": "11550"
}
```

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "street": "jalan madrasah nomor 17",
    "city": "jakarta barat",
    "province": "dki jakarta",
    "country": "indonesia",
    "postal_code": "11550"
  }
}
```

Reponse Body Error :

```json
{
  "errors": "country is requred"
}
```

## Get Address API

---

Endpoint : GET /api/contacts/:contactId/address/:addressId

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "street": "jalan madrasah nomor 17",
    "city": "jakarta barat",
    "province": "dki jakarta",
    "country": "indonesia",
    "postal_code": "11550"
  }
}
```

Response Body Error :

```json
{
  "errors": "contact is not found"
}
```

## Remove Address API

---

Endpoint : DELETE /api/contacts/:contactId/address/:addressId

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :

```json
{
  "errors": "address is not found"
}
```
