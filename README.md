# fastify-server-timeout [![Build Status](https://travis-ci.org/fastify/fastify-server-timeout.svg?branch=master)](https://travis-ci.org/fastify/fastify-server-timeout)

__This module is deprecated as the functionality is embedded in Fastify now__.
See https://www.fastify.io/docs/latest/Server/#keepalivetimeout for more details.

Set timeout for incoming messages.

nodejs by default keep the request lived [for 2 minutes](https://nodejs.org/docs/latest/api/http.html#http_server_settimeout_msecs_callback).
With this plugin you can change that timeout.

**NB:** this plugin change the nodejs core `http.Server` object. So registering this plugin,
every requests will be affected by this timeout: this plugin breaks the encapsulation

## Install

```
npm i fastify-server-timeout
```

## Usage

```js
const Fastify = require('fastify')
const plugin = require('fastify-server-timeout')

const fastify = Fastify({ logger: { level: 'silent' } })

fastify.register(plugin, {
  serverTimeout: 100 //ms
})
```
