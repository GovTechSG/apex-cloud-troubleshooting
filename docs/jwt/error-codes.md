# JWT Authentication Error Codes

If you encounter errors during the JWT authentication process, you can take note of the error code defined in the error and refer to the tables below to help you get more information on the root cause of the error.

- [Pre-Authentication Errors](#pre-authentication-errors)
- [Authentication Errors](#authentication-errors)
- [Post-Authentication Errors](#post-authentication-errors)
- [Security Errors](#security-errors)

**Legend:**<br>
(**+**) - Test not scripted<br>
(<b>**</b>) - Consider validation checks

?> **Note:** You can collapse the left sidebar navigation for a better view of the tables.

## Pre-Authentication Errors

| Error Code | Error Name | Error / Issue | Tested Result (Code / Error Body) | Comments |
|---|---|---|---|---|
| 403/432 | Client Error | Unable to download JWKS from endpoint. Please check that URL is valid and is reachable. | 403 |  |
| 433 | Client Error | Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. | 433<br>Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. |  |
| 434 | Client Error | JWT header is missing. | 434<br>JWT header is missing. |  |
| 435 | Client Error | Invalid JWT format. | 435<br>Invalid JWT format. Please double-check JWT with jwt.io. |  |
| 436 | Client Error | Missing 'iss' claim. | 436<br>Invalid JWT format. Please ensure that iss claim is valid. |  |
| 437 | Client Error | Unable to find Key Id in JWKS. | 437<br>1) Invalid JWT format. Please ensure that kid claim is valid.<br>2) Invalid kid claim. Please ensure that key ID exists in JWKS. |  |
| 438 | Client Error | Invalid 'alg' claim - algorithm. | 438<br>Invalid JWT format. Please ensure that alg claim is valid and is of value 'ES256' or 'RS256'. | Not RS256 or ES256<br>Missing alg+: (alg missing not possible to test due to library) |
| 439 | Client Error | Invalid 'typ' claim or JWT Type. | 439<br>Invalid JWT format. Please ensure that typ claim is valid. |  |
| 440 | Client Error | Missing API Key. | 440<br>Missing API Key in 'iss' claim. |  |
| 441 | Client Error | Missing 'iat' claim. | 441<br>Invalid JWT format. Please ensure that iat claim is valid. |  |
| 442 | Client Error | Missing 'aud' claim. | 442<br>Invalid JWT format. Please ensure that aud claim is valid. |  |
| 443 | Client Error | Missing 'jti' claim. | 443 |  |
| 445 | Client Error | Missing 'sub' claim. | 445<br>Invalid JWT format. Please ensure that sub claim is valid. |  |
| 446 | Client Error | Missing data hash claim. | 446<br>Invalid JWT format. Please ensure that data claim is valid. |  |
| 447 | Client Error | Missing 'exp' claim. | 447<br>Invalid exp claim. Please ensure that exp claim exists and JWT is not expired. |  |
| 400 | Bad Request | JWKS not provided for cross-zone.+ |  |  |
| 400 | Bad Request | AUD not provided for cross-zone.+ |  |  |

## Authentication Errors

| Error Code | Error Name | Error / Issue | Tested Result (Code / Error Body) | Comments |
|---|---|---|---|---|
| 403/432 | Client Error | Unable to download JWKS from endpoint. Please check that URL is valid and is reachable. | 403 |  |
| 433 | Client Error | Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. | 433<br>Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. |  |
| 434 | Client Error | JWT header is missing. | 434<br>JWT header is missing. |  |
| 435 | Client Error | Invalid JWT format. | 435<br>Invalid JWT format. Please double-check JWT with jwt.io. |  |
| 436 | Client Error | Missing 'iss' claim. | 436<br>Invalid JWT format. Please ensure that iss claim is valid. |  |
| 437 | Client Error | Unable to find Key Id in JWKS. | 437<br>1) Invalid JWT format. Please ensure that kid claim is valid.<br>2) Invalid kid claim. Please ensure that key ID exists in JWKS. |  |
| 438 | Client Error | Invalid 'alg' claim - algorithm. | 438<br>Invalid JWT format. Please ensure that alg claim is valid and is of value 'ES256' or 'RS256'. | Not RS256 or ES256<br>Missing alg+: (alg missing not possible to test due to library) |
| 439 | Client Error | Invalid 'typ' claim or JWT Type. | 439<br>Invalid JWT format. Please ensure that typ claim is valid. |  |
| 440 | Client Error | Missing API Key. | 440<br>Missing API Key in 'iss' claim. |  |
| 441 | Client Error | Missing 'iat' claim. | 441<br>Invalid JWT format. Please ensure that iat claim is valid. |  |
| 442 | Client Error | Missing 'aud' claim. | 442<br>Invalid JWT format. Please ensure that aud claim is valid. |  |
| 443 | Client Error | Missing 'jti' claim. | 443 |  |
| 445 | Client Error | Missing 'sub' claim. | 445<br>Invalid JWT format. Please ensure that sub claim is valid. |  |
| 446 | Client Error | Missing data hash claim. | 446<br>Invalid JWT format. Please ensure that data claim is valid. |  |
| 447 | Client Error | Missing 'exp' claim. | 447<br>Invalid exp claim. Please ensure that exp claim exists and JWT is not expired. |  |
| 400 | Bad Request | JWKS not provided for cross-zone.+ |  |  |
| 400 | Bad Request | AUD not provided for cross-zone.+ |  |  |

