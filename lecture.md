## JSON Web Token

header.payload.signature

## Header

base64({
algorithm: "H256"
type: "JWT"
})

## Payload

Data you want to pass back and forth:
Claims, or user permissions

base64({
membershipId: "12345"
accessLevel: "unlimited"
})

## Signature

hash(header + payload + secretString)

## JWT Auth Flow

-   Client sends credentials to the server (username password)(login)
-   Server verifies credentials. (lookup user, check pass hash, )
-   Server creates a JWT for the client.
-   Server sends back the JWT after signature and sends it back as header
-   Client saves the JWT to localstorage
-   Client sends JWT on eery subsequent request as header
-   Server verifies the JWT as valid by checking hash signature (no state required)
-   Server provies access to the resource.
