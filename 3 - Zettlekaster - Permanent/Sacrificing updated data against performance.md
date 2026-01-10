Date: 2025-06-16
Tags: [[database]]

When we got, "I want a row which not be afraid of non-repeatable phenomena" ([[Isolation levels vs read phenomena]]) and the first thing that come into play is **lock**.

Example:
1. Transaction A reads a data
2. Transaction B updates the same data
3. Transaction B commits the data
4. Transaction A reads the same data (it's outdated here, so lock at the first step it's our first think right?)

It's a good approach, but repeatable read could offer better performance in change of outdated data, instead of obtain the updated data after B updates it, at the 4th step same data is delivered as 1th step.

