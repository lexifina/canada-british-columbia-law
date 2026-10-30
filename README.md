# British Columbia: law history in git

The law of British Columbia as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change; picking a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**Metadata only, no law text, because BC Laws, the official online source of British Columbia's statutes, does not allow automated access, and permission to reuse it has not been obtained.** This repository records which bills received Royal Assent and when, with their chapter numbers, and a handful of open facts about the province's legal system. To read a statute, go to [BC Laws](https://www.bclaws.gov.bc.ca). Text will be added if permission is granted.

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `catalogue/` | Catalogue of bills given Royal Assent: title, bill number, assent date and chapter number only | 192 | 192 assent days from 31 March 1992 to 28 May 2026 (1502 bills, 35th to 43rd Parliaments) |
| `legal-system/` | Legal system facts from Wikidata (CC0) | 1 | The facts as Wikidata held them on 18 September 2026 |

## Source

The catalogue's bill numbers, titles, Royal Assent dates and chapter numbers are facts taken from the [Legislative Assembly of British Columbia](https://www.leg.bc.ca/parliamentary-business/bills-and-legislation)'s progress-of-bills record for every session it holds with Royal Assent dates, from the 1st session of the 35th Parliament to the 2nd session of the 43rd Parliament; no text of the bills or of those pages is reproduced. The Wikidata facts are from [Wikidata](https://www.wikidata.org/wiki/Q1973) (CC0).

## Dates

A catalogue entry is dated by the day of Royal Assent the Assembly records, not by commencement (many Acts come into force on other dates), and is credited to a `catalogue-<date>` entry. Commits are at noon, British Columbia time (America/Vancouver, with daylight saving time). The Wikidata facts are dated by the province's inception where Wikidata gives a day, and otherwise by the latest revision of the Wikidata item (18 September 2026; retrieved 30 October 2026).

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; results are in `REPRODUCE.md`.

## What "author" means

The author of a commit is the law (or, for facts, the retrieval) that made the change, with an e-mail address that cannot exist (`<law key>@leg.bc.ca.invalid`). The committer is always Lexifina.

## Limits

Only bills the Assembly's records show with a Royal Assent date are listed (1502); records whose assent date falls outside their own session are left out (see `corpus.json` decisions). Entries do not record commencement, later amendment or repeal. Nothing here is an official record of the statutes.
