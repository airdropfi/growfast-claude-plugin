---
description: Scan a product site with GrowFast and list the best-fit customers (saves the scan)
---

Scan the product at this domain: $ARGUMENTS

If no domain was given, ask for one and stop.

1. Tell the user that scanning takes about 30 seconds and saves the scan to their GrowFast account, then call `scan_domain` with the domain.
2. Report, exactly as returned: the ideal customer profile, the drafted first email and each fitting company with its 1-10 score and reason.
3. Offer the next step: draft emails for chosen companies (the `find-customers` skill). Nothing is sent or posted from here; GrowFast sends from https://growfast.sh.
