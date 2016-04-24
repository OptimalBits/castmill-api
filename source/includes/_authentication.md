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
```

> Make sure to replace `mycastmilltoken` with your API key.

Castmill uses JWT for authentication. You will get a secret token from your Castmill instance that you
can use to access the API, and depending on your user access level you will be able to perform
different calls (see rights and quotas).

We provide examples using curl and node, but there are jwt libraries available for most language.

The API calls require an `Authorization` header with a JWT token. You can get your secret API token
from your Account page:

`Authorization: mycastmilltoken`

<aside class="notice">
You must replace <code>mycastmilltoken</code> with your personal API key.
</aside>
