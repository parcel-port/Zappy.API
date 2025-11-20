# Create a new consignment

Allows third-party systems to make consignments and get consignment tracking
numbers based on the passed QuoteRequestUuid and CarrierMethodId. 

- Endpoint: /api/2.0/consignmentcreate
- Http Method: POST

*This API can only be called after the API authentication is approved (the correct
auth string has been passed). 

## Required Parameters:
* QuoteRequestUuid [Require, value from /api/consignment/quote]
* CarrierMethodId [Require, value from /api/consignment/quote, e.g. "ft_freight"]
* ThirdPartyOrderIds [Optional, Third-party order ID]
* BatchConsignmentId [Optional, Batch Consignment Id]
* IsSignature [Optional, 0 - No Signature required; 1 - Signature required]
* IsATL [Optional, 0 - No Authority to leave; 1 - Authority to leave]
* EncryptedConsignmentRef [Optional, Encrypted consignmentRef]
* EmailLabel [Optional, Email a return link]
* AsendiaDropOffPointsId [Optional, Asendia Drop Off Points Id]



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
    "QuoteRequestUuid": "7084b2c573e94628a09fde007fd39914",
    "CarrierMethodId": "ft_freight"
}


```

**Responses**
A JSON encoded string contains all the valid shipping methods with shipping method ids.
The requestID need to be added in the request when you create a consignment, and it will be expired.

``` json
{
    "IsSuccess": true,
    "Data": {
        "Success": true,
        "ErrorMessage": null,
        "ConsignmentRef": "000020000040",
        "ConsignmentId": null,
        "InfoMessage": null
    }
}
```





