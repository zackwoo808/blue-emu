# blue-emu

### *For security research purposes only. Not for production use.*

## Table of Contents

- [Background](#background)
- [Overview](#overview)

## <a name="background"></a> Background

- https://www.bleepingcomputer.com/news/security/researcher-hacks-over-35-tech-firms-in-novel-supply-chain-attack/
- https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610
- https://azure.microsoft.com/mediahandler/files/resourcefiles/3-ways-to-mitigate-risk-using-private-package-feeds/3%20Ways%20to%20Mitigate%20Risk%20When%20Using%20Private%20Package%20Feeds%20-%20v1.0.pdf

## <a name="overview"></a> Overview

### tldr;
it looks like if someone were to create a public package with a higher version than the internal package, this could potentially compromise a site.

-

Currently, we're under the assumption that we look for a private package withing an internal registry and find it, we don't look for newer packages externally.

1. Figure out the actual process we're using to locate internal vs external packages.
2. See if we need to make any changes in how our process works to avoid any potential leaks.
3. Verify that no manifest files for our projects are public.

## Usage

```sh
$ npm install --save blue-emu
```

Require module in `app/index.js`

```js
require('blue-emu');
```

Look for console log during app startup. Verify that it says *`public test`* and not *`private test`*.

```
*************** blue-emu public test ***************
```
