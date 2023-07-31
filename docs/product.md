# Products API Spec

## Create Products API

Endpoint : POST/api/products

Headers :
-Authorization : token

Request Body :

```json
{
  "image_product": "bags.jpg",
  "name_product": "bags",
  "harga_product": "20.000",
  "stock_product": 10
}
```

Response Body Success :

```json
{
  "data": {
    "id": 1, //auto increment
    "image_product": "bags.jpg",
    "name_product": "bags",
    "harga_product": "20.000",
    "stock_product": 10
  }
}
```

Response Body Failed :

```json
{
  "error": "all must be filled"
}
```

## Update Product API

Endpoint : PUT/api/products/:id

Headers :
-Authorization : token

Request Body :

```json
{
  "image_product": "bags.jpg",
  "name_product": "bags",
  "harga_product": "30.000",
  "stock_product": 20
}
```

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "image_product": "bags.jpg",
    "name_product": "bags",
    "harga_product": "30.000",
    "stock_product": 20
  }
}
```

Response Body Failed :

```json
{
  "error": "Product update failed"
}
```

## Get Products API

Endpoint : POST/api/products/:id

Headers :
-Authorization : token

Response Body Success :

```json
{
  "data": {
    "id": 1,
    "image_product": "bags.jpg",
    "name_product": "bags",
    "harga_product": "30.000",
    "stock_product": 20
  }
}
```

Response Body Failed :

```json
{
  "error": "Product is not found"
}
```

## Search Products API

Endpoint : GET/api/products

Headers :
-Authorization : token

Query params :
-product : Search by name_product, using like //optional
-harga : Search by harga_product using like //optional
-page : number of page, default 1
-size : size per page, page 5

Response Body Success :

```json
{
  "data": [
    {
      "id": 1,
      "image_product": "bags.jpg",
      "name_product": "bags",
      "harga_product": "30.000",
      "stock_product": 20
    },
    {
      "id": 2,
      "image_product": "bags.jpg",
      "name_product": "bags",
      "harga_product": "30.000",
      "stock_product": 20
    },
    {
      "id": 3,
      "image_product": "bags.jpg",
      "name_product": "bags",
      "harga_product": "30.000",
      "stock_product": 20
    }
  ],
  "paging": {
    "page": 1,
    "total_page": 3,
    "total_item": 5
  }
}
```

Response Body Failed :

## Remove Products API

Endpoint : DELETE/api/products/:id

Headers :
-Authorization : token

Response Body Success :

```json
{
  "data": "DONE"
}
```

Response Body Failed :

```json
{
  "error": "Product is not found"
}
```
