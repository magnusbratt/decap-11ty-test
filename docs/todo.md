# todo

- [ ] Startsida
- [ ] Definiera taggar
- [ ] migrera från Wordpress
- [ ] Dokumentera taggar vi ska använda. Editorial guidelines.
- [ ] Dokumentera olika typer av content: FAQ, HOWITWORKS, Case, Interview, etc.
- [ ] Hosting
    - Domain
    - Cert
- Features
    - [ ] Sök
        - Fuse.js
        - Algolia
    - [ ] Visitor statistics
        - GA4?
        - https://plausible.io/#pricing
        - Matomo. Har stöd för UserId
    - [ ] Cookie management
    - [ ] GTM
- [ ] Brief
- [ ] färgschema. Fråga ChatGPT och ta in i bootstrap
- [ ] Disposition iPad Portrait och ladndscape
- [ ] testa utan gradient
- [ ] ta bort skugga på cards
- [ ] 

# todo senare
- byt till standard mappstruktur och filnamn. Ev börja om med en ren start med bootstrap
- sätt upp Decap CMS att redigera vanliga sidor, inte bara blogg
- använd bootstrap via npm inte cdn? Vad är för- och nackdelar?


# Taggar
FAQ
HOWTO
HOWITWORKS
Blog post
(Offering)
(kund)

# migrera från Wordpress

# sitemap

# Design home page

- Top row
    - Logo
    - search
    - menu
    - button book a demo 
    - button login
- Row two
    - left
        - slogan
        - book a demo
        - chat box
    - right: screen shot
- Row tree: logos
- Row four: three columns / masonry: blog, events, pinned posts. USPs?
- row five: features
- row six: princing

## Color schema
https://www.youtube.com/watch?v=vvPklRN0Tco&list=LL&index=6

## Inspiration
https://www.home-assistant.io/
- ser inte ut exakt som alla andra saas
- masonry lockar till scroll
- lyfter fram blog posts och release ntoes. Vi kan ha evenemang
- 

https://www.hubspot.com/
https://buildexcellentwebsit.es/
https://evernote.com/
https://sanalabs.com/


https://www.cursor.com/
https://www.synthesia.io/
https://dust.tt/
https://www.notion.com/
https://linear.app/

https://www.upsales.com/

https://runwayml.com/ - AI chatt
https://fin.ai/

# integrera EXF för sign ups

# Cookie hantering
https://www.cookiebot.com/en/what-is-behind-powered-by-cookiebot/

# Budskap
Nordiskt
GDPR compliant

AI
- intercom eller konvolo direkt på startsidan?

Pyramiden
Best of both worlds

Opinionated
Video?



# 2025-07-06

# hero > secondary bör vara inverterad. 
# search expandderar inte längre
# balans hero olika storlekar. 

# bli av med sass-varningar
Deprecation Warning [import]: Sass @import rules are deprecated and will be removed in Dart Sass 3.0.0.

More info and automated migrator: https://sass-lang.com/d/import

  ╷
1 │ @import "mixins/banner";
  │         ^^^^^^^^^^^^^^^
  ╵
    node_modules\bootstrap\scss\bootstrap.scss 1:9  @use
    src\scss\main.scss 13:1                         root stylesheet

Deprecation Warning [import]: Sass @import rules are deprecated and will be removed in Dart Sass 3.0.0.

More info and automated migrator: https://sass-lang.com/d/import

  ╷
7 │ @import "functions";
  │         ^^^^^^^^^^^
  ╵
    node_modules\bootstrap\scss\bootstrap.scss 7:9  @use
    src\scss\main.scss 13:1                         root stylesheet

Deprecation Warning [import]: Sass @import rules are deprecated and will be removed in Dart Sass 3.0.0.