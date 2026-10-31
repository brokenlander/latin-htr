# Capture 3: Fondo III, Legati and the Fagnani testament

Worked 23 July 2026. 79 pages from 76 photographs, page ids p633–p708.

| Folder | Pages | Page ids | Content |
|---|---|---|---|
| [`03-04`](../transcriptions/03-04/) | 8 | p633–p637 | 18th-century clergy records, *stato delle anime*, table of legati |
| [`06-46`](../transcriptions/06-46/) | 9 | p638–p646 | 1885–86 Sevesi legato dossier, S. Carlo coadjutorship |
| [`06-49`](../transcriptions/06-49/) | 48 | p647–p694 | 1896 legati recap and cadastral appendix |
| [`testamento-ambrogio-fagnani`](../transcriptions/testamento-ambrogio-fagnani/) | 14 | p695–p708 | Dossier of Fagnani testaments, 1512 and copies |

## What was done
1. **Intake.** Additive manifest. Existing ids frozen.
2. **Crop.** `03-04` with `crop_pages.py`, plus new `scripts/split_spread.py` for two spreads it missed. `06-46` and `06-49` with `crop_single.py`. The testament was not cropped: `scripts/prep_testament.py` enhanced the 200 ppi PDF extracts.
3. **Read.** One Gemini 3.1 Pro read per page. A few dense pages were read again at a higher token cap.
4. **Reconcile and translate.** `03-04` ran end to end first, then stopped for owner review. `06-46` and the dense cadastral pages of `06-49` (p670–p677) were done directly; the 40 prose pages of `06-49` by four parallel agents under a locked rubric, then spot-checked at the pixels.
5. **Testament.** Five Gemini reads per page, because a single read invented formula text at 200 ppi (it gave a false daughter-legacy list and a wrong year on p695). Readings carry their agreement count, then a pixel check. p695 was corrected to 1512.

## Findings
- The testament volume is a dossier of several Fagnani wills and copies, including the 1512 bequest for S. Giacomo with the altarpiece by Giovanni Agostino da Lodi.
- The faint "marginalia" on the testament are show-through.
- Zarè, not Zari, and notary Porro Augusto on `06-46`.

## Status
Complete. The faintest testament pages are at the limit of the 200 ppi scans and need a paleographer. Contests are in [`transcriptions/_REVIEW_QUEUE.txt`](../transcriptions/_REVIEW_QUEUE.txt).
