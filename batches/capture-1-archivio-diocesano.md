# Capture 1: Archivio Diocesano

Worked May–June 2026. 383 pages from 359 photographs, page ids p001–p359. Open-book spreads are split into `a` and `b` pages.

| Folder | Pages | Page ids | Content |
|---|---|---|---|
| [`turate`](../transcriptions/turate/) | 46 | p001–p024b | *Stato delle anime* of Turate, dated 1579, Italian, 12 MP scans |
| [`x-4-1574`](../transcriptions/x-4-1574/) | 109 | p153–p261 | 1574 visitation and benefice volume, documents 1566–1662, Italian and Latin |
| [`x-18-1570-79`](../transcriptions/x-18-1570-79/) | 97 | p025–p119 | Visitations 1570–79, bound-in 1604 and 1691 censuses |
| [`x-44-1583`](../transcriptions/x-44-1583/) | 65 | p262–p326 | 1583 Taurino visitation, Latin |
| [`x-20-1583`](../transcriptions/x-20-1583/) | 33 | p120–p152 | 1583 visitation decrees, Latin and Italian |
| [`x-5-1642-74`](../transcriptions/x-5-1642-74/) | 28 | p327–p354 | Episcopal and synodal decrees, 1662 procuration, Latin |
| [`x-51`](../transcriptions/x-51/) | 5 | p355–p359 | Undated attestation on the S. Rosario chapel, Italian |

## What was done
1. **Intake.** One RAR from Google Drive, extracted with `unar`. Manifest and page index built. EXIF rotation applied: 135 of 359 photos were stored sideways.
2. **Crop.** `scripts/crop_pages.py`: orientation, spread split, crop to the text block.
3. **First attempt, abandoned.** A local ensemble of HTR engines (McCATMuS and TRIDIS on Kraken, with fine-tuning) scored about 40–60% character error on the 2 MP photos and mangled proper names. It was benched. Tooling is in `scripts/_archive/`.
4. **Read.** One Gemini 3.1 Pro read per page, `thinking_level` low, with a glossary per register.
5. **Reconcile.** An LLM session compared each read with the page image, fixed names and numbers with cross-page knowledge and marked what stayed uncertain. 194 pages were native reads. 189 pages were re-read and reconciled with their earlier version as a second vote. Turate was a three-way check of the Gemini read, the earlier McCATMuS-based text and the 12 MP image.
6. **Translate.** All 383 pages into modern Italian, including the Turate combined file. The Turate census year was corrected from 1679 to 1579.

## Status
Complete. Spots for a paleographer are in [`transcriptions/_REVIEW_QUEUE.txt`](../transcriptions/_REVIEW_QUEUE.txt).

Known errors: re-photographs taken for capture 4 show p344–p354 hold 21 wrong words and 8 omissions. The files are unchanged. The list is in the review queue under OLDER PAGES. Most pages of this capture had a single read and have had no independent check.
