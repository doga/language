# language

ES6 JavaScript module for looking up [ISO 639-1 language code](https://en.wikipedia.org/wiki/ISO_639-1) info.

## Importing this library

`import { Language } from "https://esm.sh/gh/doga/language@1.0.2/mod.mjs";`

## Usage

_Tip: Run the following example by typing this in your terminal (requires [Deno](https://deno.land)):_

```shell
deno run \
  --allow-net --allow-run --allow-env --allow-read \
  https://deno.land/x/mdrb/mod.ts \
  https://raw.githubusercontent.com/doga/language/main/README.md
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
import { Language } from "https://esm.sh/gh/doga/language@1.0.2/mod.mjs";

['en', 'fr', 'de', 'tr'].forEach(iso639_1 => {
    const lang = Language.fromCode(iso639_1);
    if(!lang)return;
    console.info(`Language info for ${lang}:`);
    console.info(`  ISO 639-1:   ${JSON.stringify(lang.iso639_1)}`);
    console.info(`  ISO 639-2:   ${JSON.stringify(lang.iso639_2)}`);
    console.info(`  Family:      ${JSON.stringify(lang.family)}`);
    console.info(`  Name:        ${JSON.stringify(lang.name)}`);
    console.info(`  Native name: ${JSON.stringify(lang.nativeName)}`);
    console.info(`  Wiki URL:    ${JSON.stringify(lang.wikiUrl)}`);
});
```

Sample output for the code above:

```text
Language info for en:
  ISO 639-1:   "en"
  ISO 639-2:   "eng"
  Family:      "Indo-European"
  Name:        "English"
  Native name: "English"
  Wiki URL:    "https://en.wikipedia.org/wiki/English_language"
Language info for fr:
  ISO 639-1:   "fr"
  ISO 639-2:   "fra"
  Family:      "Indo-European"
  Name:        "French"
  Native name: "français, langue française"
  Wiki URL:    "https://en.wikipedia.org/wiki/French_language"
Language info for de:
  ISO 639-1:   "de"
  ISO 639-2:   "deu"
  Family:      "Indo-European"
  Name:        "German"
  Native name: "Deutsch"
  Wiki URL:    "https://en.wikipedia.org/wiki/German_language"
Language info for tr:
  ISO 639-1:   "tr"
  ISO 639-2:   "tur"
  Family:      "Turkic"
  Name:        "Turkish"
  Native name: "Türkçe"
  Wiki URL:    "https://en.wikipedia.org/wiki/Turkish_language"
```

∎
