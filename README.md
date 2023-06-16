<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.sining

Bahagi ng code ng website ay open source, malugod na tumulong sa pag-optimize ng pagsasalin.

## front-end na code

* [front-end na code](https://github.com/xxai-art/web)
* [Language pack para sa site sa kabuuan](https://github.com/xxai-art/web/tree/main/i18n)
* [Language pack para sa mga module sa pag-log in](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Website na Multilingual Documentation](https://github.com/xxai-doc)

Ang front-end programming language ay [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , na nagdaragdag ng ilang feature batay sa coffeescript syntax, tingnan [ang ./coffee_plus.md](./coffee_plus.md) .

## Internasyonalisasyon ng mga website at dokumento

Bumuo sa sumusunod na 3 proyekto

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Ang suffix ay `.mdt` , maaari mong gamitin ang syntax na katulad ng `<+ ./coffee_plus/import.js>` para sumangguni sa mga external na file, at bumuo ng markdown gamit ang suffix `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Hindi isasalin ng Markdown translation ang mga code at link, at i-cache ang mga isinaling pangungusap. Kung ang pagsasalin ay binago ngunit ang orihinal na teksto ay hindi binago, ang muling pagpapatupad nito ay hindi mapapatungan ang pagbabago ng pagsasalin.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Mga file ng wika para sa pagsasalin ng mga website na nabuo ng `yaml` .
