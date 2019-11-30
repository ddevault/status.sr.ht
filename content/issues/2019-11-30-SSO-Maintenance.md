---
title: Intermittent outages during maintenance
date: 2019-11-30 15:00:00
resolved: false
resolvedWhen: 2019-11-15 20:08:00
# down, disrupted, notice
severity: disrupted
affected:
  - meta.sr.ht
  - git.sr.ht
  - hg.sr.ht
  - todo.sr.ht
  - lists.sr.ht
  - builds.sr.ht
  - man.sr.ht
  - paste.sr.ht
section: issue
---

**Ongoing deployment causing service disruption**:
We are currently deploying a major change in the Sourcehut architecture, which
is likely to cause intermittent outages during deployment as services are
rotated onto the new system and oversights are discovered and resolved.
{{< track "2019-11-30 15:00:00" >}}
