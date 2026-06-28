# This endpoint has been Deprecated.
When integrating with the Zappy API, we recommend using the Rate, Consignment, and Label endpoints directly for obtaining quotes, creating consignments, and downloading labels. All orders are maintained in your own system; only labels are retrieved from Zappy.

# Create new Custom third-party orders
To use this API, please contact the administrator to apply for third-party integration (Custom) first.
You can upload a maximum of 20 pieces of data at a time.

- Endpoint: /api/2.0/custom/create
- Http Method: POST

## Required Parameters:
*order_id* - [Required,The id of the order]

*order_number* - [Required,Order code or name]

*create_time* - [Required,The time the order was created]

*recipient_address*
- **company_name** - [Optional, company name]
- **contact_name** - [Require, contact name]
- **email** - [Require, recipient email]
- **address_body** - [Require, unit number + street number + street name]
- **address_suburb** - [Require, suburb]
- **address_city** - [Require, city]
- **address_post_code** - [Require, postcode]
- **contact_number** - [Optional, contact phone]

*order_items* - [Required, a list of order item]
- **title** - [Require, product name]
- **product_price** - [Optional, product price]
- **quantity** - [Require, product quantity]
- **product_id** - [Optional, product id]
- **weight** - [Optional, product weight]
- **width** - [Optional, product width]
- **length** - [Optional, product length]
- **height** - [Optional, product height]
- **product_description** - [Optional, product description]
- **line_item_id** - [Optional, Line Number]

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
        "order_id":"000021",
        "order_number":"000021",
        "create_time":"2025-04-22 14:41:00",
        "recipient_address":{
            "company_name":"zappy",
            "contact_name":"pptest",
            "email":"123@xx.com",
            "address_body":"123 Pacific Drive",
            "address_suburb":"Fitzherbert",
            "address_city":"Palmerston North",
            "address_post_code":"4410",
            "contact_number":"23233434",
            "address_country":"NZ",
            "address_state" : "Palmerston"
        },
        "order_items":[
            {
                "title":"pro1",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro1",
                "sku": "12341234",
                "line_item_id":"1"

            },
            {
                "title":"pro2",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro1",
                "sku": "12341234",
                "line_item_id":"1"

            }
        ]


    },
    {
        "order_id":"000022",
        "order_number":"000022",
        "create_time":"2025-04-22 14:41:00",
        "recipient_address":{
            "company_name":"zappy",
            "contact_name":"pptest",
            "email":"123@xx.com",
            "address_body":"123 Pacific Drive",
            "address_suburb":"Fitzherbert",
            "address_city":"Palmerston North",
            "address_post_code":"4410",
            "contact_number":"23233434",
            "address_country":"NZ",
            "address_state" : "Palmerston"
        },
        "order_items":[
            {
                "title":"pro2",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro2",
                "sku": "12341234",
                "line_item_id":"1"

            },
            {
                "title":"pro3",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro2",
                "sku": "12341234",
                "line_item_id":"1"

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

- Endpoint: /api/2.0/custom/update
- Http Method: POST

## Required Parameters:
*order_id* - [Required,The id of the order]

*order_number* - [Required,Order code or name]

*create_time* - [Required,The time the order was created]

*recipient_address*
- **company_name** - [Optional, company name]
- **contact_name** - [Require, contact name]
- **email** - [Require, recipient email]
- **address_body** - [Require, unit number + street number + street name]
- **address_suburb** - [Require, suburb]
- **address_city** - [Require, city]
- **address_post_code** - [Require, postcode]
- **contact_number** - [Optional, contact phone]

*order_items* - [Required, a list of order item]
- **title** - [Require, product name]
- **product_price** - [Optional, product price]
- **quantity** - [Require, product quantity]
- **product_id** - [Optional, product id]
- **weight** - [Optional, product weight]
- **width** - [Optional, product width]
- **length** - [Optional, product length]
- **height** - [Optional, product height]
- **product_description** - [Optional, product description]
- **line_item_id** - [Optional, Line Number]

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
        "order_id":"000021",
        "order_number":"000021",
        "create_time":"2025-04-22 14:41:00",
        "recipient_address":{
            "company_name":"zappy",
            "contact_name":"pptest",
            "email":"123@xx.com",
            "address_body":"123 Pacific Drive",
            "address_suburb":"Fitzherbert",
            "address_city":"Palmerston North",
            "address_post_code":"4410",
            "contact_number":"23233434",
            "address_country":"NZ",
            "address_state" : "Palmerston"
        },
        "order_items":[
            {
                "title":"pro1",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro1",
                "sku": "12341234",
                "line_item_id":"1"

            },
            {
                "title":"pro2",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro1",
                "sku": "12341234",
                "line_item_id":"1"

            }
        ]


    },
    {
        "order_id":"000022",
        "order_number":"000022",
        "create_time":"2025-04-22 14:41:00",
        "recipient_address":{
            "company_name":"zappy",
            "contact_name":"pptest",
            "email":"123@xx.com",
            "address_body":"123 Pacific Drive",
            "address_suburb":"Fitzherbert",
            "address_city":"Palmerston North",
            "address_post_code":"4410",
            "contact_number":"23233434",
            "address_country":"NZ",
            "address_state" : "Palmerston"
        },
        "order_items":[
            {
                "title":"pro2",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro2",
                "sku": "12341234",
                "line_item_id":"1"

            },
            {
                "title":"pro3",
                "product_price":10.5,
                "quantity": 2,
                "product_id":"001",
                "weight": 10.5,
                "width": 2.2,
                "length": 3.4,
                "height": 3.3,
                "product_description": "pro2",
                "sku": "12341234",
                "line_item_id":"1"

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

- Endpoint: /api/2.0/custom/search
- Http Method: POST

## Required Parameters:
*keywords* - [Optional,keywords for querying data]

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
    "keywords":"",
    "pageNumber":1,
    "pageSize":10,
    "orderStatus":""
}
```
**Responses**

Responses A JSON encoded string.
``` json
{
    "isSuccess": true,
    "data": {
        "orders": [
            {
                "order_id": "000040",
                "order_number": "000040",
                "create_time": "2025-04-22T14:41:00",
                "order_status": "0",
                "recipient_address": {
                    "company_name": "zappy",
                    "address_country": null,
                    "address_state": null,
                    "contact_name": "pptest",
                    "email": "1058363699@qq.com",
                    "address_body": "123 Pacific Drive",
                    "address_suburb": "Fitzherbert",
                    "address_city": "Palmerston North",
                    "address_post_code": "4410",
                    "contact_number": "23233434"
                },
                "order_items": [
                    {
                        "title": "pro2",
                        "picture_link": null,
                        "quantity": 2,
                        "product_id": "001",
                        "product_description": "pro2",
                        "line_item_id": "1",
                        "sku": "12341234",
                        "product_price": 10.50,
                        "length": 3.4000,
                        "height": 3.3000,
                        "width": 2.2000,
                        "weight": 10.5000
                    },
                    {
                        "title": "pro3",
                        "picture_link": null,
                        "quantity": 2,
                        "product_id": "001",
                        "product_description": "pro2",
                        "line_item_id": "1",
                        "sku": "12341234",
                        "product_price": 10.50,
                        "length": 3.4000,
                        "height": 3.3000,
                        "width": 2.2000,
                        "weight": 10.5000
                    },
                    {
                        "title": "pro4",
                        "picture_link": null,
                        "quantity": 2,
                        "product_id": "001",
                        "product_description": "pro2",
                        "line_item_id": "1",
                        "sku": "12341234",
                        "product_price": 10.50,
                        "length": 3.4000,
                        "height": 3.3000,
                        "width": 2.2000,
                        "weight": 10.5000
                    },
                    {
                        "title": "pro5",
                        "picture_link": null,
                        "quantity": 2,
                        "product_id": "001",
                        "product_description": "pro2",
                        "line_item_id": "1",
                        "sku": "12341234",
                        "product_price": 10.50,
                        "length": 3.4000,
                        "height": 3.3000,
                        "width": 2.2000,
                        "weight": 10.5000
                    },
                    {
                        "title": "pro5",
                        "picture_link": null,
                        "quantity": 2,
                        "product_id": "001",
                        "product_description": "pro2",
                        "line_item_id": "1",
                        "sku": "12341234",
                        "product_price": 10.50,
                        "length": 3.4000,
                        "height": 3.3000,
                        "width": 2.2000,
                        "weight": 10.5000
                    }
                ]
            }
        ],
        "total": 20
    }
}
```

***





