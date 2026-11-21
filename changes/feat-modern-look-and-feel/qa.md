# Modernize Mordoc's default look and feel: QA Plan

**Change:** `mordoc-changes-store/changes/feat-modern-look-and-feel`
**Tasks:** [tasks.md](./tasks.md)

## Test Strategy
- Build the Mordoc documentation with the Mordoc of this change and compare screenshots before and after, in light and dark mode.
- The build must pass without errors in English and German.

## Test Coverage
- **AC-006:** The customization pages in English and German list every new setting and the changed defaults, and each example sets values that work.
- **AC-007:** Screenshots show Mordoc's default light grey header on every page and the hero in its own light grey with a hint of warmth in light mode and Mordoc's default in dark mode.
