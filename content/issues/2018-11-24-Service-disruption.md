---
title: Service disruption
date: 2018-11-24 19:39:00
resolved: true
resolvedWhen: 2018-11-24 20:42:00
# down, disrupted, notice
severity: disrupted
affected:
  - builds.sr.ht
section: issue
---

**Debian & FreeBSD builds now available**:
Full service has been restored.
{{< track "2018-11-27 03:54:00" >}}

**Arch Linux builds now available**:
Arch is available and Debian is coming.
{{< track "2018-11-25 18:01:00" >}}

**Alpine builds now available**:
The next step is to start pulling build images down to the new build runner.
Currently Alpine is available and Arch is being worked on next.
{{< track "2018-11-25 17:01:00" >}}

**Restoring builds service**:
Work is ongoing to provision a new build host. Service is expected to be
restored within a few hours.
{{< track "2018-11-25 15:23:00" >}}

**Temporary database server provisioned**:
Full service has been restored to all services except for builds.sr.ht, which
requires the provisioning of a new build slave. Until then no builds will be
run.
{{< track "2018-11-24 22:34:00" >}}

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
