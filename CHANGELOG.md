# Changelog

## 1.3.0 (2026-11-21)

**Much faster simulations.** Stochast now works out large batches of trials with its own formula engine instead of
asking Excel to recalculate for every trial. Measured in Excel for Mac: 10,000 trials of the Project cost example took
0.1 s instead of 18.4 s, 100,000 trials 0.4 s, and the Order quantity optimization (71 candidates of 200 trials each)
0.1 s instead of 51.5 s. Before trusting it, Stochast checks every formula against the
value Excel shows and runs the first trials through Excel as well; models it cannot match exactly are calculated by
Excel as before. The results say which engine was used, and why when it was Excel. Simulate > Run has a switch to
turn it off.

- The engine understands arithmetic, comparisons, text joining, SUM/AVERAGE/MIN/MAX/COUNT/PRODUCT/MEDIAN/SUMPRODUCT,
  IF/IFERROR/IFNA/CHOOSE/AND/OR/NOT, the IS functions, the ROUND family, MOD/ABS/SQRT/EXP/LN/LOG/POWER,
  NPV/PMT/PV/FV, COUNTIF/SUMIF/AVERAGEIF and the IFS family (COUNTIFS, SUMIFS, AVERAGEIFS, MAXIFS, MINIFS),
  VLOOKUP/MATCH/INDEX (exact, or approximate on numbers sorted ascending).
- Optimizations that simulate every candidate check a model against Excel once, not on every candidate.
- Sampling PERT inputs is about 20 times faster, so very large runs start sooner.

## 1.2.0 (2026-11-21)

**New look.** Stochast has its own brand: navy, cream and signal orange, a new logo, and the Space Grotesk typeface
(bundled, so it still works offline). Charts use the brand orange by default; other colours remain under each
chart's Colour setting.

**Easier to start.**
- Simulate and Optimize open on **Get started** while a model is empty: what to do in three steps, and ready-made
  example models created in one click.
- Analyze and Forecast tools can be browsed by topic when the search box is empty.

**Optimize, redesigned.**
- Setup and Results views. Setup is numbered: Goal, Decisions, Limits, Run, and the run button says what is
  missing.
- Results show how much better the answer is than the sheet as it stands, where each best value sits in its
  allowed range, and which limits are holding the answer back.

**Installing and support.**
- The installer adds Stochast to Excel during installation (macOS blocks background programs from Excel's
  folder) and keeps working after a reinstall over the same version.
- `Uninstall Stochast.pkg` removes Stochast without Terminal.
- The pane shows the installed version and a **Help and feedback** link.

## 1.1.0 (2026-11-21)

First version offered as a Mac installer: worksheet functions, a shared runtime, and Office.js bundled so the pane
works with no internet connection.
