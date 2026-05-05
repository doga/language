# language

A JavaScript library for handling:

- [ISO 639 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes).
- [RFC 5646 language tags](https://www.rfc-editor.org/rfc/rfc5646).

## Importing this library

`import { Language, lang, LanguageTag, langTag } from "https://esm.sh/gh/doga/language@1.1.0/mod.mjs";`

## Usage example

<details data-mdrb>
<summary>Print out language info for some language codes.</summary>

<pre>
description = '''
Running this example is safe, it will not read or write anything to your filesystem.
'''
</pre>
</details>

```javascript
import {
  langTag, lang, LanguageTag, Language
} from "https://esm.sh/gh/doga/language@1.1.0/mod.mjs";

// Parse ISO 639 language codes.
['en', 'fr', 'de', 'tr'].forEach(iso639_1 => {
    const language = lang`${iso639_1}`;
    if(!language)return;
    console.group(`Language code: ${language}:`);
    console.info(`ISO 639-1:   ${language.iso639_1}`);
    console.info(`ISO 639-2:   ${language.iso639_2}`);
    console.info(`Name:        ${language.name}`);
    console.info(`Native name: ${language.nativeName}`);
    console.info(`Family:      ${language.family}`);
    console.info(`Wiki URL:    ${language.wikiUrl}`);
    console.groupEnd();
});

// Parse RFC 5646 language tags.
['en-CA', 'fr-FR', 'de-AT', 'tr'].forEach(tag => {
    const languageTag = langTag`${tag}`;
    if(!languageTag)return;
    console.group(`Language tag: ${languageTag}`);
    console.group(`ISO 639 language info:`);
    console.info(`ISO 639-1:   ${languageTag.code.iso639_1}`);
    console.info(`ISO 639-2:   ${languageTag.code.iso639_2}`);
    console.info(`Name:        ${languageTag.code.name}`);
    console.info(`Native name: ${languageTag.code.nativeName}`);
    console.info(`Family:      ${languageTag.code.family}`);
    console.info(`Wiki URL:    ${languageTag.code.wikiUrl}`);
    console.groupEnd();
    console.groupEnd();
});
```

Sample output for the code above:

```text
Language code: en:
  ISO 639-1:   en
  ISO 639-2:   eng
  Name:        English
  Native name: English
  Family:      Indo-European
  Wiki URL:    https://en.wikipedia.org/wiki/English_language
Language code: fr:
  ISO 639-1:   fr
  ISO 639-2:   fra
  Name:        French
  Native name: français, langue française
  Family:      Indo-European
  Wiki URL:    https://en.wikipedia.org/wiki/French_language
Language code: de:
  ISO 639-1:   de
  ISO 639-2:   deu
  Name:        German
  Native name: Deutsch
  Family:      Indo-European
  Wiki URL:    https://en.wikipedia.org/wiki/German_language
Language code: tr:
  ISO 639-1:   tr
  ISO 639-2:   tur
  Name:        Turkish
  Native name: Türkçe
  Family:      Turkic
  Wiki URL:    https://en.wikipedia.org/wiki/Turkish_language
Language tag: en-CA
  ISO 639 language info:
    ISO 639-1:   en
    ISO 639-2:   eng
    Name:        English
    Native name: English
    Family:      Indo-European
    Wiki URL:    https://en.wikipedia.org/wiki/English_language
Language tag: fr-FR
  ISO 639 language info:
    ISO 639-1:   fr
    ISO 639-2:   fra
    Name:        French
    Native name: français, langue française
    Family:      Indo-European
    Wiki URL:    https://en.wikipedia.org/wiki/French_language
Language tag: de-AT
  ISO 639 language info:
    ISO 639-1:   de
    ISO 639-2:   deu
    Name:        German
    Native name: Deutsch
    Family:      Indo-European
    Wiki URL:    https://en.wikipedia.org/wiki/German_language
Language tag: tr
  ISO 639 language info:
    ISO 639-1:   tr
    ISO 639-2:   tur
    Name:        Turkish
    Native name: Türkçe
    Family:      Turkic
    Wiki URL:    https://en.wikipedia.org/wiki/Turkish_language
```

## Running the usage example

Run the usage example by typing this in your terminal (requires [Deno](https://deno.com)+):

```shell
deno run --allow-net --allow-run --allow-env --allow-read jsr:@andrewbrey/mdrb@3.0.4 --dax=false --mode=isolated 'https://raw.githubusercontent.com/doga/language/main/README.md'
```

∎
