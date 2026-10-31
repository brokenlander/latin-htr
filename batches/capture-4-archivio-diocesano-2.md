# Capture 4: Archivio Diocesano 2

Worked 30–31 October 2026. 260 pages from 263 photographs received by SwissTransfer, page ids p709–p968. New volumes X 6, X 24, X 25, X 42, X 49 and X 50, plus new leaves for X 4 and X 5, which sit in their existing folders.

| Folder | Pages | Page ids | Content |
|---|---|---|---|
| [`x-24-1610-57`](../transcriptions/x-24-1610-57/) | 71 | p709–p779 | Executorial letters of 1593 on the Gerenzano provostship; printed briefs of 1645 on rochet and cappa; letters 1630–53 |
| [`x-25-1639-58`](../transcriptions/x-25-1639-58/) | 22 | p780–p801 | Short documents 1639–58; a draft of the 1641 decrees; inventories of 1604 |
| [`x-4-1574`](../transcriptions/x-4-1574/) | 13 | p802–p814 | New leaves: copy of a 1564 dowry act; letter of 1571 |
| [`x-42-1620-57`](../transcriptions/x-42-1620-57/) | 71 | p815–p885 | Baptisms, marriages and deaths 1653–58; notes for a visit |
| [`x-49-1747`](../transcriptions/x-49-1747/) | 28 | p886–p913 | Pastoral visit of Card. Giuseppe Pozzobonelli to Gerenzano, 22–23 May 1747 |
| [`x-5-1642-74`](../transcriptions/x-5-1642-74/) | 32 | p914–p945 | New leaves: decrees and visits 1657–74; re-photographs of p343–p354 |
| [`x-50`](../transcriptions/x-50/) | 9 | p946–p954 | 1742 *Status Capellanorum* and visitation decrees |
| [`x-6-1589-1686`](../transcriptions/x-6-1589-1686/) | 14 | p955–p968 | Soldano land exchange 1649–50; agreement of 1653 |

## What was done
1. **Intake.** RAR kept beside the extracted files, integrity tested, 260 photos copied and checksummed. 3 X 5 photos were byte-identical to May files and skipped. Manifest additive: 0 old rows changed.
2. **Crop.** `crop_pages.py` and the `crop_single.py` sheet detector both clipped real text on these tight phone shots of bound volumes, and one page was falsely split. Final crops are `crop_single.py --full`: whole oriented frames, nothing lost. Register contexts tell the reader to ignore facing-page strips.
3. **Reader choice.** Gemini 4 Argon. X 50 was run first at `low` and `high` thinking. `high` kept the scribe's spelling and flagged cut words, so it was used for the rest.
4. **Two reads per page.** 260 of 260 pages hold two Argon reads, the second asking for extra care with names, places and numbers. No errors or truncated reads. X 50's two reads are its `low` and `high` runs. Two reads per page is now the pipeline default.
5. **Reconcile.** Opus 5.5 compared both reads with the image and settled every disagreement at the pixels, under one locked rubric across ten parallel agents. X 50 was done first, in the main session. Both reads were sometimes wrong: p957 is 23 July 1649, and the reads gave 12 July 1619 and 22 July 1649.
6. **Translate.** All 260 pages into modern Italian under the house style. Dates in full, ages in digits, surnames as reconciled.
7. **Checks.** 1:1 file counts. Uncertainty marks compared between transcription and translation. Pixel spot checks on p710, p737, p884 and on the dates of p900, p911 and p957. Two independent readings of the same print (p714–p720, p759–p765) differed on 2 words in about 2,000.

## Repeats
- p713 is the same shot as p712, and p958 the same shot as p957. Each has a one-line pointer file.
- p934 is a re-photograph of p343. p935–p945 are re-photographs of p344–p354: pointer files, listing any differences.
- p759–p765 are a second printed copy of p714–p720, transcribed in full.

## Findings
- X 24: the booklet is issued by Camillo Borghese, Auditor of the Camera, Rome, 14 May 1593, on a brief of Clement VIII of 12 May 1593. Antonio Maria Biumi takes the provostship after Girolamo de Amiralijs dies in December 1592.
- X 24: the 1645 dress dispute runs through three prints: for Gerenzano, 25 July; Carena for Appiano and the curates, against Gerenzano, 20 September; Gerenzano's reply, 2 November. The order is inferred from the dates and the arguments.
- X 42: Prevosto Soldano gives way to Mazuchello between 29 January and 11 February 1654.
- X 49: the "1764" on p898 is a misread page number. This scribe's arched 2 is often read as a 1. The fair copy has its own year slips, kept as written and queued.
- X 25: p784, p785, p792, p793 and p786, in that order, are one draft of the 1641 decrees in X 5.
- X 6: p968 is the notary's rough minute of the 1650 act and disagrees with the formal copy on three points.

## Open
- 354 contested spots are in [`transcriptions/_REVIEW_QUEUE.txt`](../transcriptions/_REVIEW_QUEUE.txt), 185 of them in X 42. Names and dates in X 42 need a person before anyone cites them.
- Unsettled: the years on p788 and p789, p712 `1653[?]`, the letter on p711, formula lines on p812–p813, and line ends lost in the binding on p878.
