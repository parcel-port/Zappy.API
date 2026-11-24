# Zappy 3PL System API(v2.0)

Zappy 3PL API provides an access to enable you to manage your inventories using our system.

***

## UAT URL: https://test-api-3pl.zappy.nz/api  
## Live URL: https://api-3pl.zappy.nz/api  

***

## Common response (Json)

*IsSuccess*  - ['*True*' - Success, '*False*' - Has errors]  
*StatusCode* - [An error code. Included only if the '*IsSuccess*' is '*False*']  
*Errors* - [A list of error messages. Included only if the '*IsSuccess*' is '*False*']  
*Data* - [Optional. Included only if the '*IsSuccess*' is '*True*']  

***
# Get token
Please contact your account manager to obtain your access credentials.   
Then, use the 'AccessId' and 'SecretAccessKey' to obtain the access token via the following URL:  

- URL: /Auth/Token
- Http Method: POST

## Required Parameters:
- GrantType [Required, must be '*client_credentials*']
- AccessId [Required]
- SecretAccessKey [Required]
- CompanyName [Required]

## Example
**Request Headers**
```
Content-Type: application/json;
```

**Request Body [json]**
```
{
    "GrantType": "client_credentials",
    "AccessId": "F636AF63593AD39F52B",
    "SecretAccessKey": "Z4ZSS4RQ2IDCLR8BOE/5ERFDTWMIEXPMVA==",
    "CompanyName": "Test Company"
}
```

**Responses**
``` json
{
    "IsSuccess": true,
    "Data": {
        "AccessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJkNGUwMzVhZS1kMzI5LTQ4YWItOGM3NC1lNzNhZmUxYzY3YTQiLCJuYW1lIjoiVGVzdCBDb21wYW55IiwiYWNjZXNzSWQiOiJGNjM2QUY2MzU5MzE0RjM2QkNGMjlBRDJBRDM5RjUyQiIsImNvbXBhbnlJZCI6IjIiLCJleHAiOjE3MDY3Mzc0MzYsImlhdCI6MTcwNjY1MTAzNiwibmJmIjoxNzA2NjUxMDM2fQ.oZLhRFeuUTaDkxnBTj0mDoRtIrH9x3XRpXd85IH8m_w",
        "TokenType": "bearer",
        "ExpiresIn": 86400
    }
}
```


# Outwards
- **[<code style="background-color:#009D77">POST</code> /Outwards](Outwards/README.md)** Creates an outwards request.
# Stock Level
- Please contact us to arrange the setup of your StockLevel webhook.
# Outwards Order Tracking
- Please contact us to arrange the setup of your Tracking webhook.
