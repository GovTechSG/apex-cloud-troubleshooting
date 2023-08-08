# JWT Authentication Error Codes

If you encounter errors during the JWT authentication process,  refer to the tables below to help you get more information on the root cause of the error.

- [Pre-Authentication Errors](#pre-authentication-errors)
- [Authentication Errors](#authentication-errors)

?> **Note:** You can collapse the left sidebar navigation for a better view of the tables.

## Pre-authentication errors 
| Errors| Error Code | Error Name | Error / Issue | Tested Result (Code / Error Body) | Comments |
|---|---|---|---|---|---|
| 403/432 | Client Error | JWKS download error | Unable to download JWKS from endpoint. Please check that the URL is valid and is reachable. | |
| 433 | Client Error | Invalid JWKS in Application | Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. Please ensure that JWKS is of valid JSON format and the keys are lower case. | |
| 434 | Client Error | JWT header is missing | JWT header is missing. Please test with webhook.site to ensure JWT header is present. | |
| 435 | Client Error | Invalid JWT format | Invalid JWT format. Please double-check JWT with [JWT.io](https://jwt.io/). | |
| 436 | Client Error | Missing ‘iss’ claim | Invalid JWT format. Please ensure that iss claim is present and has the API Key(s). | |
| 437 | Client Error | Unable to find Key Id in JWKS | Invalid kid claim. Please ensure that kid claim exists and key ID exists in JWKS, and take note of JWKS caching time of 1 hour. | |
| 438 | Client Error | Invalid ‘alg’ claim - algorithm | Invalid kid claim. Please ensure that kid claim exists and key ID exists in JWKS, and take note of JWKS caching time of 1 hour. | Not RS256 or ES256<br>Missing alg+: (alg missing is not possible to test due to library) |
| 439 | Client Error | Invalid ‘typ’ claim or JWT Type | Invalid JWT format. Please ensure that typ claim is valid. | |
| 440 | Client Error | Missing API Key | Invalid JWT format. Please ensure that iss claim is present and has the API Key(s). | |
| 441 | Client Error | Missing ‘iat’ claim | Invalid JWT format. Please ensure that iat claim is valid. Please ensure your application is synced to global NTP service. | |
| 442 | Client Error | Missing ‘aud’ claim | Invalid JWT format. Please ensure that aud claim is valid. Please ensure this is URL of API and query parameters are not included. | |
| 443 | Client Error | Missing ‘jti’ claim | Invalid JWT format. Please ensure that jti claim is valid and not reused. | |
| 445 | Client Error | Missing ‘sub’ claim | Invalid JWT format. Please ensure that sub claim is valid. Please ensure the sub claim matches method of API call in upper caps. | |
| 446 | Client Error | Missing data hash claim | Invalid JWT format. Please ensure that data claim is valid. Please subscribe and test with /helloworld/sha256 to ensure your hash matches. | |
| 447 | Client Error | Missing ‘exp’ claim | Invalid exp claim. Please ensure that exp claim is present, not expired and is less than or equal to 180 from iat claim. | 

## Authentication errors

| Error Code | Error Name | Error / Issue | Tested Result (Code / Error Body) | Comments |
|---|---|---|---|---|
| 450 | Client Error | Authentication Error - Invalid API Key | Authentication Error - Invalid API Key.  Please double-check API key and ensure Application is subscribed to API. | |
| 452 | Client Error | Authentication Error - Signature | Authentication Error - JWT signature. Ensure JWT is signed with correct key.  Please double-check jwt is signed correctly with jwt.io. | |
