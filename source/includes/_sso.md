# Single Sign On

Castmill provides an API for implementing single sign on (SSO) on any IT infrastructure.
The SSO is implemented using JWT ([JSON Web Tokens](https://jwt.io)). You can login
in Castmill and if you have the proper rights, request a JWT token that can be used
for authenticating a user on Castmill.

## Request a JWT Token

```json
{
  "email": "john.doe@example.com",
  "token": "mysecrettoken"
}
```

> Returns
```json
{
  "redirectUrl": "https://castmill.com/login",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
}
```

`POST http://api.castmill.com/login`

A JWT token can be requested with this API. It returns a JWT token that can be used for
redirecting to a castmill instance and be automatically logged in.

> Example
```shell
https://app.castmill.com/login?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ
```

## Setting a login redirect.

In a Single sign on environment, you will probably want to define a login page to be
redirected to if a user tries to go directly to your Castmill instance. Using the
*settings* API you can define a property "redirectSSO" with a url to your login page.

Check the *settings* for details on this API.
