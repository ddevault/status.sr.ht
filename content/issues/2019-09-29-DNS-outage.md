---
title: Major DNS outage
date: 2019-09-29 18:00:00
resolved: false
resolvedWhen:
# down, disrupted, notice
severity: down
affected:
  - builds.sr.ht
  - git.sr.ht
  - lists.sr.ht
  - meta.sr.ht
  - todo.sr.ht
  - hg.sr.ht
  - paste.sr.ht
section: issue
---

**No response**
We are still waiting for an update from our registrar.
{{< track "2019-09-29 20:00:00" >}}

**Major DNS outage**:
While deploying IPv6 support across Sourcehut, we submitted a routine request to
our domain registrar to add IPv6 glue records for our nameservers. In the course
of doing this, the registrar also removed the IPv4 glue records. We are
attempting to reach them for assistance. Services are severely disrupted in the
meantime.
{{< track "2019-09-29 10:00:00" >}}
