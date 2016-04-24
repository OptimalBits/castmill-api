# Users

The users endpoint provides methods for managing the users in the system.

## Create user

A user is created by calling this API. When using this method, it is possible to
allow the user to login on the instance login page, where he will be asked for
a specific login and password, or using  to the SSO mechanism provided by the API.

`POST http://api.castmill.com/users`

### Mandatory Body parameters

Parameter | Description
--------- | -----------
email | {String} A valid email, it will be used to identify a given user.
sso | {Boolean} A boolean represeting if the user can login only via SSO.

## Get a single user

Returns all the details of a given user.

`GET http://api.castmill.com/users/:id`

## Get users

Returns a collection with all the users in the system, or the result of a `query`.

`GET http://api.castmill.com/users`

## Edit user

Edit some fields in a user.

`PUT http://api.castmill.com/users`

## Remove user

Removes a user from the system.

`DELETE http://api.castmill.com/users/:id`

## Get users groups

Returns the groups where a user is part of. Groups are used to share resources
between users.

`GET http://api.castmill.com/users/:id/groups`

## Get user resources

```json
{
    owner: String,
    id: String,
    collection: String,
    permissions: [String],
    populated: {Object}
}
```

Returns all the resources that a user has access to. The resources are wrapped with
some data useful for handling the resources, such as owner of the resource as well
as its permissions.

`GET http://api.castmill.com/users/:id/resources`
