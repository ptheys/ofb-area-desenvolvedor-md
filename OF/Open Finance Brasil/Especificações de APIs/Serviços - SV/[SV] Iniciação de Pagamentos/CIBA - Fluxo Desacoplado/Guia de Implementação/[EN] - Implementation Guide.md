[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213811201)

## Option 1: Payment Initiation using an Identification Token (id\_token) in the Initiator

The Payment Initiation Service of Open Finance Brazil implements the consent flow with redirection for payment authorization. This redirection can be carried out via redirect between applications or websites &lt;&gt; applications. CIBA provides an alternative for this flow where there's a decoupling of the process and the channel for the authorization can come from a push-notification, SMS, email, WhatsApp, etc.

### Adhesion

After a regular redirection, the user, in an account holder with CIBA enabled, can adhere to this form of authorization when accepting consent.

### Settlement

In the payment initiator's environment, the user can select the saved account and receive the authorization request via push-notification, SMS, email, WhatsApp, etc. The user must still authorize the consent for the payment to be successfully executed.

### Guidelines for this option:

1. Payment initiators and account holders should consider the id\_token, obtained in the FAPI Hybrid Flow, as user and account identification to be used at the endpoint to retrieve the payment authentication token.
2. The id\_token must have a minimum expiration of 180 days.
3. Payment initiators should display, in the payment flow, the user and account data to be selected. This query can be done by fetching the data from the Payment Consent endpoint (GET /payments/v2/consents/{consentId}, data /data/debtorAccount/number).
4. Use the UX guide as a reference where there will be a checkbox for "save account for future transactions" (UX guide and figma link).
5. The id\_token should be used in the authorization call through the "id\_token\_hint" parameter.
6. Only the "poll mode" will be used to obtain the token for sending the payment via the CIBA Backchannel Authentication Endpoint described in the account holder's well-known.
7. The id\_token's cancellation can be carried out by the account holder in fraud cases or for security reasons.
8. The id\_token's cancellation can be performed by the payment initiator in cases of fraud or for security reasons, by removing the id\_token of the client in its database. Based on FAPI and OIDF protocols, only the removal of the id\_token is enough to interrupt the use of the CIBA flow since, after removal, the payment initiator will not be able to reference the client.

### Information and validations of an id\_token

Information contained in an id\_token

| **Parameters** | **Validations** |
| --- | --- |
| iss | <ul><li><p>The Authorization Server should establish a standard identifier, or set of identifiers &quot;iss&quot; for use in CIBA transactions. The Authorization Server should not accept an &quot;iss&quot; that differs from its own standard identifier or set of identifiers.</p></li></ul> |
| sub | <ul><li><p>The Authorization Server should check if the &quot;sub&quot; identifier in question has already been issued for a client/account, and if it's valid within its requirements.</p></li></ul> |
| aud | <ul><li><p>The Authorization Server should not accept an &quot;aud&quot; that differs from the client_id from which the authorization request for the CIBA flow originates.</p></li></ul> |
| exp | <ul><li><p>&quot;exp&quot; should be established according to the risk policies of the Account Holding institution.</p></li></ul> |
| iat | <ul><li><p>No specific validations.</p></li></ul> |
| auth\_time | <ul><li><p>No specific validations.</p></li></ul> |
| nonce | <ul><li><p>No specific validations for the AS.</p></li></ul> |
| acr | <ul><li><p>If present, the AS should only accept values equal to or higher than the authentication requirements of the Holder to authorize payment transactions.</p></li></ul> |
| amr | <ul><li><p>If present, the AS (Authorization Server) should only accept values equal to or better than the authentication requirements of the Holder to authorize payment transactions.</p></li></ul> |
| azp | <ul><li><p>The Authorization Server should not accept an &quot;azp&quot; different from the client_id from which the authorization request for the CIBA flow originates.</p></li></ul> |

Parameters for validating an id\_token.

All parameters must be present in the JWT header (header).

