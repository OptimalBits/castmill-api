
# Displays

## Register a display

Displays can be registered by posting a name and pincode to the endpoint above. The pincode must be the
same one as the one displayed by the player on the welcome screen.

`POST http://api.castmill.com/displays`

### Body params
Parameter | Description
--------- | -----------
name | {String} The name of the display.
pincode | {String} The pincode of the display.

## Get a display

`GET http://api.castmill.com/displays/:id`

## Get displays

`GET http://api.castmill.com/displays`

## Edit display

`PUT http://api.castmill.com/displays/:id`

## Assign calendars to display

`PUT http://api.castmill.com/displays/:id/calendars`

## Remove calendar from a display

`DELETE http://api.castmill.com/displays/:id/entries`

## Remove display

`DELETE http://api.castmill.com/displays/:id`

## Display events

GET /displays/:id
GET /displays/:id/events
