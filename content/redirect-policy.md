---
title: "Redirect and Canonical Policy"
description: "What this domain does with traffic, where the 301 points, and why the landing page exists at all."
weight: 20
draft: false
image: "img/mood/mechanism.webp"
page_type: "policy"
canonical_target: "https://incredible-consulting.com/"
redirect_status: 301
redirect_scope: "all paths except the site root"
current_mode: "landing page at root, 301 for deep paths"
review_cadence: "annual, at domain renewal"
---

**Purpose.** Document the intended routing behaviour for anyone maintaining the portfolio, and give search engines and humans a single honest explanation of what this domain is for.

**Contains.**
- The rule in one sentence: incredibleconsulting.org is a defensive registration whose canonical target is https://incredible-consulting.com/
- Current mode: a thin landing page served at the root, HTTP 301 for every deep path, so a mistyped deep link still lands somewhere useful
- Why the root is not redirected yet: a one click choice between the commercial and the open site beats guessing wrong for half the traffic
- The switch condition for going full 301 at the root, and who decides it
- Canonical tag policy: every page here declares the commercial site as canonical, and this domain is excluded from indexing
- Path mapping table, backed by data/routes.yaml, so the intended targets are versioned rather than tribal knowledge
- Note that the domain is renewed for brand protection only and carries no revenue

**Primary CTA.** Maintainers: change routing here first, then in DNS and the edge config. Visitors: go to the canonical site.
**Links to.** /which-site/, https://incredible-consulting.com/, https://incredible-company.com/
