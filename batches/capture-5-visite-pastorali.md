# Capture 5: Visite pastorali

Worked 13 November 2026. 173 pages from 99 photographs (13 MP, taken 26 February 2019), received by SwissTransfer, photo ids p969–p1067. 74 photos are open-book spreads, split into a left page (`a`) and a right page (`b`).

| Folder | Pages | Page ids | Content |
|---|---|---|---|
| [`visite-pastorali-1596-1687-sommario`](../transcriptions/visite-pastorali-1596-1687-sommario/) | 26 | p969a–p981b | Italian notebook written after 1912, summarising the Latin visit volume |
| [`visite-pastorali-1596-1687-visite`](../transcriptions/visite-pastorali-1596-1687-visite/) | 104 | p982–p1034b | Latin copy of the visits of 1596 (Albergati for Card. Federico Borromeo), 1605 (Borromeo), 1639 (Monti decrees), 1687 (Card. Federico Visconti), certified 28 April 1741 |
| [`visite-pastorali-1734-visita`](../transcriptions/visite-pastorali-1734-visita/) | 21 | p1035–p1045b | Acts and decrees of Repossi's visit, April 1734, certified copy |
| [`visite-pastorali-1899-1912-questionari`](../transcriptions/visite-pastorali-1899-1912-questionari/) | 15 | p1046–p1060 | Printed visit questionnaires filled in for 1899 and 1912 |
| [`visite-pastorali-sec-xviii-decreti`](../transcriptions/visite-pastorali-sec-xviii-decreti/) | 7 | p1061–p1067 | Pozzobonelli's general decrees for the Pieve, May 1747[?]; acts of the April 1767 visit |

## What was done
1. **Intake.** RAR kept beside the extracted files. `unar` reported 28 of 99 files as failing; the official `unrar` tested all 99 as OK, so the archive was sound. 99 photos copied into `raw/Archivio diocesano/Visite pastorali/` in five subfolders, checksummed. Manifest additive: 0 old rows changed.
2. **Split.** Each spread cut at the middle with a 10% overlap on each side (`split_spread.py <pid> 0.5 0.10`), so every page is whole in its own image plus a strip of the facing page; guides were checked on all 74. Single leaves kept whole. Where a gutter sat off-centre, line ends were read from the other half of the same photo.
3. **Two reads per page.** Gemini 4 Argon, 346 reads, no errors. Lines differing between the reads: Latin visits 9%, questionnaires 11%, notebook 15%, 1734 acts 35%, decrees 47%.
4. **Reconcile and translate.** Opus 5.5, nine parallel agents under one rubric, every disagreement settled at the pixels. New this batch: agents could ask Gemini about one zoomed spot (about 20 times in all), as one more vote.
5. **Checks.** 1:1 file counts. Uncertainty marks and years compared between the trees. Pixel checks in the main session on the disputed figures (28 April 1573, 628 communicants, 200 aurei).

## Repeats
p988a/p988b are the same shot as p987a/p987b, and p1059 the same as p1058: pointer files.

## Findings
- The 1596–1687 copyist writes 2 as a hook that drops below the line, and every reader took it for 1. Read as 2, a page of grain debts adds up to its own written total.
- The Italian notebook and the Latin copy check each other. The notebook is right on 28 April 1573 and 628 communicants and wrong on Provost Bossi's age and two months.
- The 1734 acts and the 1747 visit (X 49) disagree on several legati dates; all are queued.
- The S. Giacomo oratory was consecrated with its altar on 28 April 1573.

## Open
93 contested spots are in [`transcriptions/_REVIEW_QUEUE.txt`](../transcriptions/_REVIEW_QUEUE.txt). Unsettled: the Oleario act date on p1036b (1611[?], 13[?]), the 1747[?] year on p1061, the year of the questionnaire on p1052–p1055, five relic names on p1058.
