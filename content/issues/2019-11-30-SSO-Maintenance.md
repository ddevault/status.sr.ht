---
title: Intermittent outages during maintenance
date: 2019-11-30 15:00:00
resolved: true
resolvedWhen: 2019-11-30 15:45:00
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
  - dispatch.sr.ht
section: issue
---

**Deployments complete**:
The deployment has been completed for all services and no issues have been
found. Service should be operating normally.
{{< track "2019-11-30 15:45:00" >}}

**Ongoing deployment causing service disruption**:
We are currently deploying a major change in the Sourcehut architecture, which
is likely to cause intermittent outages during deployment as services are
rotated onto the new system and oversights are discovered and resolved.
{{< track "2019-11-30 15:00:00" >}}
