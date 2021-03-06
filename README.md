[![npm version](https://badge.fury.io/js/adblock-minus.svg)](http://badge.fury.io/js/adblock-minus)
[![Build Status](https://travis-ci.org/xiaody/adblock-minus.svg?branch=master)](https://travis-ci.org/xiaody/adblock-minus)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com/)
[![Test Coverage](https://codeclimate.com/github/xiaody/adblock-minus/badges/coverage.svg)](https://codeclimate.com/github/xiaody/adblock-minus/coverage)
[![dependencies Status](https://david-dm.org/xiaody/adblock-minus/status.svg)](https://david-dm.org/xiaody/adblock-minus)
[![devDependencies Status](https://david-dm.org/xiaody/adblock-minus/dev-status.svg)](https://david-dm.org/xiaody/adblock-minus?type=dev)
[![NSP Status](https://nodesecurity.io/orgs/adblock-minus/projects/b9a21295-2771-4654-87f5-00a811eef867/badge)](https://nodesecurity.io/orgs/adblock-minus/projects/b9a21295-2771-4654-87f5-00a811eef867)

A plain JavaScript implementation of adblocking that understands most [Adblock Plus filters](https://adblockplus.org/filters) syntax.

The package also contains a runnable Chrome extension demo, could be a good usage guide and starting point for your work.

To run the demo:

```
npm install && npm run build
```

then load the `build` folder via Chrome extensions page.

Or quick install via [Chrome web store](https://chrome.google.com/webstore/detail/adblock-minus/kokiipohaahehocgnfaleknlfblmcagh)


## Install

`npm install --save adblock-minus`



## Usage

```javascript
const adblock = require('adblock-minus')
const blocker = new adblock.Blocker()

const target = 'http://evil.com/ad.gif'
blocker.match(target) // => false
blocker.add('||evil.com/ad.')
blocker.match(target) // => true

blocker.add('evil.com###adbanner')
for (const selector of blocker.selectors('evil.com')) {
  console.log(selector) // => ['#adbanner']
}
```
