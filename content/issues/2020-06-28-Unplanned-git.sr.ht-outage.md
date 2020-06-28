---
title: Unplanned git.sr.ht web outage
date: 2020-06-28 12:07:00
resolved: true
resolvedWhen: 2020-06-28 12:53:00
severity: disrupted
affected:
  - git.sr.ht
section: issue
---

**An unexpected Redis failure caused a partial outage of git.sr.ht**

The git.sr.ht web service was partially interrupted today due to unexpected
Redis errors. Some pages which rely on Redis for caching returned 500 errors,
namely the summary and tree pages.

The issue has been resolved. To prevent its recurrence, we have [filed a
ticket](https://todo.sr.ht/~sircmpwn/sr.ht/251) to make our caching system more
tolerant of Redis outages, and
[added an alarm](https://lists.sr.ht/~sircmpwn/sr.ht-dev/patches/11360) to
[detect](https://metrics.sr.ht/graph?g0.range_input=6h&g0.end_input=2020-06-28%2015%3A25&g0.expr=rate(http_requests_total%7Bstatus%3D%22500%22%7D%5B10m%5D)%20%3E%205%2F60&g0.tab=0)
this kind of issue earlier.
{{< track "2020-06-28 12:07:00" >}}
