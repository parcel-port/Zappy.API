# Create new Custom third-party orders
To use this API, please contact the administrator to apply for third-party integration (Custom) first.
You can upload a maximum of 20 pieces of data at a time.

- Endpoint: api/Custom/Create
- Http Method: POST

## Required Parameters:
*OrderId* - [Required,The id of the order]

*OrderNumber* - [Required,Order code or name]

*CreateAt* - [Required,The time the order was created]

*Address*
- **CompanyName** - [Optional, company name]
- **Name** - [Require, contact name]
- **Email** - [Require, recipient email]
- **Street** - [Require, unit number + street number + street name]
- **Suburb** - [Require, suburb]
- **City** - [Require, city]
- **Postcode** - [Require, postcode]
- **State** - [Require, State]
- **Country** - [Require,Country]
- **Phone** - [Optional, contact phone]

*ThirdPartyOrderItems* - [Required, a list of order item]
- **Name** - [Require, product name]
- **ImgUrl** - [Optional, Image Url]
- **Quantity** - [Require, product quantity]
- **ProductId** - [Optional, product id]
- **Weight** - [Optional, product weight]
- **Width** - [Optional, product width]
- **Length** - [Optional, product length]
- **Height** - [Optional, product height]
- **Sku** - [Optional, product sku]
- **LineItemId** - [Optional, Line Number]

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

[
    {
    "OrderId":"0000004",
    "OrderNumber":"0000004",
    "CreateAt":"2025-04-28 15:27:00",
    "Address":{
        "Name":"TT",
        "CompanyName":"Zappy",
        "Phone":"234234234",
        "Email":"34343@zappy.com",
        "Street":"123 Parkyn Parade",
        "Suburb": "Mooloolaba",
        "City":"Mooloolaba",
        "State":"QLD",
        "Postcode":"4557",
        "Country":"AU",
        "Instruction":"test"
    },
    "ThirdPartyOrderItems":[
            {
                "Name":"pro 1",
                "ImgUrl":"",
                "Length":0,
                "Width":0,
                "Height":0,
                "Weight":0,
                "ProductId":"234234",
                "LineItemId":"0000001",
                "Quantity":1
            }

        ]

    },
    {
    "OrderId":"0000005",
    "OrderNumber":"0000005",
    "CreateAt":"2025-04-28 15:27:00",
    "Address":{
        "Name":"TT",
        "CompanyName":"Zappy",
        "Phone":"234234234",
        "Email":"34343@zappy.com",
        "Street":"123 Parkyn Parade",
        "Suburb": "Mooloolaba",
        "City":"Mooloolaba",
        "State":"QLD",
        "Postcode":"4557",
        "Country":"AU",
        "Instruction":"test"
    },
    "ThirdPartyOrderItems":[
            {
                "Name":"pro 1",
                "ImgUrl":"",
                "Length":0,
                "Width":0,
                "Height":0,
                "Weight":0,
                "ProductId":"234234",
                "LineItemId":"0000001",
                "Quantity":1
            }

        ]

    }

]

