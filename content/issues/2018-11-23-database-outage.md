---
title: Database RAID failure
date: 2018-11-23 18:00:00
resolved: false
resolvedWhen: 2018-05-25 04:40:00
# down, disrupted, notice
severity: down
affected:
  - builds.sr.ht
  - git.sr.ht
  - meta.sr.ht
section: issue
---

*Resolving*
An issue with one of the hard drives on one of our database servers was
discovered, resulting in a total outage for this server. The RAID array is being
rebuilt and service is expected to be restored within a few hours.
{{< track "2018-11-23 20:00:00" >}}

*Investigating*
One of our database servers has gone offline and is unresponsive. The issue will
require manual intervention at the datacenter, but the NOC is slow to respond
during the holiday weekend. Once we gain access to the server, an update will be
posted.
{{< track "2018-11-23 18:00:00" >}}
