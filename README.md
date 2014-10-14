[![Build Status](https://travis-ci.org/tirithen/node-jsoncompress.svg?branch=master)](https://travis-ci.org/tirithen/node-jsoncompress)

# node-jsoncompress

A Node.js and browser JSON compression tool that uses JSON templates (inspired by https://github.com/Raveler/packetflattener), LZ, and optional float decimal reduction to compress JSON data for storage or sending over a network.

## Installation for Node.js

    $ cd /my/project/directory
    $ npm install jsoncompress --save

## Example for Node.js

    'use strict';

    var jsoncompress = require('jsoncompress');

    var data = { position: { x: 123.3432123, y: 3.2342233, z: 643.3423423 } };
    var template = { position: { x: 0, y: 0, z: 0 } };

    var compressed = jsoncompress.compress(data, template);
    console.log('Compressed string', compressed);

    var decompressed = jsoncompress.decompress(compressed, template);
    console.log('Decompressed and restored data', decompressed);

## Example for browser

    <script src="/path/to/jsoncompress.min.js"></script>
    <script>
        'use strict';

        var jsoncompress = require('jsoncompress');

        var data = { position: { x: 123.3432123, y: 3.2342233, z: 643.3423423 } };
        var template = { position: { x: 0, y: 0, z: 0 } };

        var compressed = jsoncompress.compress(data, template);
        console.log('Compressed string', compressed);

        var decompressed = jsoncompress.decompress(compressed, template);
        console.log('Decompressed and restored data', decompressed);
    </script>
