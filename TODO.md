# TODO

- [ ] Clean up the code in this repo
- [ ] Clean up the `Data Compilation` folder and get rid of duplicates
- [ ] Run steps 2-5 in `Raw data files\OSAR\Organizosar.md` for the 26 crosses with new files
- [ ] On that first run, update every cross in `thesis_stats` and `Bootstrapped stats`, not just the new ones. 11 crosses with an out-of-date test N aren't among the 26:
  - `MB027B x Chrimson2`, `MB077B x ACR`, `MB112C x ACR`, `MB434B x Chrimson2`, `SS01188 x ACR`, `SS52050 x Chrimson2`
  - `SS67662 x Chrimson2`, `SS77442 x Chrimson2`, `SS80974 x Chrimson2`, `SS81353 x ACR`, `SS95118 x Chrimson2`
- [ ] Sort out responder/+ controls before re-running the stats
  - Add `w1118 x ACR` or `w1118 x Chrimson2` logs to the 6 new cross folders: `MB057B x ACR`, `MB057B x Chrimson2`, `SS01127 x ACR`, `SS01127 x Chrimson2`, `SS01388 x ACR`, `SS67727 x ACR`
  - Decide what to do about the range across crosses (25 to 333 `w1118 x ACR` flies), since it can shift effect sizes
- [ ] Choose an `osar` version before re-running: `20250930version` has 0.23.7, but notebook 3's saved run printed 0.23.9. That env also has no `nbconvert`, so it can't run notebooks from the command line
- [ ] Check that all crosses have all 9 metrics in `thesis_stats` after the re-run. 15 have only 4 now
