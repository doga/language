# language

ES6 JavaScript module for looking up [ISO 639-1 language code](https://en.wikipedia.org/wiki/ISO_639-1) info.

## Importing this library

```js
import { Language } from "https://esm.sh/gh/doga/language@1.0.1/mod.mjs";
```

## Usage

_Tip: Run the following example by typing this in your terminal (requires [Deno](https://deno.land)):_

```shell
deno run \
  --allow-net --allow-run --allow-env --allow-read \
  https://deno.land/x/mdrb/mod.ts \
  --dax=false \
  https://raw.githubusercontent.com/doga/object-semantic-mapping/main/README.md
```

<details data-mdrb>
<summary>Print out language info for some language codes.</summary>

<pre>
description = '''
Running this example is safe, it will not read or write anything to your filesystem.
'''
</pre>
</details>

```javascript
// import { I18nString, Person } from "https://esm.sh/gh/doga/object-semantic-mapping@0.1.5/mod.mjs";
// import { Qworum } from "https://esm.sh/gh/doga/qworum-for-web-pages@1.3.5/mod.mjs";
import { Language } from "https://esm.sh/gh/doga/language@1.0.1/mod.mjs";

['en', 'fr', 'de', 'tr'].forEach(iso639_1 => {
    console.info(`Language info for ${JSON.stringify(iso639_1)}:`);
    console.info(`  ISO 639-1:   ${JSON.stringify(iso639_1.code639_1)}`);
    console.info(`  ISO 639-2:   ${JSON.stringify(iso639_1.code639_2)}`);
    console.info(`  Family:      ${JSON.stringify(iso639_1.family)}`);
    console.info(`  Name:        ${JSON.stringify(iso639_1.name)}`);
    console.info(`  Native name: ${JSON.stringify(iso639_1.nativeName)}`);
    console.info(`  Wiki URL:    ${JSON.stringify(iso639_1.wikiUrl)}`);
});
```

Sample output for the code above:

```text

```

∎
