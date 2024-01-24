[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213811213)

## Foreword

Este documento também está disponível em [português](file:///C:/wiki/spaces/DraftOF/pages/138674283)

The Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the[Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.

Open Finance Brasil Financial-grade API Security Profile 1.0 consists of the following parts:

- [Open Banking Brasil Financial-grade API Security Profile 1.0](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76283925/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3)
- [Open Banking Brasil Dynamic Client Registration Profile 1.0](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76709980/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3)

These parts are intended to be used with [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) and [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)

## Introduction

The Financial-grade API Standard provides a profile for OAuth 2.0 suitable for use in financial services. The standard OAuth method for the client to send the resource owner to the authorization server is to use an HTTP redirect. Parts 1 and 2 of this specification support this interaction model and are suitable for use cases where the resource owner is interacting with the client on a device they control that has a web browser. There are however many use-cases for initiating payments where the resource owner is not interacting with the client in such a manner. For example, the resource owner may want to authorize a payment at a "point of sale" terminal at a shop or fuel station.

This document is a profile of the OpenID Connect Client Initiated Backchannel Authentication Flow[CIBA](https://openid.net/specs/openid-financial-api-ciba-ID1.html) that supports this decoupled interaction method. The CIBA spec allows a client that gains knowledge of an identifier for the user to obtain tokens from the authorization server. The user consent is given at the user's Authentication Device mediated by the authorization server. This document profiles the CIBA specification to bring it in line with the other FAPI parts and provides security recommendations for its use with APIs that require financial-grade security.

Although it is possible to code an OpenID Provider and Relying Party from first principles using this specification, the main audience for this specification is parties who already have a certified implementation of[Financial-grade API: Client Initiated Backchannel Authentication Profile](https://openid.net/specs/openid-financial-api-ciba-ID1.html) and want to achieve certification for the Brasil Open Finance programme.

## Notational Conventions

The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in[ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml). These key words are not used as dictionary terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.

## 1. Scope

This document specifies the method of:

1. applications to obtain OAuth tokens via a backchannel authentication flow in an appropriately secure manner for higher risk access to data in a manner that meets the requirements of[Open Finance Brasil](https://www.in.gov.br/en/web/dou/-/resolucao-conjunta-n-1-de-4-de-maio-de-2020-255165055);
2. applications to use OpenID Connect CIBA to suggest the identity of the customer;

This document is applicable to all participants engaging in Open Finance in Brasil.

## 2. Normative references

The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.

[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2

[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework

[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage

[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients

[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations

[RFC7515](https://tools.ietf.org/html/rfc7515) - JSON Web Signature (JWS)

[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)

[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol

[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol

[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)

[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1

[FAPI-CIBA](https://openid.net/specs/openid-financial-api-ciba-ID1.html) - Financial-grade API: Client Initiated Backchannel Authentication Profile

[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1

[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1

[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens

[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)

[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests

[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request

[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline

[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced

[FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md) - Financial-grade API Security Profile 2.0 - Part 1: Baseline

[FAPI-2-Advanced](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Advanced_Profile.md) - Financial-grade API Security Profile 2.0 - Part 2: Advanced

[FAPI-CIBA](https://openid.net/specs/openid-financial-api-ciba-ID1.html) - Financial-grade API: Client Initiated Backchannel Authentication Profile

[FAPI-BR](file:///C:/wiki/spaces/OF/pages/82083996) - Open Finance Brasil Financial-grade API Security Profile 1.0

[CIBA](https://openid.net/specs/openid-financial-api-ciba-ID1.html) - OpenID Connect Client Initiated Backchannel Authentication Core

[LIWP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper

[OBB-FAPI-DCR](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3.html) - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0

[RFC4648](https://tools.ietf.org/html/rfc4648) - The Base16, Base32, and Base64 Data Encodings

## 3. Terms and definitions

For the purpose of this document, the terms defined in[RFC6749](https://tools.ietf.org/html/rfc6749),[RFC6750](https://tools.ietf.org/html/rfc6750),[RFC7636](https://tools.ietf.org/html/rfc7636),[OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html),[CIBA](https://openid.net/specs/openid-financial-api-ciba-ID1.html) and ISO29100 apply.

## 4. Symbols and Abbreviated terms

**API **- Application Programming Interface

**OFBIS **- Open Finance Brasil Initial Structure

**CSRF **- Cross Site Request Forgery

**DCR **- Dynamic Client Registration

**FAPI **- Financial-grade API

**HTTP **- Hyper Text Transfer Protocol

**OIDF **- OpenID Foundation

**REST **- Representational State Transfer

**TLS **- Transport Layer Security

**MFA **- Multi-Factor Authentication

## 5. Brasil Open Banking Security Profile

### 5.1. Introduction

The Brasil Open Finance Security profile specifies additional security and identity requirements for high risk API resources protected by the OAuth 2.0 Authorization Framework that consists of[RFC6749](https://tools.ietf.org/html/rfc6749),[RFC6750](https://tools.ietf.org/html/rfc6750),[RFC7636](https://tools.ietf.org/html/rfc7636),[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html),[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html),[FAPI-CIBA](https://openid.net/specs/openid-financial-api-ciba-ID1.html) and other specifications.

This profile describes security and features provisions for a server and client that are necessary for the Brasil Open Finance Programme by defining the measures to address:

- the requirement to convey the Authentication Context Request that was performed by an OpenID Provider to a Client to enable appropriate client management of customer conduct risk.
- the requirement for clients to assert a pre-existing customer relationship by asserting a customer identity claim as part of the CIBA flow.

### 5.2. Open Banking Brasil CIBA Security provisions

#### 5.2.1. Introduction

Open Finance Brasil has a requirement to adopt Client[Initiated Back Channel Authentication](https://openid.net/specs/openid-financial-api-ciba-ID1.html) as a means of enabling decoupled authentication work flows. In addition this profile describes the specific scope, acr and client management requirements necessary to support the wider Open Finance Brasil ecosystem.

As a profile of the OAuth 2.0 Authorization Framework, this document mandates the following for the Brasil Open Finance Security profile.

#### 5.2.2. Authorization server

The Authorization Server shall support the provisions specified in clause 5.2.2 of[Financial-grade API CIBA Security Profile 1.0](https://openid.net/specs/openid-financial-api-ciba-ID1.html)

In addition, the Authorization Server

1. The acceptance time of consent on the Authorization request received via CIBA shall remain the same as defined for the flow via Hybrid Flow, of 5 minutes;
2. shall ensure that ‘exp’ in all issued id\_tokens is at least 180 days from the time of issue;
3. The id\_token shall be used in the authorization call through the "id\_token\_hint" parameter;
4. shall support CIBA poll mode;
5. shall not support CIBA push mode;
6. shall not support CIBA ping mode;
7. The cancellation of the id\_token shall be carried out by the account holder institution in cases of fraud or for security reasons.
8. Error table “HTTP 400 Bad Request”:

- invalid\_request: The request is missing a required parameter, includes an invalid parameter value, includes a parameter more than once, contains more than one of the hints, or is otherwise malformed;
- invalid\_scope: The requested scope is invalid, unknown, or malformed;
- expired\_id\_token\_hint: The id\_token hint provided in the authentication request is not valid because it has expired;
- unknown\_user\_id: The OpenID Provider is not able to identify which end-user the Client wishes to be authenticated by means of the hint provided in the request (id\_token\_hint);
- unauthorized\_client: The Client is not authorized to use this authentication flow;
- invalid\_id\_token\_hint: The id\_token is invalid and can’t be used in the flow.

1. Shall issue ciba auth request acknowledgements (response of the consultation of auth\_req\_id) with a maximum expiry of 5 minutes, as defined for the flow via Hybrid Flow;
2. Id\_token payload validation.

| **Parameters** | **Validation** |
| --- | --- |
| iss | The Authorization Server must establish an identifier, or set of standard "iss" identifiers for use in CIBA transactions. - The Authorization Server should not accept "iss" different from its own identifier, or set of identifiers, standard. |
| sub | The Authorization Server should check if the "sub" identifier in question has already been issued to a client/account, and if it is valid within its requirements. |
| aud | The Authorization Server should not accept "aud" different from the client\_id from where the authorization request for the CIBA flow originates. |
| exp | "exp" should be established according to the risk policies of the Account Holder institution, provided that requirement 5.2.2.15 is respected (minimum of 180 days) - The Authorization Server should not accept authorization requests whose date/time is greater than "exp". |
| iat | No specific validations |
| auth\_time | No specific validations |
| nonce | No specific AS validations |
| acr | If present, the AS should only accept values equal to or above the Holder's authentication requirements to authorize payment transactions. |
| amr | If present, the AS should only accept values equal to or better than the Holder's authentication requirements to authorize payment transactions. |
| azp | The Authorization Server should not accept "azp" different from the client\_id from where the authorization request for the CIBA flow originates. |

1. Parameters for signature validation

| **Parameters** | **Description** | **Condition** | **Recommended values** |
| --- | --- | --- | --- |
| alg | The "alg" (algorithm) parameter identifies the cryptographic algorithm used to protect the JWS/JWE. The JWS Signature value is invalid if the "alg" value does not represent a supported algorithm or if there is no compatible key for the use of the algorithm associated with the entity that digitally signed the content. | Required | PS256 or PS512 |
| kid | The "kid" (Key ID) parameter indicates which key was used to protect the JWS/JWE. This parameter allows senders to explicitly signal a key change to recipients. The "kid" value MUST be a case-sensitive string. When used with a JWK, the "kid" value is used to match a "kid" parameter value of the JWK. | Required |  |
| x5t | x5t#S256 | The "x5t" or “x5t#S256” (X.509 Certificate SHA-1/SHA-256 Thumbprint) parameter is a base64url encoded SHA-1/SHA-256 thumbprint (hash) of the DER encoding of the X.509 certificate (RFC5280) corresponding to the key used to digitally sign the JWS. | Required |  |
| typ | The "typ" (Type) parameter is used by JWS applications to declare the media type (IANA.MediaTypes) of this complete JWS. It is intended for use by the application when more than one type of object may be present in an application data structure that can contain a JWS; the application can use this value to eliminate ambiguity between the different types of objects that may be present. | Optional | JWT |

#### 5.2.3. Confidential client

In addition, the confidential client

1. shall support parameterized OAuth 2.0 resource scope consent as defined in clause 6.3.1[OIDF FAPI WG Lodging Intent Pattern](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md)
2. shall support refresh tokens

## 6. Security considerations

Participants shall support all security considerations specified in all clauses and sub clauses of [\[FAPI-BR\]](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82083996/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3) and[FAPI-CIBA](https://openid.net/specs/openid-financial-api-ciba-ID1.html)

## 7. Data Sharing Considerations

Participants shall support all data sharing considerations specified in [FAPI-BR]

## 8. Acknowledgements

With thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.

The following people contributed to this document:

- Gustavo Cunha (Banco do Brasil)
- Karina Cabral (Mercado Pago)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## Appendix A. Notices

Copyright (c) 2023 Open Finance Brasil Initial Structure.

The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.

The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.

## Author's Address

OFBIS GT Security

Open Finance Brasil Initial Structure

Email: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)

URI:[https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213811213)