## Post-authentication Errors

| Error Code | Error Name | Error / Issue | Tested Result (Code / Error Body) | Comments |
|---|---|---|---|---|
| 403/432 | Client Error | Unable to download JWKS from endpoint. Please check that URL is valid and is reachable. | 403 |  |
| 433 | Client Error | Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. | 433<br>Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. |  |
| 434 | Client Error | JWT header is missing. | 434<br>JWT header is missing. |  |
| 435 | Client Error | Invalid JWT format. | 435<br>Invalid JWT format. Please double-check JWT with jwt.io. |  |
| 436 | Client Error | Missing 'iss' claim. | 436<br>Invalid JWT format. Please ensure that iss claim is valid. |  |
| 437 | Client Error | Unable to find Key Id in JWKS. | 437<br>1) Invalid JWT format. Please ensure that kid claim is valid.<br>2) Invalid kid claim. Please ensure that key ID exists in JWKS. |  |
| 438 | Client Error | Invalid 'alg' claim - algorithm. | 438<br>Invalid JWT format. Please ensure that alg claim is valid and is of value 'ES256' or 'RS256'. | Not RS256 or ES256<br>Missing alg+: (alg missing not possible to test due to library) |
| 439 | Client Error | Invalid 'typ' claim or JWT Type. | 439<br>Invalid JWT format. Please ensure that typ claim is valid. |  |
| 440 | Client Error | Missing API Key. | 440<br>Missing API Key in 'iss' claim. |  |
| 441 | Client Error | Missing 'iat' claim. | 441<br>Invalid JWT format. Please ensure that iat claim is valid. |  |
| 442 | Client Error | Missing 'aud' claim. | 442<br>Invalid JWT format. Please ensure that aud claim is valid. |  |
| 443 | Client Error | Missing 'jti' claim. | 443 |  |
| 445 | Client Error | Missing 'sub' claim. | 445<br>Invalid JWT format. Please ensure that sub claim is valid. |  |
| 446 | Client Error | Missing data hash claim. | 446<br>Invalid JWT format. Please ensure that data claim is valid. |  |
| 447 | Client Error | Missing 'exp' claim. | 447<br>Invalid exp claim. Please ensure that exp claim exists and JWT is not expired. |  |
| 400 | Bad Request | JWKS not provided for cross-zone.+ |  |  |
| 400 | Bad Request | AUD not provided for cross-zone.+ |  |  |

## Security Errors

| Error Code | Error Name | Error / Issue | Tested Result (Code / Error Body) | Comments |
|---|---|---|---|---|
| 403/432 | Client Error | Unable to download JWKS from endpoint. Please check that URL is valid and is reachable. | 403 |  |
| 433 | Client Error | Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. | 433<br>Invalid JWKS in Application. Please ensure that JWKS is correct and is of the correct algorithm. |  |
| 434 | Client Error | JWT header is missing. | 434<br>JWT header is missing. |  |
| 435 | Client Error | Invalid JWT format. | 435<br>Invalid JWT format. Please double-check JWT with jwt.io. |  |
| 436 | Client Error | Missing 'iss' claim. | 436<br>Invalid JWT format. Please ensure that iss claim is valid. |  |
| 437 | Client Error | Unable to find Key Id in JWKS. | 437<br>1) Invalid JWT format. Please ensure that kid claim is valid.<br>2) Invalid kid claim. Please ensure that key ID exists in JWKS. |  |
| 438 | Client Error | Invalid 'alg' claim - algorithm. | 438<br>Invalid JWT format. Please ensure that alg claim is valid and is of value 'ES256' or 'RS256'. | Not RS256 or ES256<br>Missing alg+: (alg missing not possible to test due to library) |
| 439 | Client Error | Invalid 'typ' claim or JWT Type. | 439<br>Invalid JWT format. Please ensure that typ claim is valid. |  |
| 440 | Client Error | Missing API Key. | 440<br>Missing API Key in 'iss' claim. |  |
| 441 | Client Error | Missing 'iat' claim. | 441<br>Invalid JWT format. Please ensure that iat claim is valid. |  |
| 442 | Client Error | Missing 'aud' claim. | 442<br>Invalid JWT format. Please ensure that aud claim is valid. |  |
| 443 | Client Error | Missing 'jti' claim. | 443 |  |
| 445 | Client Error | Missing 'sub' claim. | 445<br>Invalid JWT format. Please ensure that sub claim is valid. |  |
| 446 | Client Error | Missing data hash claim. | 446<br>Invalid JWT format. Please ensure that data claim is valid. |  |
| 447 | Client Error | Missing 'exp' claim. | 447<br>Invalid exp claim. Please ensure that exp claim exists and JWT is not expired. |  |
| 400 | Bad Request | JWKS not provided for cross-zone.+ |  |  |
| 400 | Bad Request | AUD not provided for cross-zone.+ |  |  |