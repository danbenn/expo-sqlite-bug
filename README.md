# expo-sqlite-module-bug

## Repro Steps
1. Clone this repo
2. `expo start`
3. Error: `Unable to resolve "./assets/sample.db" from "App.js"`

## How I created this
1. `sqlite3 sample.db "create table verses(field1 int);"`
1. `expo init sqlite-module-bug`
1. added this in App.js:
```
const sampleDatabase = require('./assets/sample.db');
```
1. Updated packager settings:
```
"assetBundlePatterns": [
  "assets/*"
],
"packagerOpts": {
  "assetExts": ["db"]
}
```
That's it.
