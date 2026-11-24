# Stock Level – Deprecated. Stock levels are now updated via webhook. Please contact us to arrange setup.

Request for all stock levels or for one specified product.

- URL: /Stock
- Http Method: Post

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* **Barcode** - [Optional]  

## Response：
*Data* - [A list of stock level]
- **Barcode** 
- **ProductName**
- **AvailableStock**


## Example

**Request Headers**
```
Content-Type: application/json;
```

**Request Authorization**
```
Bearer:XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI87iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z
```

**Request Body**
``` json
{
    "Barcode": "I-001"
}
```

**Responses**
``` json
{
    "IsSuccess": true,
    "Data": [
        {
            "Barcode": "I-001",
            "ProductName": "Product with an expiration date",
            "AvailableStock": 4278
        }
    ]
}
```
