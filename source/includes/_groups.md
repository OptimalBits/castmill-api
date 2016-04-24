# Groups

## Create a group

`POST http://api.castmill.com/groups`

## Get a group

`GET http://api.castmill.com/groups/:id`

## Get groups

`GET http://api.castmill.com/groups`

## Edit group

`PUT http://api.castmill.com/groups/:id`

## Add users to group

`PUT http://api.castmill.com/groups/:id/users`

## Remove users from a group

`DELETE http://api.castmill.com/groups/:id/users`

## Insert resources in a group

```json
{
    owner: String,
    id: String,
    collection: String,
    permissions: [String]
}
```

`PUT http://api.castmill.com/groups/:id/resources`

## Get resources from a group

`GET http://api.castmill.com/groups/:id/resources`

## Remove resources from a group

`DELETE http://api.castmill.com/groups/:id/resources`

## Remove group

`DELETE http://api.castmill.com/groups/:id`
