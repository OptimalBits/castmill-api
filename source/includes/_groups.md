# Groups

Groups provides functionality to share resources between users by defining
a set of permissions per shared resource. A group is composed of resources and
users. Every resource can have its permission finegrained defined.

There are 4 different types of resources:
- Media
    A media is a image, video, ppt, pdf, or a widget.
- Playlist
    A playlist contains a list of medias to be played in sequence.
- Display
    A display represents a registered player.
- Calendar
    A calendar defines where in time the playlists and medias should be played.

## Create a group

In order to create a group a name and a owner must be defined.

`POST http://api.castmill.com/groups`

### Body params
Parameter | Description
--------- | -----------
name | {String} The name of the group
ownerUsername | {String} The owner of the group. (email)

## Get a group

With this API you can get the details of a give group.

`GET http://api.castmill.com/groups/:id`

## Get groups

You can get all the groups in the system.

`GET http://api.castmill.com/groups`

## Edit group

`PUT http://api.castmill.com/groups/:id`

## Add users to group

Add users to a given group by calling this API. Send in the

`PUT http://api.castmill.com/groups/:id/users`

### Body params
Parameter | Description
--------- | -----------
_cid | {String} The id of the user to add to the group.


## Remove users from a group

`DELETE http://api.castmill.com/groups/:id/users/:userId`

## Insert resources in a group

In order to add a resource to a group, you need to provide the resource Id,
the type of resource (Media, Playlist, Display or Calendar) as well as an array
with the permissions for that resource, 'get', 'put', 'use' or 'delete'.

### Body params
Parameter | Description
--------- | -----------
_cid | {String} The id of the resouce to add to the group.
type | {String} The type of resource.
permissions | String[] An array with permissions.

`PUT http://api.castmill.com/groups/:id/resources`

## Get resources from a group

`GET http://api.castmill.com/groups/:id/resources`

## Remove resources from a group

`DELETE http://api.castmill.com/groups/:id/resources/:resourceId`

## Remove group

`DELETE http://api.castmill.com/groups/:id`


## Audit resources

Sometimes is usefull to know which groups a resource is part of. This can be used to
understand why a given user may have rights over a given resource.

`GET http://api.castmill.com/audit/:resourceId`


