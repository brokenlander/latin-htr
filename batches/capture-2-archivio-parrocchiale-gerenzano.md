# Capture 2: Archivio Parrocchiale di Gerenzano

Worked June 2026. 273 pages, about 13 MP, page ids p360–p632. Documents 1438–1892, in 29 fascicoli across fondi VI, VII, VIII, XI and XII.

| Folder | Pages | Page ids | Content |
|---|---|---|---|
| [`06-01`](../transcriptions/06-01/) | 3 | p360–p362 |  |
| [`06-05`](../transcriptions/06-05/) | 7 | p363–p369 |  |
| [`06-06`](../transcriptions/06-06/) | 10 | p370–p379 |  |
| [`06-07`](../transcriptions/06-07/) | 7 | p380–p386 |  |
| [`06-138`](../transcriptions/06-138/) | 7 | p387–p393 |  |
| [`06-142`](../transcriptions/06-142/) | 2 | p394–p395 |  |
| [`06-143`](../transcriptions/06-143/) | 22 | p396–p417 |  |
| [`06-145`](../transcriptions/06-145/) | 5 | p418–p422 |  |
| [`06-184`](../transcriptions/06-184/) | 6 | p423–p428 |  |
| [`06-265`](../transcriptions/06-265/) | 12 | p429–p440 |  |
| [`06-266`](../transcriptions/06-266/) | 4 | p441–p444 |  |
| [`06-269`](../transcriptions/06-269/) | 3 | p445–p447 |  |
| [`06-270`](../transcriptions/06-270/) | 5 | p448–p452 |  |
| [`06-43`](../transcriptions/06-43/) | 21 | p453–p473 |  |
| [`06-67`](../transcriptions/06-67/) | 12 | p474–p485 |  |
| [`07-02`](../transcriptions/07-02/) | 17 | p486–p502 |  |
| [`07-03`](../transcriptions/07-03/) | 9 | p503–p511 |  |
| [`07-154`](../transcriptions/07-154/) | 39 | p512–p550 |  |
| [`08-04`](../transcriptions/08-04/) | 2 | p551–p552 |  |
| [`08-06`](../transcriptions/08-06/) | 3 | p553–p555 |  |
| [`08-13`](../transcriptions/08-13/) | 9 | p556–p564 |  |
| [`08-19`](../transcriptions/08-19/) | 12 | p565–p576 |  |
| [`08-26`](../transcriptions/08-26/) | 10 | p577–p586 |  |
| [`08-29`](../transcriptions/08-29/) | 3 | p587–p589 |  |
| [`08-37`](../transcriptions/08-37/) | 28 | p590–p617 |  |
| [`08-43`](../transcriptions/08-43/) | 7 | p618–p624 |  |
| [`11-04`](../transcriptions/11-04/) | 2 | p625–p626 |  |
| [`11-05`](../transcriptions/11-05/) | 2 | p627–p628 |  |
| [`12-10`](../transcriptions/12-10/) | 4 | p629–p632 |  |

## What was done
1. **Intake.** Additive manifest: existing page ids frozen, new ids from p360. `scripts/build_manifest.py` was made additive.
2. **Crop.** New `scripts/crop_single.py` for single leaves on a dark table: no spread splitting, and it falls back to the full frame when detection looks wrong. 273 of 273 cropped, with a 20-page visual check.
3. **Context.** Reader prompt widened to c. 1430–1850. Shared glossary `registers/_gerenzano_archive.md` copied into every fascicolo context.
4. **Read.** One Gemini 3.1 Pro read per page. 7 dense pages that hit the token cap were read again at a higher cap.
5. **Reconcile, first pass.** Image-grounded reconcile of every page.
6. **Reconcile, second pass.** An independent blind read from the image alone, then disagreements on names, numbers and dates settled at the pixels. Legible 19th-century correspondence and construction accounts stayed single-pass by decision. Where the blind pass showed Gemini had cut a page short, Gemini read that page again.
7. **Translate.** All 273 pages. Latin and early-modern fascicoli were translated directly; the clean 19th-century Italian by parallel agents under one house style. File counts matched 1:1.

## Findings
- 06-06: the testator is Bossi. Both earlier AI passes had turned him into the dominant family name.
- 06-05 p365: "Dottore Collegiato", not "Colliato".
- 06-270 p451 is faded and unreadable.

## Status
Complete. Contests are in [`transcriptions/_REVIEW_QUEUE.txt`](../transcriptions/_REVIEW_QUEUE.txt).
