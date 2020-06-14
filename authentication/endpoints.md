# REST Endpoints for the Authentication WEB API

### Get Tokens
Method: POST
Expected request body:
```json
{
    "credentials": {
        "email": "ben@vyrz.dev",
        "password": "test",
        "captchaCode": "Should be passed in, only in production."
    }
}
```
Expected Response if credentials correct:
```json
{
    "access_token": "A JWT Auth Token valid for 50 seconds",
    "refresh_token": "A JWT Auth Token valid for 2 hours"
}
```
---------------------------------------------------------------------------------
### Refresh Access Token
Method: POST & GET

- Make an empty request with your refresh_token in your auth header.

Expected Response:
```json
{
    "access_token": "A JWT Auth Token valid for 50 seconds"
}
```
---------------------------------------------------------------------------------

### List Refresh Tokens
Method: GET & POST

- Make an empty request with your access_token in your auth header.

Expected Response:
```json
{
    "tokens": [
        {
            "tokenJTI": "4356879021428734608139",
            "expiresAt": "UTC Timestamp of Expiry"
        }
    ]
}
```
---------------------------------------------------------------------------------

### Invalidate a specific token
Method: POST

Expected Request:
```json
{
    "token_jti": "The JTI of the refresh_token you wish to invalidate."
}
```
---------------------------------------------------------------------------------

### Invalidate all tokens
Method: GET & POST

- Send an empty request with your access_token in auth header.

Expected Response:
```json
{
    "msg": "All Refresh tokens have been invalidated"
}
```

