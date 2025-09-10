# Zappy System API(v2.0)

Zappy API provides an access to enable your customer to send parcels using our system.

Try it in [Postman](https://zappy-nz.postman.co/network/import?collection=9251978-78b291be-1ec4-4f58-a552-529f512c233e-2sB2j3BrhD&referrer=https%3A%2F%2Fdocumenter.getpostman.com%2Fview%2F9251978%2F2sB2j3BrhD&versionTag=latest&environment=9251978-179ba691-cb46-4ef2-abb3-de8caaea1ca9-2sB2j3BrhD&source=documenter&traceId=7ab58a82-b219-4ba5-98a0-dc9c5e28e749). Please make sure to use the Zappy API environment that has been provided.
***

### URL: https://api.zappy.nz  

# Get token 
Allows third-party systems to get Zappy customers’ API authorization token from Zappy System. The token will expire in 1 day.  
- Log in to the Zappy website first. Then, add your client credentials on the 'Settings -> API Secret Key' page. 
- Utilize the added 'ClientId' and 'Secret' to obtain the access token via the following endpoint: /token   

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

***

# Get rates
- **[<code style="background-color:#009D77">POST</code> /api/2.0/rate](Rate/README.md)** returns a list of rate

# Create a consignment
- **[<code style="background-color:#009D77">POST</code> /api/2.0/consignment](Consignment/README.md)** Create a consignment

# Download label
- **[<code style="background-color:#009D77">POST</code> /api/2.0/label](Label/README.md)** Get a url of label(PDF)

# Booking pickup
- **[<code style="background-color:#009D77">POST</code> /api/2.0/booking](Booking/README.md)** Booking a pickup time

# Tracking
- **[<code style="background-color:#009D77">POST</code> /api/2.0/tracking](Tracking/README.md)** Get tracking history of the consignment
