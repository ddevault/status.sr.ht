---
title: Unplanned git.sr.ht outage
date: 2021-05-14 12:00:00
resolved: true
resolvedWhen: 2021-05-14 15:50:00
severity: disrupted
affected:
  - git.sr.ht
section: issue
---

**Snapshot growth caused an outage on git.sr.ht**

git.sr.ht's ZFS snapshots grew to consume all available disk space. This is
normally an understood pathology of the server configuration, but due to a
change in billing with Twilio, our paging script did not alert the operators to
the imminent issue. It seems that there is not a grace period with Twilio; they
reported the billing issue to us only yesterday.

The issue with git.sr.ht has been resolved, the bill has been paid, and we are
researching ways to avoid this occuring again in the future.
{{< track "2021-05-14 15:00:00" >}}
