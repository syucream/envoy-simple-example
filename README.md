# envoy-simple-example

An Envoy Proxy example with simple usage for xDS API

## Overview

- Envoy Proxy
  - A reverse proxy to endpoints.
  - Fetch endpoints from HTTP xDS API.
- HTTP xDS API
  - A xDS API based on HTTP REST fashion by using nginx.
  - Support only EDS.
- endpoint0
  - An origin server.
- endpoint1
  - An origin server.

## How to try

- At first, start containers.

```
$ docker-compose up
```

- Then you can request to endpoints via Envoy Proxy with load balancing.

```
$ curl http://localhost:10000/whoami.html
<html>
  <head>
    <title>I'm endpoint1</title>
  </head>
  <body>
    <p>endpoint1 works</p>
  </body>
</html>
$ curl http://localhost:10000/whoami.html
<html>
  <head>
    <title>I'm endpoint0</title>
  </head>
  <body>
    <p>endpoint0 works</p>
  </body>
</html>
```

