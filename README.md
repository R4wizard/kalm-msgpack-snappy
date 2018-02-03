# kalm-msgpack-snappy

[msgpack](http://msgpack.org/) and [snappy](https://google.github.io/snappy/) [serializer](https://github.com/kalm/kalm.js/wiki/Serials) for [Kalm](https://github.com/kalm/kalm.js)

[![kalm-msgpack](https://img.shields.io/npm/v/kalm-msgpack-snappy.svg)](https://www.npmjs.com/package/kalm-msgpack-snappy)
[![Node](https://img.shields.io/badge/node->%3D4.0-blue.svg)](https://nodejs.org)
[![Dependencies Status](https://david-dm.org/r4wizard/kalm-msgpack-snappy.svg)](https://david-dm.org/kalm/kalm-msgpack-snappy)

## Install

    npm install kalm-msgpack-snappy


## Usage

Setting up your server:

```node
    const Kalm = require('kalm');
    const msgpacksnappy = require('kalm-msgpack-snappy');

    const server = Kalm.listen({
        port: 3000,
        serial: msgpacksnappy
    });

    server.on('connection', (client) => {
        client.subscribe('/', (data) => {
            console.log(data);  // 'Hello from Browser!'
        });
    });

```

Using in your browser:

```node
    // Install kalm and kalm-msgpack-snappy via a package manager (recommended).

    import Kalm from 'kalm';
    import msgpacksnappy from 'kalm-msgpack-snappy';

    const client = Kalm.connect({
        hostname: '127.0.0.1',  // Your server's hostname
        port: 3000,             // Your server's port
        serial: msgpacksnappy
    });

    client.write('Hello from Browser');

```


## Contribute

Please do! This is an open source project - if you see something that you want, [open an issue](//github.com/r4wizard/kalm-msgpack-snappy/issues/new) or file a pull request.

If you have a major change, it would be better to open an issue first so that we can talk about it.

I am always looking for more maintainers, as well. Get involved.


## License

[Apache 2.0](LICENSE) (c) 2017 Peter Corcoran - based on work by Frederic Charette ([kalm-msgpack](https://github.com/kalm/kalm-msgpack/) and [kalm-snappy](https://github.com/kalm/kalm-snappy/))
