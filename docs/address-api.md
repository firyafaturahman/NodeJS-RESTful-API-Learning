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
