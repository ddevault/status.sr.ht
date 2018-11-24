---
title: Service disruption
date: 2018-11-24 19:39:00
resolved: false
resolvedWhen: 2018-11-24 20:42:00
# down, disrupted, notice
severity: disrupted
affected:
  - builds.sr.ht
  - git.sr.ht
  - lists.sr.ht
  - meta.sr.ht
section: issue
---

**Replacing the database server**:
The database server has been taken out of service for maintenance, and in the
meantime I'm provisioning a replacement. I believe that there has been no data
loss.
{{< track "2018-11-24 22:06:00" >}}

**Reopened**:
Failures are back up. Investigating.
{{< track "2018-11-24 21:03:00" >}}

**Resolved**:
The issue has been resolved, and we're monitoring the system for more
information.
{{< track "2018-11-24 20:42:00" >}}

**Investigating**:
The same database server causing issues yesterday is causing more problems
today. Investigating.
{{< track "2018-11-24 19:40:00" >}}
