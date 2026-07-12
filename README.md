# SF Parking Ticket Leaderboard

A leaderboard of the most-fined license plates in San Francisco, built from
[SFMTA Parking Citations & Fines](https://data.sfgov.org/Transportation/SFMTA-Parking-Citations-Fines/ab4h-6ztd/about_data)
on DataSF (23.9M citations, $2B in fines since 2008).

**Live:** https://raemond.com/sf-parking-ticket-leaderboard/

## Features

- Most-fined plates, this year or all-time, with "load more" paging through all 5.7M ticketed plates
- Run your own plate to see its record and overall rank
- Add friends' plates to build a shareable grudge match (`?plates=A,B,C&range=all`)
- Plates rendered in each state's livery; clean plates sparkle
- Out-of-state division: the top visiting plate per state

## How it works

The site is a single self-contained `index.html` — no build, no dependencies.
Top-20 lists and rank-distribution tables are baked in as a snapshot; everything
else (paging, search, ranks, this-year data) queries the DataSF Socrata API live
from the browser. Exact ranks use a chained SoQL query; an interpolated estimate
from the embedded distribution table shows instantly while the exact count loads.

Fine totals are amounts as issued, not amounts paid. Plates with no recorded
state are excluded from rankings by plate–state combination.
