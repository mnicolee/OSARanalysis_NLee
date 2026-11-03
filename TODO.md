# TODO

> [!WARNING]
> **Do NOT open, list or read any files in the Dropbox folders (CSVs, Excel files, and especially videos).** Opening them makes Dropbox download them to this computer, and there isn't space for that. Only touch a Dropbox file when it's named explicitly and you're asked to.

- [ ] Clean up the code in this repo
- [ ] Clean up the `Data Compilation` folder and get rid of duplicates
- [x] Run steps 2-5 in `Raw data files\OSAR\Organizosar.md` for the 26 crosses with new files (done 2026-11-03, up to `20260824`)
- [ ] On that first run, update every cross in `3. summary_table` and `2. Bootstrapped_stats`, not just the new ones. 11 crosses with an out-of-date test N aren't among the 26:
  - `MB027B x Chrimson2`, `MB077B x ACR`, `MB112C x ACR`, `MB434B x Chrimson2`, `SS01188 x ACR`, `SS52050 x Chrimson2`
  - `SS67662 x Chrimson2`, `SS77442 x Chrimson2`, `SS80974 x Chrimson2`, `SS81353 x ACR`, `SS95118 x Chrimson2`
- [ ] Sort out responder/+ controls before re-running the stats
  - The `w1118 x ACR` and `w1118 x Chrimson2` runs were last done on **2026-03-27** (8 ACR logs, 12 Chrimson2 logs, in `DATA\OSAR\WT\WT_Green` / `WT_Red`). Holding this dataset for now; don't copy them into any more crosses
  - **If a future run comes across `w1118 x ACR` or `w1118 x Chrimson2` logs, STOP and ask me what to do**
  - Add `w1118 x ACR` or `w1118 x Chrimson2` logs to the 6 new cross folders: `MB057B x ACR`, `MB057B x Chrimson2`, `SS01127 x ACR`, `SS01127 x Chrimson2`, `SS01388 x ACR`, `SS67727 x ACR`
  - ~~Decide what to do about the range across crosses (25 to 333 `w1118 x ACR` flies)~~ Decided 2026-11-03: leave as is. Colours and genotypes in every countlog folder were checked and are correct
- [x] Choose an `osar` version before re-running: `20250930version` now has 0.23.9 (matches notebook 3's saved run) and `nbconvert` 7.16.6, so notebooks can run from the command line
- [ ] Revisit the processing steps in `Raw data files\OSAR\Organizosar.md` (Dropbox). Last processed date is now `20260824`. The next run processes every date folder after that, up to the newest, then sets the date to the last folder processed
- [ ] Check that all crosses have all 9 metrics in `3. summary_table` after the re-run. 15 have only 4 now

## Climbing (one-off)

- [ ] Later: make a combined OSAR + climbing sample size workbook (the old `Compilation of sample sizes` file is gone)

- [ ] First climbing copy (step 1 of `Organiziclimb.md`): set `last_processed = "20260428"` once, so `20260513` (never copied) is picked up. Files already in `DATA` are skipped by name
- [ ] Typos in `Raw data files\Climbing` folder names, for that first copy: `SS81308` (20260608) and `SS1308` (20260622) should be `SS01308`. Add them to `name_fixes` in `1. Renamingfiles.ipynb` cell 3 after checking
- [ ] Ignored for now: every raw `w1118 x <driver> [G|R]` climbing folder from `20260429` on is empty (0 files). Some 2026-06 w1118 logs sit loose in `DATA\Climbing\Climbing_<resp>\WT\` instead of a `w1118 x <driver>` subfolder
- [ ] Some `DATA\Climbing\Climbing_<resp>\WT\` folders have both `w1118 x <driver>` and `w1118 x <driver> [G]`/`[R]` versions (some with a double space). The copy cell uses the plain name
- [ ] Later: `Compilation with delta\2025climbingtoosarcomp` is left out of `Organiziclimb.md` for now. Nothing writes it any more (log2 speed and log2 bout speed moved into `1. Delta_g output` in Oct 2025), but `Asovalencevsme` and some CLOSAR notebooks still read it

- [ ] Once, for every cross in `Climbing_New`: run only the sample size cell (cell 3) of `DrosoClimb\3. Multi-file processing.ipynb`, with `lst` set to all drivers, once for ACR and once for Chrimson2. It writes `Compilation with delta\samplesizes\<cross>_samplesize.csv` (Test, `w1118 x <driver>`, `w1118 x <responder>`) and `Totalosarclimbing\Climbing sample sizes_<date>.xlsx`. This downloads the w1118 ClimbLogs (~250 MB) and `Climbing_New` (~256 MB)
  - If a cross stops on the `assert` line, its `Climbing_New` file doesn't match `DATA` any more: re-run notebook 2 for it, then this cell
- [ ] Do this together with the first full climbing run of the new data (`Raw data files\Climbing\Organiziclimb.md`). After that, sample sizes only update for the crosses in `lst`
