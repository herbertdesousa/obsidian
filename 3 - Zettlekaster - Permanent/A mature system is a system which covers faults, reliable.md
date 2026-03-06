Date: 2026-02-03
Tags: [[reliability]]

At the beginning of the software, a few possibilities exists, but as the software runs on production, faults/branches/miss-function happens, cover them is be reliable.

Real example:
GCB Background didn't accept minor aged people, to do that, on the query from the data provided about the person onboarding on the app we looked for the 'MINOR' string in the whole JSON. A person has 'MINORA' as their last name, she wasn't a minor, but was handled as one.

To refactor a reliable system be careful, [[Code turns dangerous when many branches shows up]]