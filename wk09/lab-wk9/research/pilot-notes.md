## Pilot Notes Template

**File**: `pilot-notes/P#_notes.md`

```markdown
# Pilot [#] Notes

**Session ID**: P#1
**Date**: [2025-12-05]
**Browser**: Safari
**JS Mode**: [js-on / js-off]
**Assistive Tech**: None
**Input Method**: Touchpad

---

## Task 1: Add Task (complete 2860 worksheet 6)
- **Start**: [HH:MM:SS]
- **End**: [HH:MM:SS]
- **Duration**: [##s]
- **Outcome**: [Success / Partial / Failure]
- **Errors**: [None / "Title is required" / Other]
- **Confidence**: [1-5]
- **Observations**:
  - [e.g., "Pilot clicked 'Add' button immediately; no hesitation"]
  - [e.g., "Validation error triggered; pilot read message and corrected"]

---

## Task 1: Filter Tasks (Show incomplete)
- **Start**: [HH:MM:SS]
- **End**: [HH:MM:SS]
- **Duration**: [##s]
- **Outcome**: [Success / Partial / Failure]
- **Errors**: [None / Other]
- **Confidence**: [1-5]
- **Observations**:
  - [e.g., "Pilot used dropdown; filter applied instantly (HTMX)"]

---

## Task 2: Edit Task (Buy milk → Buy oat milk)
- **Start**: [HH:MM:SS]
- **End**: [HH:MM:SS]
- **Duration**: [##s]
- **Outcome**: [Success / Partial / Failure]
- **Errors**: [None / Focus issue / SR announcement missing / Other]
- **Confidence**: [1-5]
- **Observations**:
  - [e.g., "Pilot tabbed to Edit button; pressed Enter; focus moved to input"]
  - [e.g., "NVDA announced 'Title, edit, Buy milk' correctly"]

---

## Task 4: Delete Task (Buy oat milk)
- **Start**: [HH:MM:SS]
- **End**: [HH:MM:SS]
- **Duration**: [##s]
- **Outcome**: [Success / Partial / Failure]
- **Errors**: [None / Other]
- **Confidence**: [1-5]
- **Observations**:
  - [e.g., "Pilot clicked Delete; task removed via OOB swap (no page reload)"]

---

## Overall Observations
- **Most challenging task**: [T#]
- **Smoothest task**: [T#]
- **Unexpected behaviours**: [List any]
- **Verbatim quotes** (useful for qualitative analysis):
  - "[e.g., 'I didn't realise the edit button was there at first']"
  - "[e.g., 'The error message was really helpful']"

---

## Technical Notes
- **Console errors**: [None / Screenshot saved / Other]
- **Logger entries**: [Verified in metrics.csv / Issues noted below]
- **Network requests**: [HTMX partials / Full-page reloads / Both]
```

---

## Post-Pilot Checklist

- [ ] All 4 tasks completed (or pilot withdrew consent)
- [ ] `data/metrics.csv` updated with all rows
- [ ] `pilot-notes/P#_notes.md` saved with observations
- [ ] Confidence ratings recorded (1–5 for each task)
- [ ] Debrief completed (open questions asked)
- [ ] Browser console screenshot saved (if errors occurred)
- [ ] Thank pilot and confirm data deletion rights

---

**Template source**: Week 9 Lab Pack, COMP2850 (University of Leeds)
**References**: Week 9 Lab 1 (Activity 4), `../../../references/evaluation-metrics-quickref.md`
