# Two Sapper Pages

## Showcasing Problem With Generated Service Worker
The main page is deployed at the root, the sub page is deployed under the route subpage. This minimal example is set up to show case the mismatch in the precached files of both generated service-workers, which is related to the static folder structure.

To generate the files use `npm run export`.

## Showcasing Problem When Using Custom server.js and service-worker.js
When changing the input filename for the `server.js` or `service-worker.js` in `rollup.config.js`, then other parts of sapper breaks. Most notably the debugging function called with `node --inspect node_modules/sapper/dist/cli.js dev`. There is also no possibility to have two different debugging functions for each sapper application.

## Build Problem When Using Custom client.js
When changing the input filename of `client.js` in the same way as the serviceworker in `rollup.config.js` then sapper cli dev|build|export fails with the error **Could not resolve entry module (src/client.js).**