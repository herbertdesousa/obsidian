Date: 2026-02-03
Tags: [[hardware]]

SSDs are composed with blocks, and those blocks has pages.

There are rules:
1. Only can write a page at the time.
2. Cannot update a page
    It needs to be wiped and then written on another page. The past page is marked as stale.
3. Clear needs be applied on the entire block
    Removing all staled pages and moving the active to other block pages.

Consider a case of a random update:
- Request to update a page.
- But SSD do not overwrite pages, as rule #2 says, so it need to wipe and write on another page.

Stales increase fast with random updates. Garbage collector comes in, but #3 rule must be followed.