# Caseflow Worker — approved Stitch design reference

This repository contains the approved Caseflow Worker screen designs exported from Google Stitch.

## Authority

- Existing `.html` + `.png` screen pairs are the canonical visual/interaction references.
- `DESIGN.md` defines the shared visual system and translation rules.
- `CASEFLOW_IMPLEMENTATION_TARGET.md` defines the real production frontend stack.
- `CASEFLOW_BEHAVIOR_CONSTRAINTS.md` records the small set of product-behavior rules that design regeneration must respect.

## Important

This repository is for design/reference purposes. It is **not** the private Caseflow application repository and does not contain production secrets, credentials, real client data, backend implementation, or authoritative release state.

When using this repo with Stitch or another design/code generator:

1. preserve the existing screen visuals with high fidelity;
2. use the guidance files to translate them into React + TypeScript + Vite + application-owned CSS;
3. change the coding implementation, not the Human-approved product design;
4. do not recreate offline Capture / waiting-to-sync behavior — the current Worker MVP is online-only.

## Representative artifacts

- `microsoft_sign_in.*` — sign-in
- `choose_a_program_initial_selection.*` / `switch_program_bottom_sheet.*` — program context
- `caseload_screen_locked_system.*` — caseload
- `coverage_search_*` — deliberate coverage lookup
- `client_overview_jordan_m._locked_system.*` — Client Overview
- `client_recent_*` — Recent
- `client_tasks_*` / `task_detail_*` / `add_task_*` / `edit_task_*` — client task workflows
- `quick_capture_*` — current Capture flows
- `edit_current.*` / `discard_current_changes_confirmation.*` — Current editing
- `privacy_review_*` — privacy review
- `today_screen_locked_system.*` / `tasks_screen_locked_system.*` — approved later primary-navigation states
- `documentation_*` / `to_document_*` / related preparation states — approved later documentation workflow designs

The ordinary `quick_capture_capture_saved.*` confirmation remains valid. Offline `waiting to sync` artifacts are intentionally excluded.
