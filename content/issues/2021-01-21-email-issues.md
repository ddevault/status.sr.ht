---
title: Email issues
date: 2021-01-21 19:00:00
resolved: true
resolvedWhen: 2021-01-21 19:45:00
severity: notice
affected:
  - todo.sr.ht
  - lists.sr.ht
section: issue
---

**An issue with mail delivery caused some emails to be dropped**. Upgrades to
our mail server caused authentication to unexpectedly and silently fail, and it
took some time to detect. During this period, ticket submission to todo.sr.ht
failed, and emails were not forwarded from lists.sr.ht. You can thank Oracle for
changing the license terms on Berkely DB, which had wider reaching consequences
than we expected.
{{< track "2021-01-21 19:00:00" >}}

