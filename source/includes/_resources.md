# Resources

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

## Get resources

Resources can be queried using this API. Its possible to specify which resources that should be returned by
specifing them on the query string.

### Query params
Parameter | Description
--------- | -----------
types | {String}  a comma separated list of resources

`GET http://api.castmill.com/resources`


## Create a resource

`POST http://api.castmill.com/calendars`


## Get calendars

`GET http://api.castmill.com/calendars`

## Edit calendar

`PUT http://api.castmill.com/calendars/:id`

## Add entry to calendar

`PUT http://api.castmill.com/calendars/:id/entries`

## Remove an entry from a calendar

`DELETE http://api.castmill.com/calendars/:id/entries`

## Remove calendar

`DELETE http://api.castmill.com/calendars/:id`
