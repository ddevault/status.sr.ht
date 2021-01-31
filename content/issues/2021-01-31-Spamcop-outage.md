---
title: Spamcop outage
date: 2021-01-31 10:30:00
resolved: true
resolvedWhen: 2021-01-31 13:25:00
severity: notice
affected:
  - todo.sr.ht
  - lists.sr.ht
section: issue
---

**One of our third-party DNSBL service, SpamCop, allowed their domain to
expire**, presumably as a mistake, and began to return "listed" for all DNSBL
checks. We use a DNSBL as an early rejection for spam emails, and this caused
21 incoming emails to be wrongfully rejected. We have removed SpamCop from our
list of DNSBLs and filed a ticket to [improve our
monitoring](https://todo.sr.ht/~sircmpwn/sr.ht-ops/6) so that we may catch this
sooner. Incoming emails are working now, but be advised that if your postmaster
uses SpamCop, emails *from* Sourcehut will likely be rejected until the issue is
resolved.
{{< track "2021-01-31 13:25:00" >}}

