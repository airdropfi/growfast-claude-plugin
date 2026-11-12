---
description: Show GrowFast Reddit monitors and matches, or set up Reddit listening for a product
---

Reddit listening for: $ARGUMENTS

1. Call `list_reddit_monitors` and show the products being monitored with their keywords.
2. If the user named a monitored product, call `list_reddit_matches` for it (status new unless they ask otherwise) and show each post title, subreddit and drafted reply. Remind the user to read the thread, follow the subreddit's rules and say they made the product before they post it themselves from https://growfast.sh. Nothing is posted from here.
3. To set up or change listening, collect the product domain, name, a one-sentence pitch and up to 6 keywords. If the product already has a monitor, say that `set_reddit_monitor` replaces its settings and wait for a clear yes. Then call `set_reddit_monitor` and confirm what it will listen for.
