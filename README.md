# incredibleconsulting.org: Typo-Catch & Defensive Domain

**Domain:** incredibleconsulting.org
**Role:** Defensive · Typo-catch for incredible-consulting.org, minimal landing
**Priority:** Phase 4
**Strategy doc:** internal, not linked from here

## Purpose
The unhyphenated variant of incredible-consulting.org. Its only job is to catch mistyped traffic and hand it off cleanly to the right consulting site. Deliberately small: a landing page with two onward routes, a disambiguation page, a documented redirect and canonical policy, and a contact fallback. No services, no pricing, no case studies. If a topic belongs to a sibling domain, this site links to it instead of duplicating it.

## Key Features / Sections
- Landing page with the two onward routes (commercial and open methodology)
- "Which site do you want" disambiguation page covering the whole portfolio
- Redirect and canonical policy note documenting the intended 301 target
- Contact fallback: one address, one booking link, no forms
- Routing table versioned in `data/routes.yaml`
- No indexing, no tracking, no newsletter, no lead capture

## Monetization
None. Brand protection and traffic recovery only. Every commercial intent is routed to incredible-consulting.com.

## Content map
```
incredibleconsulting.org/
├── hugo.toml
├── README.md
├── Makefile
├── .gitignore
├── archetypes/
│   └── default.md
├── content/
│   ├── _index.md              Landing page, two onward routes
│   ├── which-site.md          Disambiguation across the portfolio
│   ├── redirect-policy.md     301 target, canonical policy, path mapping
│   └── contact.md             Contact fallback, no forms
├── data/
│   └── routes.yaml            Onward route schema, 3 seeded entries
├── layouts/                   Empty, theming is a later pass
│   └── .gitkeep
└── static/
    └── .gitkeep
```

Four markdown content files, by design. If this tree grows, the domain has stopped doing its job.

## Relationship to other Incredible domains
- **incredible-consulting.com** is the canonical consulting domain and the default 301 target. Anything commercial goes here.
- **incredible-consulting.org** is the domain this one is defending: same name, one hyphen. Anyone who typed .org deliberately probably wants the open methodology site.
- **incredible-company.com** is the umbrella brand, the legal entity, and the source of the shared contact address. It is the fallback when intent cannot be classified.
- **incredible.builders**, **incredible.community**, and **incredible.training** are listed once on the disambiguation page as overflow routes for practitioners, members, and learners. They are never duplicated here.

## Routing state
Current mode: a thin landing page at the root, HTTP 301 to https://incredible-consulting.com/ for every deep path. Every page declares the commercial site as canonical and this domain is excluded from indexing. See `content/redirect-policy.md` for the switch condition that would turn the root into a full redirect too.

## Local development
```
make dev      # hugo server, auto-increments the port if 1313 is busy
make build    # hugo --gc --minify
make clean    # remove public, resources/_gen, .hugo_build.lock
```
