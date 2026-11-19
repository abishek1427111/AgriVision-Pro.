# Packaging audit

- Source archive: `AgriVision-Pro-main.zip`
- Original source files retained, except intentional edits described below.
- Python source files syntax-parsed: 9; parse errors: none
- Included files after documentation: 56
- No dependencies installed, web services contacted, models unpickled, or GUI/web applications executed during packaging. Runtime functionality is **not verified**.
- No Git history exists in the source ZIP; original commit authorship cannot be reconstructed.
- Original README preserved verbatim in `ORIGINAL_README.md`.
- No standalone license was found; public distribution permission should be confirmed.

## Intentional source adjustments
- `backend/create_train_dataset.py`: replaced a teammate-specific absolute Windows path with a configurable local data directory.
- `backend/auth.py`: replaced a fixed JWT secret with an environment-configurable secret and development-only fallback.
- Prediction engine remains in **demo mode** (randomized mock results), unchanged.
