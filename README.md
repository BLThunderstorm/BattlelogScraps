<div>
  <h1 align=center>BattlelogScraps</h1>
  <p align=center>This repository is where the team at BLTHunderstorm scraps the Battlefield Battlelog site.</p>
</div>

___

## Embedding this repo in your Javascript software
First, install this repo first as an NPM package.
```bash
yarn add https://github.com/BLThunderstorm/BattlelogScraps
```
Then you can import JSON files from this repo to your code.
```ts
import * as maps from 'battlelogscraps/maps.json';
import { BattlelogClient } from 'battlelog.js';
import type { Server } from 'battlelog.js';
let battlelog = new BattlelogClient();
let bf4 = battlelog.game("bf4");

bf4.fetchServers().forEach((guid: string, server: Server) => {
return console.log(`
---
Name: ${server.name}
GUID: ${server.guid}
Country: ${server.country}
Map: ${maps["bf4"][server.map] || server.map}
---
`)
} )

```

## License

This repository is licensed under [Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
