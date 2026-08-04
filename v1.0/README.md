# Zappy System API(v1.0)

ZappyAPI provides an access to enable your customer to send parcels using our system.

***

### UAT URL: https://test-api.zappy.nz  
### Live URL: https://api.zappy.nz  

# Get token
Allows third-party systems to get Zappy customers’ API authorization token from Zappy System. The token will expire in 30Mins

Endpoint: /token

## Required Parameters:
- username [Required]
- password [Required]
- grant_type [Required, must be '*password*']

## Example
Request 
POST https://api.zappy.nz/token

**Headers**
```
Content-Type: application/json;
```

**x-www-form-urlencoded**
``` json
{
    "username":"Test",
    "password":"Password",
    "grant_type": "password"
}
```

**Responses**
``` json
{
    "isSuccess": true,
    "accessToken": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI8iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "access_token": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI8iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "expiresIn": 86399,
    "tokenType": "bearer"
}
```

***

# Get token using client credentials
Log in to the Zappy website first. Then, add your client credentials on the 'Settings -> API Secret Key' page. 
Utilize the added 'ClientId' and 'Secret' to obtain the access token through the following endpoint: /token   

## Required Parameters:
- client_id [Required]
- client_secret [Required]
- grant_type [Required, must be '*client_credentials*']

## Example
Request 
POST https://api.zappy.nz/token

**Headers**
```
Content-Type: application/json;
```

**x-www-form-urlencoded**
``` json
{
    "client_id":"XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv",
    "client_secret":"GyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6D==",
    "grant_type": "client_credentials"
}
```

**Responses**
``` json
{
    "isSuccess": true,
    "accessToken": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI8iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "access_token": "XlES6IXxqQZwo37CoB9ydlZmWQV84VdNhv-MF0WXpr9SUJqv3bL5CsBIDTqrDildBRBkzo6J2VmbdGyZu7yBGANnCUVMDzxelycDQXn9xBxqobDBAVs70nslc4C90PJ6jmtEI56U5SD8ms5c7ubKOa6DR0rLb_GTY4kXitqHPsPpCaUKckwGSIyCwGeZcAx60A50Na2CTISg5CfCGFTTAOQ6znVRLkJIb4fbbI8iYkBLDbQb2S09iFAqMc0odR9lpziU3BS5y41fZBXHwUUCEwk2-EFs7RFS_L6WT0zRcBSlwluqGchGuiLCg7d3NT1bZEPcf8u_BQFc_Wnkjd_pf4RHdt7pBHa6mgDib5ao1hugdE5z",
    "expiresIn": 86399,
    "tokenType": "bearer"
}
```

# API Rate Limits
| Endpoint | Policy Type | Per Second | Per Minute |
| --- | --- | --- | --- |
| `/token` | Endpoint | 5 | 50 |
| `/api/1.0/shippingoptions` | Endpoint | 1 | 30 |
| `/api/1.0/consignment` | Endpoint | 1 | 30 |
| `/api/1.0/labels` | Endpoint | 1 | 30 |
| `/api/1.0/bookings` | Endpoint | 1 | 30 |
| `/api/1.0/tracking` | Endpoint | 1 | 30 |
| `/api/1.0/thirdpartyorders` | Endpoint | 1 | 30 |

***

# Shipping
- **[<code style="background-color:#009D77">POST</code> /api/1.0/shippingoptions](Shipping/GetShippingMethod.md)** returns a list of available shipping methods

# Make a consignment
- **[<code style="background-color:#E97500">PUT</code> /api/1.0/consignment](Consignment/PostConsignment.md)** Put a consignment

# Label
- **[<code style="background-color:#1391FF">GET</code> /api/1.0/labels](Label/GetLabel.md)** Get a url of label(PDF)

# Booking
- **[<code style="background-color:#009D77">POST</code> /api/1.0/bookings](Booking/PostBooking.md)** Booking a pickup time

# Tracking
- **[<code style="background-color:#1391FF">GET</code> /api/1.0/tracking](Tracking/GetTracking.md)** Get tracking history of the consignment

# Third Party orders
- **[<code style="background-color:#E97500">PUT</code> /api/1.0/thirdpartyorders](ThirdPartyOrders/PutThirdPartyOrders.md)** Put a list of third party orders
