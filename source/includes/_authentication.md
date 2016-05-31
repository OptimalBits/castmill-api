# Authentication
> To authorize, use this code:


```javascript
var castmill = require('castmill');

var api = castmill.authorize('mycastmilltoken')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api.castmill.com"
  -H "Authorization: mycastmilltoken"

# You can also use the query string parameter 'accessToken'
curl "api.castmill.com?accessToken=mycastmilltoken"
```
> Make sure to replace `mycastmilltoken` with your API key.

Castmill uses a secret token for authentication. This token can be generated in the Account page.
The acccess token will provide the same level of access as your castmill account, so please keep
this token secured, never expose it in client code.

Depending on your user access level you will be able to perform different calls (see rights and quotas).

The API calls require an `Authorization` header with a token or a query string parameter *accessToken*.

`Authorization: mycastmilltoken`

<aside class="notice">
You must replace <code>mycastmilltoken</code> with your personal API key.
</aside>