| **Parameters** | **Description** | **Recommended Values** |
| --- | --- | --- |
| alg | The "alg" (algorithm) parameter identifies the cryptographic algorithm used to secure the JWS/JWE. The JWS Signature value is invalid if the "alg" value does not represent a supported algorithm or if there is no compatible key available for the algorithm associated with the entity that digitally signed the content. | PS256 or PS512 |
| jku | The "jku" (JWK Set URL) parameter is a URI (RFC3986) that points to a resource for a set of public keys encoded in JSON, one of which matches the key used to digitally sign the JWS. The keys MUST be encoded as a JWK Set.<br><br>The protocol used to acquire the resource MUST provide integrity protection; an HTTP GET request to retrieve the JWK Set MUST use Transport Layer Security (TLS); and the server's identity MUST be validated, according to Section 6 of RFC6125. (OPTIONAL) |  |
| jwk | The "jwk" (JSON Web Key) parameter is the public key that matches the key used to digitally sign the JWS. This key is represented as a JWK. (OPTIONAL) |  |
| kid | The "kid" (Key ID) parameter indicates which key was used to secure the JWS/JWE. This parameter allows senders to explicitly signal a key change to recipients. The "kid" value MUST be a case-sensitive string. When used with a JWK, the "kid" value matches a "kid" parameter value of the JWK. (OPTIONAL) |  |
| x5u | The "x5u" (X.509 URL) parameter is a URI (RFC3986) pointing to a resource for the X.509 public key certificate or certificate chain (RFC5280) corresponding to the key used to digitally sign the JWS. (OPTIONAL) |  |
| x5c | The "x5c" (X.509 Certificate Chain) parameter contains the X.509 public key certificate or certificate chain (RFC5280) corresponding to the key used to digitally sign the JWS. (OPTIONAL) |  |
| x5t | The "x5t" (X.509 Certificate SHA-1 Thumbprint) is a base64url encoded SHA-1 thumbprint (hash) of the DER encoding of the X.509 certificate (RFC5280) corresponding to the key used to digitally sign the JWS. (OPTIONAL) |  |
| x5t#S256 | The "x5t#S256" (X.509 Certificate SHA-256 Thumbprint) is a base64url encoded SHA-256 thumbprint (hash) of the DER encoding of the X.509 certificate (RFC5280) corresponding to the key used to digitally sign the JWS. It can be used alternatively to "x5t". (OPTIONAL) |  |
| typ | The "typ" (Type) parameter is used by JWS applications to declare the media type (IANA.MediaTypes) of this complete JWS. It is intended for use by the application when more than one type of object can be present in an application data structure that might contain a JWS; the application can use this value to disambiguate between the different types of objects that could be present. (OPTIONAL) | JWT |
| cty | The "cty" (Content Type) parameter is used by JWS applications to declare the media type (IANA.MediaTypes) of the secured content (payload). It is intended for use by the application when multiple types of objects might be present in the JWS Payload; the application can use this value to disambiguate between the different types of objects that could be present. | use “example” instead “application/example” |
| crit | The "crit" (Critical) parameter indicates that extensions to this specification and/or [JWA] are being used and MUST be understood and processed. Its value is an array containing the names of the Header Parameters present in the JOSE Header that are using these extensions. |  |

### Step by step to save an id\_token

Remember, the flow for generating an id\_token is a regular FAPI Hybrid-Flow consent! The Payment Initiator should save the id\_token that comes in the redirection back from the holder via query parameters.

1. Follow the steps of the [Sequence Diagram](/wiki/spaces/DraftOF/pages/169672781) of a Payment Initiation via Hybrid-Flow.
2. At the stage of receiving the **code, state, id\_token **on the redirectURL (redirection back from the holder to the initiator), the initiator must save the id\_token that also comes in the URL's parameters. Pay attention to item 4 of the sequence diagram link above.
3. Execute the payment as usual because only in the next payment will it be possible to use the CIBA channel to communicate with the client to authorize a consent.

### Step by step for a Payment Initiation with the saved id\_token

