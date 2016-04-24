---
title: Castmill API Reference

language_tabs:
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - authentication
  - users
  - sso
  - medias
  - playlists
  - players
  - calendars
  - groups
  - displays
  - settings
  - errors

search: true
---

# Introduction

Welcome to Castmill public API. With this API you can access all the services provided
by Castmill in a programatic way.

We provide examples in curl and javascript (node).

The API is quite uniform, so manipulating and getting resources often use the same APIS, just
the endpoints are different.

### Query strings

For endpoints that return collections, there are a few query parameters that can be used
for search, filtering as well as pagination:

Parameter | Description
--------- | -----------
limit | {Number} Max amount of items returned
skip | {Number} Skip given amount of items.
fields | {String} A list of space separated fields to include.
cond | {Object} A query object

Query objects support all query commands provided by
[mongodb](https://docs.mongodb.org/manual/tutorial/query-documents/)

Examples:

`api.castmill.com/users/?limit=4&fields=name email&cond[name]=john`

