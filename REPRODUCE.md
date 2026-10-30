# How this repository was made (British Columbia)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Legislative Assembly of British Columbia: progress of bills, per session | <https://www.leg.bc.ca/parliamentary-business/bills-and-legislation> | 2026-10-30 | Facts only (bill number, title, Royal Assent date, chapter number); no text of the bills or of the Assembly's pages is reproduced |
| Wikidata | <https://www.wikidata.org/wiki/Q1973> | 2026-10-30 | CC0 1.0 |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `catalogue` | Catalogue of British Columbia bills given Royal Assent (title, bill number, assent date and chapter number only) | 192 | 1992-03-31 to 2026-05-28 |
| `legal-system` | British Columbia: legal system facts (Wikidata) | 1 | 2026-09-18 to 2026-09-18 |

The build made 193 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 191 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 193 laws in the record.
- 384 tags.

## Dates

Each commit is dated at noon (America/Vancouver) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Catalogue entries are dated by the day of Royal Assent recorded by the Legislative Assembly; they describe bills and are not law text. https://www.leg.bc.ca/parliamentary-business/bills-and-legislation

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `1e7921692ccaf16822ee7ccd21c1bb000ab9723f6125d5c6883bcea34285e4b1` (686935 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a97ff7ea62c3c7595c5668a297d533da0b74373c`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

193 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- No law text is published. BC Laws, the official online source of British Columbia's statutes, does not allow automated access to its pages, and permission to use it has not been obtained, so nothing was taken from it.
- The catalogue holds facts only: bill number and type, the title, the Royal Assent date and the S.B.C. chapter number, as the Legislative Assembly's progress-of-bills record for each session gives them. The Assembly's copyright notice reserves its material for personal use; titles, numbers and dates are facts, and no text of the bills or of the Assembly's pages is reproduced.
- Coverage: every bill with a Royal Assent date in the Assembly's records, from 1992-03-31 to 2026-05-28: 1502 bills on 192 assent days; 1502 with a chapter number.
- 47 records whose Royal Assent date lies outside the session they belong to (before it opened, or after the next session opened) were left out as evident data-entry errors, rather than guessed: bill-36-2-g055 (1997-02-10), bill-36-3-g101 (2000-07-15), bill-36-4-g031 (2001-07-06), bill-36-4-g033 (2001-09-17), bill-36-4-g034 (2001-12-08), bill-37-2-g021 (2002-08-27), bill-37-2-g022 (2002-08-27), bill-37-2-g027 (2001-01-27), bill-37-2-g028 (2001-01-28), bill-37-2-g029 (2001-01-28), bill-37-3-g033 (2003-04-30), bill-37-4-g047 (2004-05-29), bill-37-4-g098 (2004-12-02), bill-37-4-g099 (2004-12-16), bill-37-5-g048 (2005-05-20), bill-37-5-g049 (2005-05-20), bill-38-1-g018 (2006-11-24), bill-38-2-g035 (2007-05-18), bill-38-3-g038 (2008-05-31), bill-38-4-g006 (2009-03-31), bill-38-4-g044 (2009-05-29), bill-39-1-g022 (2010-11-26), bill-39-2-g022 (2011-06-03), bill-39-3-g016 (2012-06-02), bill-39-4-g002 (2013-11-14), bill-39-4-g004 (2011-03-15), bill-39-4-g008 (2011-03-15), bill-39-4-g014 (2011-05-31), bill-39-4-g015 (2011-03-29), bill-39-4-g018 (2011-03-29), bill-39-4-g020 (2011-03-29), bill-39-4-g055 (2013-05-31), bill-39-4-g056 (2013-05-31), bill-40-1-g003 (2014-07-25), bill-40-2-g026 (2015-05-29), bill-40-4-g028 (2016-05-28), bill-40-5-g026 (2017-05-19), bill-41-2-g006 (2018-11-30), bill-41-2-g017 (2018-11-30), bill-41-3-g035 (2019-05-31), bill-41-4-g034 (2020-05-30), bill-41-5-g025 (2021-08-14), bill-42-1-g004 (2020-03-25), bill-42-2-g016 (2022-06-17), bill-42-3-g025 (2023-06-02), bill-42-4-g030 (2024-05-11), bill-42-4-g031 (2024-11-08).
- Wikidata facts (CC0) form the "legal-system" act, dated by the province's inception where Wikidata gives a day, otherwise by the latest revision of the Wikidata item before retrieval (2026-09-18; retrieved 2026-10-30), so no commit lies after the build.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code with Claude Opus 5.5 wrote Lexifina's code and chose the sources; it did not write or alter any legal text. The code is deterministic and runs no model.