1. Create a phase 3 consent for standard Payment Initiation.
2. Receive a response from the creation of the consent with **AWAITING\_AUTHORISATION **status.
3. Request the CIBA Backchannel Authentication Endpoint for consent authorization, check the payload below:

    POST {BackchannelAuthenticationEndpoint} HTTP/1.1
    Host: {AuthorizationServer}
    Content-Type: application/x-www-form-urlencoded
    
    scope=openid consent:urn:bancoex:C1DD33123&
    id_token_hint=eyJhbGciOiJSUzI1NiIsImtpZCI6IjE2Nzcy
    NiJ9.eyJpc3MiOiJodHRwczovL3NlcnZlci5leGFtcGxlLmNvbSI
    sInN1YiI6IjI0ODI4OTc2MTAwMSIsImF1ZCI6InM2QmhkUmtxdDM
    iLCJlbWFpbCI6ImphbmVkb2VAZXhhbXBsZS5jb20iLCJleHAiOjE
      1Mzc4MTk4MDMsImlhdCI6MTUzNzgxOTUwM30.aVq83mdy72ddIFV
      JLjlNBX-5JHbjmwK-Sn9Mir-blesfYMceIOw6u4GOrO_ZroDnnbJ
      XNKWAg_dxVynvMHnk3uJc46feaRIL4zfHf6Anbf5_TbgMaVO8icz
      D16A5gNjSD7yenT5fslrrW-NU_vtmi0s1puoM4EmSaPXCR19vRJy
      WuStJiRHK5yc3BtBlQ2xwxH1iNP49rGAQe_LHfW1G74NY5DaPv-V
      23JXDNEIUTY-jT-NbbtNHAxnhNPyn8kcO2WOoeIwANO9BfLF1EFW
      tjGPPMj6kDVrikec47yK86HArGvsIIwk1uExynJIv_tgZGE0eZI7
      MtVb2UlCwDQrVlg&

The fields must be URL-encoded (URL Encoded). In the example, they were left as plain text to facilitate understanding.

The BackchannelAuthenticationEndpoint can be found in the ***.well-known ***of the account holder (detentora).

The initiator (iniciadora) must send the consent ID in the scope field along with the ***openid ***scope.

The account holder (detentora) must validate the id\_token according to the tables referenced above.

### **Error table “HTTP 400 Bad Request”:**

1. **invalid\_request**: The request is missing a required parameter, includes an invalid parameter value, includes a parameter more than once, contains more than one of the hints, or is otherwise malformed.
2. **invalid\_scope**: The requested scope is invalid, unknown, or malformed.
3. **expired\_id\_token\_hint**: The id\_token hint provided in the authentication request is not valid because it has expired.
4. **unknown\_user\_id**: The OpenID Provider is not able to identify which end-user the Client wishes to be authenticated by means of the hint provided in the request (id\_token\_hint).
5. **unauthorized\_client**: The Client is not authorized to use this authentication flow.
6. **invalid\_id\_token\_hint**: The id\_token is invalid and can’t be used in the flow.

1. Response from the Backchannel Authentication Endpoint:

    HTTP/1.1 200 OK
    Content-Type: application/json
    
    {
      "auth_req_id": "1c266114-a1be-4252-8ad1-04986c5b9ac1",
      "expires_in": 120,
      "interval": 2
    }

**auth\_req\_id**: identifier for the authentication request;

**expires\_in**: expiration time of the auth\_req\_id in seconds, the maximum time the initiator can poll the `/token`;

**interval**: minimum polling interval on `/token`** **which must be greater than 2 seconds;

