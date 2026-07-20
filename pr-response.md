# PR Response Doc — CineLog Watchlist Feature

## AI Usage
1. Asked AI tool Claude to tell me how to approach each comment.
2. Asked Claude to understand the deduplication logic in add_to_collection()
3. Used Claude to write the tests in comment 3 following the structure of tests in the test_collection.py file. All tests passed.

## Comment 1 — Rename
**What I did:** I renamed save_to_watchlist to add_to_watchlist per naming convention in services/watchlist_service.py. I also renamed the function call in routes/watchlist/watchlist.py. I found the call in this file using ctrl + f.
**How I verified:** I verified that I renamed the function in all files by hitting ctrl + f in all files to see whether the save_to_watchlist function was present in any of them.

## Comment 2 — Deduplication
**What I did:** I wrote a deduplication check in add_to_watchlist() and created an AlreadyInWatchlistError error when a film already appears in the user's watchlist.
**How I verified:** I verified this by checking the deduplication logic in add_to_collection() and writing my check with a similar pattern.

## Comment 3 — Missing test
**What I did:** I created a new file for the watchlist tests called test_watchlist.py. I added tests for nonexistent film_id in add_to_watchlist() in this file following the same fixture and assertion structure as test_add_to_collection_nonexistent_film_raises().
**How I verified:** I verified this test works by running the test and passing 100%.

## Comment 4 — Default visibility
**My position:** I stand to continue defaulting watchlists to public=True
**Reasoning:** I do this because this allows the public to get a better understanding of a user's film taste. This also allows for more community engagement and networking, as a public watchlists allows for people with similar tastes to connect. This can also deepen relationships between friends and followers who can better understand the films that the user tends to like.
**Tradeoff acknowledged:** This feature indeed compromises the privacy of the user who may have intended for the watchlist to be private. 

## Comment 5 — Sort order
**My position:** Watchlists should continue to default to alphabetical.
**Reasoning:** When user's want to find the name of a film that they have been wanting to watch in their watchlist, it is easier for them to find the name if the list is organized alphabetically. 
**Engagement with reviewer's point:** I understand that some users might also prefer seeing the films that they recently added to their list, as a recently added film is more likely to connect to their current tastes in films. However, in situations where the user wants to remember the name of a film that is at the tip of their tongue, it is easier for them to find the film if it is arranged alphabetically. We can always include a toggle near the watchlist header for the user to change the default setting according to their preferences.

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->
