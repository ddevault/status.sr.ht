---
title: Major DNS outage
date: 2019-09-29 18:00:00
resolved: true
resolvedWhen: 2019-09-29 21:45:00
# down, disrupted, notice
severity: disrupted
affected:
  - builds.sr.ht
  - git.sr.ht
  - lists.sr.ht
  - meta.sr.ht
  - todo.sr.ht
  - hg.sr.ht
  - paste.sr.ht
  - man.sr.ht
  - dispatch.sr.ht
section: issue
---

**Resolved**
The issue has been fixed. It may take time for DNS updates to propegate to your
local server.
{{< track "2019-09-29 21:45:00" >}}

**Working on the issue**
We have reached support and they've rolled back the changes. We're monitoring
our services to make sure the trasition occurs smoothly.
{{< track "2019-09-29 21:00:00" >}}

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
