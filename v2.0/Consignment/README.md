# Create a new consignment

Allows third-party systems to make consignments and get consignment tracking
numbers based on the passed quoteRequestId and carrierMethodId. 

- Endpoint: /api/2.0/consignment
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* quoteRequestId [Require, value from /api/2.0/rate]
* carrierMethodId [Require, value from /api/2.0/rate, e.g. "CPOLTPA5"]
* emailToRecipient [Optional, 0 or 1, 1 if email to recipient]

*Booking*
- **pickupOption** [Optional, 0 or 1, default 1 for booking later, 0 if booking now]
- **pickupDate** [Optional, default DateTime.Now]


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
  "quoteRequestId": "f7788fac-b4e0-478d-93ab-028a10f27d22",
  "carrierMethodId": "CPOLTPA5",
  "emailToRecipient": "1"
//   "booking":{
    // "pickupOption": "0",
    // "pickupDate": "2022/09/20 12:30"
//   }
}
```

**Responses**
A JSON encoded string contains all the valid shipping methods with shipping method ids.
The requestID need to be added in the request when you create a consignment, and it will be expired.

``` json
{
    "isSuccess": true,
    "data": {
        "consignmentRef": [
            "007862954443"
        ],
        "consignmentTrackingRef": [
            "2541300295444301AKL003AN"
        ],
        "totalPrice": 4.82,
        "totalGst": 0.73
    }
}
```

***