1. Upon receiving the call from the Backchannel Authentication Endpoint, the account holder (detentora) should inform the user about the payment request, using the decoupled channel (SMS, push notification, etc) of their choice to authenticate the client according to their policies and authorize the payment.
2. With the payment acknowledged by the user, the account holder (detentora) changes the status of the consent to AUTHORISED.
3. In possession of the auth\_req\_id, the initiator (iniciadora) must call the `/token`** **endpoint at a time interval determined by the `interval`** **field from the response of the Backchannel Authentication Endpoint call to receive the `access_token`, `id_token`, and the `refresh_token`** **of the authorized consent until a time limit determined by the `expires_in`** **field of the response. This is the poll mode.

    POST {TokenEndpoint} HTTP/1.1
    Host: {AuthorizationServer}
    
    Content-Type: application/x-www-form-urlencoded
    grant_type=urn:openid:params:grant-type:ciba&   //    Mandatory
    auth_req_id=1c266114-a1be-4252-8ad1-04986c5b9ac1    //    Mandatory

The fields must be URL Encoded. In the example, it was left as plaintext to facilitate understanding.

**grant\_type**: should be urn:openid:params:grant-type:ciba

**auth\_req\_id**: identifier of the authentication request received in the response from the Backchannel Authentication Endpoint.

1. Conduct polling to get the status of the consent request's authorization. Once the payment request is authorized, the account holder (detentora) should return a successful response with statusCode 200. In cases where the consent has not yet been accepted or has been rejected, the account holder (detentora) should return 403 with the error codes listed below.

Example of a successful response according to CIBA.Core1 10.1.1:

    HTTP/1.1 200 OK
    Content-Type: application/json
    
    {
      "access_token":   "9f312798-11e7-4e87-a143-b83bd1c2026f",
      "token_type":     "Bearer",
      "refresh_token":  "c410670a-5cb9-4bef-aa0d-d5c30e3d33a3",
      "expires_in":     120,
      "id_token":       "eyJhbGciOiJSUzI1NiIsImtpZCI6IjE2Nzcy
          NiJ9.eyJpc3MiOiJodHRwczovL3NlcnZlci5leGFtcGxlLmNvbSI
          sInN1YiI6IjI0ODI4OTc2MTAwMSIsImF1ZCI6InM2QmhkUmtxdDM
          iLCJlbWFpbCI6ImphbmVkb2VAZXhhbXBsZS5jb20iLCJleHAiOjE
          1Mzc4MTk4MDMsImlhdCI6MTUzNzgxOTUwM30.aVq83mdy72ddIFV
          JLjlNBX-5JHbjmwK-Sn9Mir-blesfYMceIOw6u4GOrO_ZroDnnbJ
          XNKWAg_dxVynvMHnk3uJc46feaRIL4zfHf6Anbf5_TbgMaVO8icz
          D16A5gNjSD7yenT5fslrrW-NU_vtmi0s1puoM4EmSaPXCR19vRJy
          WuStJiRHK5yc3BtBlQ2xwxH1iNP49rGAQe_LHfW1G74NY5DaPv-V
          23JXDNEIUTY-jT-NbbtNHAxnhNPyn8kcO2WOoeIwANO9BfLF1EFW
          tjGPPMj6kDVrikec47yK86HArGvsIIwk1uExynJIv_tgZGE0eZI7
          MtVb2UlCwDQrVlg"
      }

Example of an error response according to CIBA.Core1 10.1.1:

    HTTP/1.1 403 Forbidden
    Content-Type: application/json
    {
        1. "error": "authorization_pending",
        2. "error_description": "The user has not yet been authenticated, and the authorization request is still pending."
    }

### List of possible errors:

| **Error Code** | **Error Description** |
| --- | --- |
| authorization\_pending | The user has not yet been authenticated, and the authorization request is still pending |
| slow\_down | The authorization request is still pending, and the client must increase the interval for polling requests by at least x seconds |
| expired\_token | The transaction (auth\_req\_id) has expired. The client must start over with a new Authentication Request |
| access\_denied | The user did not consent to the authorization request |

1. Continue with the payment initiation process and make calls to the payment API, if access is successfully granted.

### CIBA flow sequence diagram

![att213712930]([EN]%20-%20Implementation%20Guide/attachments/Diagrama_CIBA_EN.png)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213811201)