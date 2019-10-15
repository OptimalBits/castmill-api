# Users

The users endpoint provides methods for managing the users in the system.

## Create user

A user is created by calling this API. When using this method, it is possible to
allow the user to login on the instance login page, where he will be asked for
a specific login and password, or using to the SSO mechanism provided by the API.

When a user is created, the user will receive a welcoming email and a link
to verify his account. When cliking on the link the user will be able to set
the desider password.

If the sso boolean is enabled, the user will not get a the welcoming mail, and
he will only be able to use via SSO.

`POST http://api.castmill.com/users`

### Mandatory Body parameters

| Parameter | Description                                                         |
| --------- | ------------------------------------------------------------------- |
| email     | {String} A valid email, it will be used to identify a given user.   |
| sso       | {Boolean} A boolean represeting if the user can login only via SSO. |

## Get a single user

Returns all the details of a given user.

`GET http://api.castmill.com/users/:id`

## Get users

Returns a collection with all the users in the system, or the result of a `query`.
See `queries` for details on how they are specified.

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

Resources are used to manipulate entities in Castmill that can be shared among users. A resource is a wrapper over an underlying
entity. The wrapper includes the permissions the current user has over a given resource. It is also possible to manipulate the
underlying resources directly, but in most cases it is not needed other than for performing administrative tasks.

The available resources are:

- Medias
- Playlists
- Displays
- Calendars

Resources always belong to a group or directly to a user (its owner). When a resource is created is placed on the creators
ownership with all the available permissions, but it can later be placed in different groups with different permission sets.

### Query params

| Parameter | Description                                  |
| --------- | -------------------------------------------- |
| types     | {String} a comma separated list of resources |

```json
{
  "owner": "String",
  "id": "String",
  "collection": "String",
  "permissions": "[String]",
  "populated": "{Object}"
}
```

Returns all the resources that a user has access to. The resources are wrapped with
some useful data for handling the resources, such as owner of the resource as well
as its permissions.

`GET http://api.castmill.com/users/:id/resources`

## Upload Medias

It is possible to upload medias to castmill for a given user by using the following API. All media types supported by Castmill
are algo supported by this API (for example images, videos and audios of any kind, powerpoints, PDFs, and HTML5 content).

`POST http://api.castmill.com/users/:id/medias`
