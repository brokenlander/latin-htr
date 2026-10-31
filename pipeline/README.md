# pipeline/ — the diocesan-archive HTR pipeline (v2.1)

Reusable tool for transcribing early-modern cursive (Italian + Latin) at scale.
**Full operating guide lives in `../HANDOVER.md`.** This README is the quick map.

## One rule
**Gemini 4 Argon ONLY** from capture 4 on (`config.json`); p001–p708 were read by Gemini 3.1 Pro. Never 2.5, never Flash.
`thinking_level: high` on Argon: on X 50 it kept scribal spelling and flagged cut words that `low` modernised or filled in. The `low` lock in `HANDOVER.md` §2 applied to 3.1 Pro only. Never invent text; the image always wins.

## Flow
```
processed/cropped/<slug>/<pid>.jpg ─► SAMPLE (1 Gemini read, thinking=low) ─► candidates/<pid>.s1.json
                                   ─► AGREE (pure-Python meta, NO API call) ─► meta/<pid>.json
                                   ─► CLAUDE VERIFY (in-session, vs image)  ─► reconciled/<pid>.txt (FINAL)
```
`run` = sample + agree, and **skips any page that already has a final** — it never re-reads (or
re-bills) a finished page. There is **no Gemini reconcile call** in the default path; Claude reconciles, free.

## Files
| file | role |
|---|---|
| `config.json` | pinned model/params (gemini-4-argon, n_samples=2); benched-kraken gate |
| `gemini_htr.py` | `sample`/`agree`/`run`/`status` orchestrator; quota autostop; structured JSON + provenance |
| `validate.py` | structural lints over `reconciled/` → flag re-review (advisory, exits 0) |
| `_run_v2.sh` | detached sampler launcher (the caller runs it under `setsid`; the watchdog does) |
| `VERIFY_LOOP.md` | the hourly-cron per-wake playbook |

The benched local-engine stubs and all the old fine-tune/ensemble tooling now live in `../scripts/_archive/`.

## Run
```bash
PYTHONPATH=scripts .venv/bin/python3 pipeline/gemini_htr.py run x-4-1574     # a register (skips done pages)
PYTHONPATH=scripts .venv/bin/python3 pipeline/gemini_htr.py run p209 --hard  # one page, n_samples=2 (n_samples_hard)
PYTHONPATH=scripts .venv/bin/python3 pipeline/gemini_htr.py status           # progress per register
```
Then **Claude verifies**: read the image + `candidates/<pid>.s1.json` + `registers/<slug>/context.md`
→ fix names/numbers against the pixels, confirm blanks → write `reconciled/<pid>.txt`. Flag dubious
pages to `processed/transcriptions/_REVIEW_QUEUE.txt`.

## kraken / McCATMuS — BENCHED
`config.json kraken.enabled=false`. Tested 2026-06: ~40–60% CER on the 2 MP cursive backlog (names
mangled — "Alessandro Franco" → "A'estandre bra ner"). Not part of the pipeline; the gate stubs are
archived. Revive only for 12 MP material (Turate, already done).
