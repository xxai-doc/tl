<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Inirerekomenda na i-install muna ang nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , at pagkatapos ay `direnv allow` pagkatapos na makapasok sa direktoryo ( [ang .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) ay awtomatikong isasagawa pagkatapos na makapasok sa direktoryo).

Ang kahulugan ay: pagsasalin ng Chinese sa Japanese, Korean, English, English, translation sa lahat ng iba pang wika. Kung gusto mo lang suportahan ang Chinese at English, maaari mo lang isulat `zh: en` .

Ang kahulugan ay: pagsasalin ng Chinese sa Japanese, Korean, English, English, translation sa lahat ng iba pang wika. Kung gusto mo lang suportahan ang Chinese at English, maaari mo lang isulat `zh: en` .

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

### Mga Tagubilin sa Automation sa Pagsasalin ng Dokumento

Tingnan ang code repository [xxai-art/doc](https://github.com/xxai-art/doc)

Inirerekomenda na i-install muna ang nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , at pagkatapos ay `direnv allow` pagkatapos na makapasok sa direktoryo ( [ang .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) ay awtomatikong isasagawa pagkatapos na makapasok sa direktoryo).

Upang maiwasan ang malaking code base na isinalin sa daan-daang wika, gumawa ako ng hiwalay na code base para sa bawat wika at gumawa ng organisasyon upang mag-imbak ng code base

Ang pagtatakda ng environment variable `GITHUB_ACCESS_TOKEN` at pagkatapos ay pagpapatakbo [ng create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) ay awtomatikong lilikha ng code repository.

Siyempre, maaari mo ring ilagay ito sa isang code base.

Sanggunian sa script ng pagsasalin [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Ang script code ay binibigyang kahulugan bilang mga sumusunod:

[Ang bunx](https://bun.sh/docs/cli/bunx) ay kapalit ng npx, na mas mabilis. Siyempre, kung wala kang naka-install na bun, maaari mong gamitin `npx` sa halip.

`bunx mdt zh` ay nag-render `.mdt` sa zh directory bilang `.md` , tingnan ang 2 naka-link na file sa ibaba

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` ay ang pangunahing code para sa pagsasalin (kung mayroon ka lang naka-install `nodejs` , ngunit hindi naka-install `bun` at `direnv` , maaari mo ring patakbuhin `npx i18n` upang magsalin).

Ipapa-parse nito [ang i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , ang configuration ng `i18n.yml` sa dokumentong ito ay ang sumusunod:

```
en:
zh: ja ko en
```

Ang kahulugan ay: pagsasalin ng Chinese sa Japanese, Korean, English, English, translation sa lahat ng iba pang wika. Kung gusto mo lang suportahan ang Chinese at English, maaari mo lang isulat `zh: en` .

Ang huli ay [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , na kinukuha ang nilalaman sa pagitan ng pangunahing pamagat at ang unang subtitle ng `README.md` ng bawat wika upang makabuo ng entry na `README.md` . Ang code ay napaka-simple, maaari mong tingnan ito sa iyong sarili.

Ginagamit ang Google API para sa libreng pagsasalin. Kung hindi mo ma-access ang Google, mangyaring mag-configure at magtakda ng proxy, gaya ng:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Ang script ng pagsasalin ay bubuo ng isinalin na cache sa `.i18n` na direktoryo, pakisuri ito gamit ang `git status` at idagdag ito sa code repository upang maiwasan ang mga paulit-ulit na pagsasalin.

Mangyaring patakbuhin `bunx i18n` sa tuwing babaguhin mo ang pagsasalin upang i-update ang cache.

Kung ang orihinal na teksto at ang pagsasalin ay binago sa parehong oras, ang cache ay malito, kaya kung gusto mong baguhin, maaari mo lamang baguhin ang isa, at pagkatapos ay patakbuhin `bunx i18n` upang i-update ang cache.
