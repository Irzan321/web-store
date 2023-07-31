# Payment API Spec

## Payment Mathod API

Endpoint : POST/api/payment

Request Body :

```json
{
  "id": 1,
  "name_product": "bags",
  "quantity": 1,
  "harga_product": "20.000",
  "total_harga": "40.000",
  "payment_mathod": {
    "mathod": "transfer",
    "name_bank": "BCA",
    "nomor_rekening": 21121206663,
    "nama_rekening": "irzan"
  }
}
```

Response Body Success :

```json
{
  "id": 1,
  "name_product": "bags",
  "quantity": 1,
  "harga_product": "20.000",
  "total_harga": "40.000",
  "payment_mathod": {
    "mathod": "transfer",
    "name_bank": "BCA",
    "nomor_rekening": 21121206663,
    "nama_rekening": "irzan"
  },
  "status_payment": "paid off"
}
```

Response Body Failed :

```json
{
  "data": [
    {
      "error": {
        "code": 500, //jika terjadi kesalahan server
        "message": "Internal Server Error"
      }
    },
    {
      "error": {
        "code": 401, // jika users belum login
        "message": "User not authenticated"
      }
    }
  ]
}
```
