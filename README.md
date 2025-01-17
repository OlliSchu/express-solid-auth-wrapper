﻿# express-solid-auth-wrapper
Middleware functions to authenticate to a remote solid service. Merely a wrapper around '@solid/access-token-verifier' and 'solid-node-client'. Use `npx @inrupt/generate-oidc-token` to provide your app with Solid credentials. This module around contains the following functions:

- extractWebId():
middleware function to extract the webId from a request sent to the service (DPOP). Invoked via `app.use(extractWebId)`

- setSatellite(config):
middleware function to use the service as an authenticated satellite for an existing Pod. Invoked via `app.use(setSatellite(config))`, where config is a JSON object retrieved via `solid-node-client` in the following form ```{
    "refreshToken" : "a-refresh-token",
    "clientId"     : "a-client-id",
    "clientSecret" : "a-client-secret",
    "oidcIssuer"   : "https://pod.lbdserver.org/"
  }```
