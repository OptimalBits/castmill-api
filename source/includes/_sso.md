# Single Sign On

Castmill provides an API for implementing single sign on (SSO) on any IT infrastructure.
The SSO is implemented using JWT ([JSON Web Tokens](https://jwt.io)). You can login
in Castmill and if you have the proper rights, request a JWT token that can be used
for authenticating a user on Castmill.

## Request a JWT Token

`POST http://api.castmill.com/login/:userId`

A JWT token can be requested with this API. It returns a JWT token that can be used for
redirecting to a castmill instance and be automatically logged in.

The call returns a JWT token like:

`eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI1NzI2NTcyZWVjYjNkYTAxMDBhYjc3MGQiLCJleHAiOjE0NjQxMjM0MTUuMTg3LCJpYXQiOjE0NjQxMjE2MTV9.H51HDjsRtldoSW0gfryf7Vxjs-VeL9yiHnWk52jzUhE`

## Authorize a user using the JWT token

With the JWT token provided by the previous API call it is now possible to login as the given user.

`GET http://api.castmill.com/auth/jwt?token=mytoken`

It is also possible to redirect to a certain view when login in using the `redir` query parameter:

`GET http://api.castmill.com/auth/jwt?token=mytoken&redir=/dashboard/medias`


## Setting a login redirect.

In a Single sign on environment, you will probably want to define a login page to be
redirected to if a user tries to go directly to your Castmill instance. Using the
*settings* API you can define a property "redirectSSO" with a url to your login page.

Check the *settings* for details on this API.
