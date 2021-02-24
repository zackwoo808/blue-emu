# blue-emu

*For security research purposes only. Not for production use.*

## Table of Contents

- [Background](#background)
- [Overview](#overview)

## Background

### https://www.bleepingcomputer.com/news/security/researcher-hacks-over-35-tech-firms-in-novel-supply-chain-attack/

## Overview

tldr; it looks like if someone were to create a public package with a higher version than the internal package, this could potentially compromise the site.

Currently, we're under the assumption that we look for internal package with npm.fandnago.com for our fd- libraries and if we find it, we don't look for newer packages externally.

1. Figure out the actual process we're using to locate internal vs external packages - this would be good in a how-to doc for take2
2. See if we need to make any changes in how our process works to avoid any potential leaks
3. Verify that no manifest files for our projects are public.

## Usage

```sh
$ npm install --save blue-emu
```

Require module in your ```app/index.js```
```js
require('blue-emu');
```

Look for console log during app startup. Verify that it says private test and not public test.
```
*************** blue-emu private test ***************
```
