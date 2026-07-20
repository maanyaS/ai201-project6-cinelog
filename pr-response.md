# PR Response Doc — CineLog Watchlist Feature

## AI Usage
1. Asked AI tool Claude to tell me how to approach each comment.
2. Asked Claude to understand the deduplication logic in add_to_collection()

## Comment 1 — Rename
**What I did: I renamed save_to_watchlist to add_to_watchlist per naming convention in services/watchlist_service.py. I also renamed the function call in routes/watchlist/watchlist.py. I found the call in this file using ctrl + f.**
**How I verified: I verified that I renamed the function in all files by hitting ctrl + f in all files to see whether the save_to_watchlist function was present in any of them.**

## Comment 2 — Deduplication
**What I did: I wrote a deduplication check in add_to_watchlist() and created an AlreadyInWatchlistError error when a film already appears in the user's watchlist.**
**How I verified: I verified this by checking the deduplication logic in add_to_collection() and writing my check with a similar pattern.**

## Comment 3 — Missing test
**What I did: I created a new file for the watchlist tests called test_watchlist.py. I added tests for nonexistent film_id in add_to_watchlist() in this file following the same fixture and assertion structure as test_add_to_collection_nonexistent_film_raises().**
**How I verified: I verified this test works by running the test and passing 100%.**

## Comment 4 — Default visibility
**My position:**
**Reasoning:**
**Tradeoff acknowledged:**

## Comment 5 — Sort order
**My position:**
**Reasoning:**
**Engagement with reviewer's point:**

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->