```

**Responses**

Responses A JSON encoded string.
``` json
{
    "isSuccess": true
}
```

***


# Update Custom third-party orders
To use this API, please contact the administrator to apply for third-party integration (Custom) first.
You can upload a maximum of 20 pieces of data at a time.

- Endpoint: /api/Custom/Update
- Http Method: POST

## Required Parameters:
*OrderId* - [Required,The id of the order]

*OrderNumber* - [Required,Order code or name]

*CreateAt* - [Required,The time the order was created]

*Address*
- **CompanyName** - [Optional, company name]
- **Name** - [Require, contact name]
- **Email** - [Require, recipient email]
- **Street** - [Require, unit number + street number + street name]
- **Suburb** - [Require, suburb]
- **City** - [Require, city]
- **Postcode** - [Require, postcode]
- **State** - [Require, State]
- **Country** - [Require,Country]
- **Phone** - [Optional, contact phone]

*ThirdPartyOrderItems* - [Required, a list of order item]
- **Name** - [Require, product name]
- **ImgUrl** - [Optional, Image Url]
- **Quantity** - [Require, product quantity]
- **ProductId** - [Optional, product id]
- **Weight** - [Optional, product weight]
- **Width** - [Optional, product width]
- **Length** - [Optional, product length]
- **Height** - [Optional, product height]
- **Sku** - [Optional, product sku]
- **LineItemId** - [Optional, Line Number]

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

[
    {
    "OrderId":"0000004",
    "OrderNumber":"0000004",
    "CreateAt":"2025-04-28 15:27:00",
    "Address":{
        "Name":"TT",
        "CompanyName":"Zappy",
        "Phone":"234234234",
        "Email":"34343@zappy.com",
        "Street":"123 Parkyn Parade",
        "Suburb": "Mooloolaba",
        "City":"Mooloolaba",
        "State":"QLD",
        "Postcode":"4557",
        "Country":"AU",
        "Instruction":"test"
    },
    "ThirdPartyOrderItems":[
            {
                "Name":"pro 1",
                "ImgUrl":"",
                "Length":0,
                "Width":0,
                "Height":0,
                "Weight":0,
                "ProductId":"234234",
                "LineItemId":"0000001",
                "Quantity":1
            }

        ]

    },
    {
    "OrderId":"0000005",
    "OrderNumber":"0000005",
    "CreateAt":"2025-04-28 15:27:00",
    "Address":{
        "Name":"TT",
        "CompanyName":"Zappy",
        "Phone":"234234234",
        "Email":"34343@zappy.com",
        "Street":"123 Parkyn Parade",
        "Suburb": "Mooloolaba",
        "City":"Mooloolaba",
        "State":"QLD",
        "Postcode":"4557",
        "Country":"AU",
        "Instruction":"test"
    },
    "ThirdPartyOrderItems":[
            {
                "Name":"pro 1",
                "ImgUrl":"",
                "Length":0,
                "Width":0,
                "Height":0,
                "Weight":0,
                "ProductId":"234234",
                "LineItemId":"0000001",
                "Quantity":1
            }

        ]

    }

]

```
**Responses**

Responses A JSON encoded string.
``` json
{
    "isSuccess": true
}
```

***

# Search third-party orders
To use this API, please contact the administrator to apply for third-party integration (Custom) first.

- Endpoint: /api/Custom/Search
- Http Method: POST

## Required Parameters:
*keyword* - [Optional,keywords for querying data]

*orderStatus* - [Optional,Third-party order status]

*pageNumber* - [Require,page number,Integer greater than 0]

*pageSize* - [Require,page size,Integer greater than 0,Maximum value 50]

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
    "keyword":"",
    "pageNumber":1,
    "pageSize":10,
    "orderStatus":""
}
```
**Responses**

Responses A JSON encoded string.
``` json

{
    "IsSuccess": true,
    "Data": {
        "TotalCount": 5,
        "PageNumber": 1,
        "PageSize": 10,
        "DataList": [
            {
                "OrderId": "0000001",
                "OrderNumber": "0000001",
                "CreateAt": "2025-04-28T15:27:00",
                "Status": "0",
                "Address": {
                    "Street": "123 Parkyn Parade",
                    "Suburb": "Mooloolaba",
                    "City": "Mooloolaba",
                    "State": "QLD",
                    "Postcode": "4557",
                    "Country": "AU",
                    "Name": "DD",
                    "CompanyName": "Zappy",
                    "Phone": "234234234",
                    "Email": "34343@zappy.com",
                    "Instruction": "test"
                },
                "ThirdPartyOrderItems": [
                    {
                        "Name": "pro 1",
                        "ImgUrl": "",
                        "Quantity": 1,
                        "Length": 0.00,
                        "Width": 0.00,
                        "Height": 0.00,
                        "Weight": 0.000,
                        "ProductId": "",
                        "LineItemId": "",
                        "Sku": null
                    }
                ]
            },
            {
                "OrderId": "0000002",
                "OrderNumber": "0000002",
                "CreateAt": "2025-04-28T15:27:00",
                "Status": "0",
                "Address": {
                    "Street": "123 Parkyn Parade",
                    "Suburb": "Mooloolaba",
                    "City": "Mooloolaba",
                    "State": "QLD",
                    "Postcode": "4557",
                    "Country": "AU",
                    "Name": "SS",
                    "CompanyName": "Zappy",
                    "Phone": "234234234",
                    "Email": "34343@zappy.com",
                    "Instruction": "test"
                },
                "ThirdPartyOrderItems": [
                    {
                        "Name": "pro 1",
                        "ImgUrl": "",
                        "Quantity": 1,
                        "Length": 0.00,
                        "Width": 0.00,
                        "Height": 0.00,
                        "Weight": 0.000,
                        "ProductId": "",
                        "LineItemId": "",
                        "Sku": null
                    }
                ]
            },
                     
            

        ]

    }
}

```

***
