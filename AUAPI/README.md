# Zappy System API

Zappy API provides an access to enable your customer to send parcels using our system.

***

### URL: https://api.zappy.au  

# Get token using client credentials
Log in to the Zappy website first. Then, add your client credentials on the 'Settings -> API Secret Key' page. 
Utilize the added 'ClientId' and 'Secret' to obtain the access token via the following endpoint: /api/auth/token 

- Endpoint: /api/auth/token
- Http Method: POST

## Required Parameters:
- ClientId [Required]
- ClientSecret [Required]
- GrantType [Required, must be '*client_credentials*']
- CompanyName [Required]
  
## Example
Request 
POST https://api.zappy.au/api/auth/token

**Headers**
```
Content-Type: application/json;
```
**Body Raw**
``` json
{
    "ClientId":"9DC2DD08D6EC43A4B8693B0DAD9394C9",
    "ClientSecret":"7DU3CR6JSB+B76JPRRL82WMXW7BMP5ZMXA==",
    "GrantType": "client_credentials",
    "CompanyName": "Zappy"
}
```

**Responses**
``` json
{
    "IsSuccess": true,
    "Data": {
        "AccessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxZjYxNWM0OC0yMWIxLTQyOWUtYWZlNy1iNDljYjNkZDllY2IiLCJuYW1lIjoiSVQgVGVzdCIsImVtYWlsIjoidGVzdEBzaGlwemFwcHkuY29tIiwicGhvbmVfbnVtYmVyIjoiMDAwMDAwMDAiLCJodHRwOi8vc2NoZW1hcy5taWNyb3NvZnQuY29tL3dzLzIwMDgvMDYvaWRlbnRpdHkvY2xhaW1zL3JvbGUiOiJVc2VyIiwidXNlcklkIjoiMDAyZmVhZDQ2ZmIxNDY5YmI1NGJmMjlhNDI0NDM4MmUiLCJjb21wYW55SWQiOiIyIiwiZXhwIjoxNzIxODA0ODE4LCJpYXQiOjE3MjE3MTg0MTgsIm5iZiI6MTcyMTcxODQxOH0.yylbHq8RUMyXoKycvShHKFHRL2XjkKGc5J-T07nUR5w",
        "TokenType": "bearer",
        "ExpiresIn": 86400
    }
}
```

***

# Get rates
- **[<code style="background-color:#009D77">POST</code> /api/consignment/quote](Rate/README.md)** returns a list of rate

# Create a consignment
- **[<code style="background-color:#009D77">POST</code> /api/consignment/create](Consignment/README.md)** Create a consignment

# Download label
- **[<code style="background-color:#009D77">GET</code> /api/consignment/label](Label/README.md)** Get a url of label(PDF)

# Booking pickup
- **[<code style="background-color:#009D77">POST</code> /api/consignment/book](Booking/README.md)** Booking a pickup time

# Tracking
- **[<code style="background-color:#009D77">GET</code> /api/consignment/trackinghistory](Tracking/README.md)** Get tracking history of the consignment
