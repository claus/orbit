# Orbit

> A distributed, peer-to-peer chat application built on [IPFS](http://ipfs.io)

[![Project Status](https://badge.waffle.io/haadcode/orbit.svg?label=In%20Progress&title=In%20Progress)](http://waffle.io/haadcode/orbit)
[![CircleCI Status](https://circleci.com/gh/haadcode/orbit.svg?style=shield&circle-token=158cdbe02f9dc4ca4cf84d8f54a8b17b4ed881a1)](https://circleci.com/gh/haadcode/orbit)

<img src="https://raw.githubusercontent.com/haadcode/orbit/master/screenshots/screenshot4%202016-04-16.png" width="80%">
<img src="https://raw.githubusercontent.com/haadcode/orbit/master/screenshots/screenshot3%202016-04-14.png" width="50%">
<img src="https://raw.githubusercontent.com/haadcode/orbit/master/screenshots/screenshot6%202016-04-17.png" width="50%">

## Run

***Please note that Orbit is not secure at the moment!***

### Browser

Open `client/dist/index.html` in your browser *(Chrome recommended!)*

The browser version uses [js-ipfs](http://github.com/ipfs/js-ipfs) library. 

Live demo: [http://orbit.libp2p.io/](http://orbit.libp2p.io)

### App

Orbit uses [Electron](http://electron.atom.io/) to wrap the application in a native executable. The Electron version of Orbit uses [go-ipfs](https://github.com/ipfs/go-ipfs) daemon. You don't need to have an IPFS daemon running to run Orbit.

#### Requirements

To build the Electron app, you will need to following tools:

- Node.js v6.x.x
- npm v3.x.x

#### Build the Electron app

```
npm install
npm build
```

The builds are in `dist/`. Eg. on OS X, open the application from `dist/Orbit-darwin-x64`.

## Development

### Requirements
- Node.js v6.x.x
- npm v3.x.x
- g++, gcc, make (for building native modules)
- python 2 (for building, some native modules need it, node-fibers perhaps?)

### Tests

*Note: requires a running redis-server*

```
npm install
npm test
```

### Build all
```
npm install
npm build
```

The builds are in `dist/`

## UI Development
```
cd client/
npm install
npm dev
```

This will open webpack dev-server at [localhost:8000/webpack-dev-server/](localhost:8000/webpack-dev-server/).

Build UI distributable:
```
cd client/
npm install
npm build
```

This will create `client/dist` directory which can be copied and distributed.

### UI Development with Electron
For UI development (webpack-dev-server in the Electron app).

Start Electron:
```
npm install
ENV=dev ./node_modules/.bin/electron . 
```

Start the webpack dev server:
```
cd client/
npm install
npm dev
```

## Run your own network
Get https://github.com/haadcode/orbit-server and start the server. In Orbit's login window, point to the host where your orbit-server is running.

## Contributing
Would be happy to accept PRs! If you want to work on something, it'd be good to talk beforehand to make sure nobody else is working on it. You can reach me on Twitter [@haadcode](https://twitter.com/haadcode) or on IRC #ipfs on Freenode.

Good place to start is to take a look at the ["help wanted" issues](https://github.com/haadcode/orbit/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22).

See [TODO](https://github.com/haadcode/orbit/blob/master/TODO.md) for ideas and tasks up for grabs.

## Orbit API

#### connect(url, username, password)
Connect to a network. `url` should be given as a string in the form of `host:port`.

TODO: return value, thrown errors, example

#### disconnect()
Disconnect from the currently connected network.

TODO: return value, thrown errors, example

#### join(channel)
Join a `channel`.

TODO: return value, thrown errors, example

#### leave(channel)
Leave a `channel`.

TODO: return value, thrown errors, example

#### send(channel, message)
Send a `message` to a `channel`. Channel must be joined first.

TODO: return value, thrown errors, example

#### get(channel, lessThanHash, greaterThanHash, amount)
Get messages from a channel. Returns a Promise that resolves to an `Array` of messages.

TODO: params, thrown errors, example

#### getPost(hash)
Get the contents of a message.

TODO: params, return value, thrown errors, example

#### addFile(channel, filePath || buffer)
Add a file to a `channel`. 

TODO: params, return value, thrown errors, example

#### getFile(hash)
Returns contents of a file from IPFS.

TODO: params, return value, thrown errors, example

#### getDirectory(hash)
Returns a directory listing as an `Array`

TODO: params, return value, thrown errors, example
