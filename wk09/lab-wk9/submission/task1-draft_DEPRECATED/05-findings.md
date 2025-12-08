# Task 1: Findings & Evidence Chains

**Purpose**: Synthesize pilot data into actionable findings with evidence chains linking raw data to backlog items.

---

## Executive Summary

**Pilots conducted**: [3] participants
**Date range**: [YYYY-MM-DD to YYYY-MM-DD]
**Variants tested**: Standard (HTMX), keyboard-only, no-JS, [screen reader]

**Key findings**:
1. Keyboard users cannot use edit/delete controls which led to failure and timeout (WCAG 2.1.1 Keyboard - A)
2. Confirmation message poorly visible and not always seen
3. Using safari with js off does not work at all and leads to failure of all tasks, meaning non-js users on safari cannot complete any core task

**Recommended fixes for Week 10**: [List 2-3 priority fixes] 
1. Increase visibility of confimration messages, maybe a short on screen pop up
2. Fix keyboard accessibility for edit/delete features 

---

## 1. Quantitative Results

### 1.1 Completion Rates

| Task | Code | Completion | Notes |
|------|------|-----------|-------|
| [Filter tasks] | T1 | 2/3 ([66%]) | Safari no js failed, keyboard and touchpad succeeded |
| [Edit task] | T2 | 1/3 ([33%]) | Keyboard only doesn't work and safari no-js broken |
| [Add task] | T3 | 2/3 ([66%]) | safari no-js also doesn't work |
| [Delete task] | T4 | 1/ 3 ([33%]) | Only worked with trackpad/mouse |

**Analysis**: [Interpret completion rates. Which tasks had low completion? Why?]
- T2 and T4 had the worst completion rates with only 33 percent due to accessibility issued 
- Keyboard only could not navigate to Edit/Delete at all 
- On safari, with js turned off, none of the tasks could be completed successfully, all of the actions let to downloading an empty file instead of completing the task.
**Evidence**:
- `04-results.csv` lines [4-5]: [P1_5w2q] with `step=fail`
- `04-results.csv` lines [10-13]: [P3_0k2m] with `step=fail` or incomplete task sequences
- `06-evidence/pilot-notes-template.md` line [Y]: Edit/delete tasks describing repeated use of Tab
- `06-evidence/pilot-notes-template.md` line [Y]: All tasks time out and download instead of being completed 
---

### 1.2 Task Completion Times

**Median times** (success only):

| Task | Code | Median (ms) | Median (s) | MAD (ms) | Range | n |
|------|------|------------|------------|---------|-------|---|
| Filter | T1 | 21500 | 21.5s | 10500ms | 11s–32s | 2 |
| Edit | T2 | 8000s | 8s | 0 | 8s–8s | 1 |
| Add | T3 | 26500 | 26.5s | 12500s | 14s–39s | 2 |
| Delete | T4 | 6000 | 6s | 0 | 6-6 | 1 |

**Analysis**: [Interpret times. Which tasks were slow? Why? Any outliers?]

- Add (T3) and Filter (T1) are faster for a mouse user (P2), but slow for keyboard-only (P1), which inflates the medians and MAD.
- Edit (T2) and Delete (T4) appear fast (8s and 6s), but that’s because the only successful attempts come from the confident mouse user.

**Evidence**:
- `04-results.csv`: Filtered `step=success`, calculated median and MAD
- `06-evidence/pilot-notes-templates.md/`: Pilot 1 shows hesitation and confusion ("This is quite confusing to navigate through")
- `06-evidence/pilot-notes-templates.md/`: Pilot 2 shows quick navigation with minor error with mis-click on Edit
---

### 1.3 Error Rates

| Task | Code | Validation Errors | Total Attempts | Error Rate | Notes |
|------|------|------------------|----------------|-----------|-------|
| [Task name] | T1 | [n] | [n] | [%] | [Error type] |
| [Task name] | T2 | [n] | [n] | [%] | [Error type] |
| [Task name] | T3 | [n] | [n] | [%] | [Error type] |
| [Task name] | T4 | [n] | [n] | [%] | [Error type] |

**Analysis**: [Interpret error rates. Which errors were common? Accessibility implications?]

**Evidence**:
- `04-results.csv`: Filtered `step=validation_error`, counted occurrences
- `06-evidence/pilot-notes/`: [Quotes about error messages, confusion]

---

### 1.4 JS-On vs JS-Off Comparison

**Task [X] comparison** (most impacted by JS):

| Variant | Median Time (ms) | n | Notes |
|---------|-----------------|---|-------|
| JS-on (HTMX) | 26500 | 2 | Works well but slower with keyboard |
| JS-off (Safari) | -- | 0 | No tasks could be completed, all led to a download of an empty file |
| **Difference** | [Z]× slower | | [Expected due to PRG pattern] |

**Analysis**: [Evaluate no-JS parity. Is slowdown acceptable? Any functional differences?]

- The JS-off variant is non-functional in Safari for this setup.
- For JS-on, both keyboard-only and mouse users can eventually add and filter tasks, although keyboard users are significantly slower and more frustrated.
- For JS-off, all tasks fail (100% failure rate across all four tasks), so no median times can be computed.

**Evidence**:
- `04-results.csv`: Filtered `js_mode=off` for session [P3_0k2m]
- `06-evidence/pilot-notes-template.md`: Describes empty files being downloaded for all tasks

---

## 2. Qualitative Findings

### 2.1 Accessibility Issues

**Finding A1**: Keyboard users cannot reach Edit/Delete

**Severity**: High (WCAG [2.1.1] violation)

**Affected users**: Keyboard only users

**Evidence chain**:
1. **Raw data**: `04-results.csv` line [X]: Session [P2_xxxx], task [T2], `step=validation_error`
2. **Observation**: `06-evidence/pilot-notes/P2-notes.md` line [Y]: "[Quote: 'I didn't hear any error message']"
3. **Screenshot**: None
4. **WCAG reference**: 2.1.1 Keyboard (should be fully functional with solely keyboard)

**Impact**:
- **Inclusion**: Keyboard only users cannon complete edit and delete operations
- **Frequency**: 0% of attempts on triggered validation errors
- **Criticality**: Excludes keyboard-only users

**Proposed mitigation**: Ensure all tasks are reachable by pushing tab, maybe add specific keyboard shortcuts to directly navigate to a task.

**Backlog item**: [wk9-01] (see `backlog/backlog.csv`)

---

**Finding A2**:  Status and confirmation messages very small in the corner 

**Severity**: High for low-vision users 

**Affected users**: Low-vision users

**Evidence chain**:
1. **Raw data**: `04-results.csv` line [X]: Session [P2_xxxx], task [T2], `step=success`
2. **Observation**: `06-evidence/pilot-notes/P2-notes.md` line [Y]: "Pilot asked how they know if the task has been added because they didnt see the message at the top"
3. **Screenshot**: None
4. **WCAG reference**: 2.1.1 Keyboard (should be fully functional with solely keyboard)

**Impact**:
- **Inclusion**: Keyboard only users cannon complete edit and delete operations
- **Frequency**: 0% of attempts on triggered validation errors
- **Criticality**: Excludes keyboard-only users

**Proposed mitigation**: Move where message shows up/ make it bigger/ make it a temporary on screen pop up

**Backlog item**: [wk9-02] (see `backlog/backlog.csv`)
---
**Finding A3**:  No-js doesn't work in safari

**Severity**: High(prevents all tasks in that environment)

**Affected users**: Users with JS disabled on safari

**Evidence chain**:
1. **Raw data**: `04-results.csv` line [X]: Session [P2_xxxx], task [T2], `step=validation_error`
2. **Observation**: `06-evidence/pilot-notes/P2-notes.md` line [Y]: "[Quote: 'I didn't hear any error message']"
3. **Screenshot**: None
4. **WCAG reference**: 2.1.1 Keyboard (should be fully functional with solely keyboard)

**Impact**:
- **Inclusion**: Keyboard only users cannon complete edit and delete operations
- **Frequency**: 0% of attempts on triggered validation errors
- **Criticality**: Excludes keyboard-only users

**Proposed mitigation**: Ensure all tasks are reachable by pushing tab, maybe add specific keyboard shortcuts to directly navigate to a task.

**Backlog item**: [wk9-01] (see `backlog/backlog.csv`)

### 2.2 Usability Issues

**Finding U1**: Filter results and list location create confusion

**Severity**: Medium (UX issue, not WCAG violation)

**Evidence chain**:
1. **Observation**: `06-evidence/pilot-notes/P1-notes.md` line [X]: "[Quote: 'Is it filtering automatically? I expected a button.']"
2. **Observation**: `06-evidence/pilot-notes/P4-notes.md` line [Y]: "[Quote: 'I typed and then waited... nothing happened']"
3. **Screenshot**: `06-evidence/screenshots/filter-expectation.png`

**Impact**:
- **Inclusion**: Low (all users can eventually figure out)
- **Frequency**: [X] / [n] participants hesitated
- **Criticality**: Delays task but doesn't block

**Proposed mitigation**: Provide helper text("Scroll down to see filtered tasks")

**Backlog item**: [wk9-02] (see `backlog/backlog.csv`)

---

**Finding U2**: [Next usability issue]

[Repeat structure]

---

### 2.3 Positive Observations

**What worked well** (keep in redesign):

1. Standard mouse/trackpad interactions are smooth for all actions with js on.
    - Evidence: pilot-notes/P2 shows Add (14s), Filter (11s), Edit (8s), Delete (6s) all completed with high confidence.

2. Users understand easily with no explanation which buttons they need to complete which tasks.
    - Evidence: pilot-notes, P2 could successfully complete tasks without timeout and needed to help or explanation

3. [Positive observation 3, e.g., "No-JS parity maintained—all tasks completable"]
   - Evidence: `04-results.csv`: Session [P3_xxxx] completed all tasks with `js_mode=off`

---

## 3. Prioritization for Week 10

**Prioritization formula**: `(Impact + Inclusion) – Effort` (all 1–5 scale)

| ID | Issue | Impact | Inclusion | Effort | Score | Priority | Week 10? |
|----|-------|--------|-----------|--------|-------|----------|----------|
| wk9-01 | Keyboard only cant use edit/delete | 5 | 5 | 4 | 6 | High | ✅ |
| wk9-02 | Status/confirmation messages too small | 4 | 4 | 2 | 6 | High | ✅ |
| wk9-03 | Safari no-JS doesn't work | 5 | 3 | 4 | 4 | High | ⏸ ❌ |
| wk9-04 | Filter feedback unclear results off-screen | 3 | 3 | 2 | 4 | Medium | ❌ |

**Rationale**:
- **Impact**: Severity of problem (5 = blocks task, 1 = minor annoyance)
- **Inclusion**: Affects marginalized users (5 = SR/keyboard only, 1 = all users equally)
- **Effort**: Development + testing time (5 = >4 hours, 1 = <30 min)

- wk9-02 (status messages) and wk9-04 (filter feedback) are high impact, moderate inclusion, low effort → ideal for Week 10.
- wk9-01 (keyboard Edit/Delete) is critical for inclusion, but may be more complex (tab order, component refactor). Worth starting but may not be fully solved in one week.
- wk9-03 (Safari no-JS bug) is high impact but more about environment configuration; best documented clearly and postponed beyond Week 10.

**Week 10 focus**: [wk9-01], [wk9-02] — highest inclusion impact + feasible effort

- Implement clearer, more visible confirmation/status messages (wk9-02).
- Add filter result feedback and/or auto-scroll/focus behavior (wk9-04).
- Begin addressing keyboard focus/navigation issues for Edit/Delete, at least improving focus styles and checking Tab order (wk9-01 – partial progress).

---

## 4. Evidence Chains (Summary)

**Purpose**: Ensure every claim is traceable to data (no assumptions).

**Format**: `Raw data → Observation → Interpretation → Backlog item → Proposed fix`

### Example: Finding A1 (Validation errors not announced)

```
04-results.csv line 127: P2_4d8e,T2_edit,validation_error,blank_title,0,400,on
    ↓
06-evidence/pilot-notes/P2-notes.md line 12: "P2: 'I didn't hear any error message'"
    ↓
Interpretation: SR users cannot detect validation errors (WCAG 4.1.3)
    ↓
backlog/backlog.csv wk9-01: "Add role=alert to error messages"
    ↓
Week 10 fix: Implement aria-live="assertive" + aria-describedby + focus management
```

**All findings must follow this structure** for credibility and transparency.

---

## 5. Limitations & Future Work

### 5.1 Study Limitations

1. **Sample size**: 3 participants (small but typical for formative evaluation—Nielsen's 5-user rule)
2. **Diversity**: Limited to peers all of similar age, no screen readers included 
3. **Context**: Lab setting (not real-world usage—may miss long-term patterns)
4. **Tasks**: Artificial scenarios (real tasks might reveal different issues)

### 5.2 Data Quality Issues

- Safari JS-off (P3) produced downloads instead of rendered pages, resulting in 100% task failure. These were retained as legitimate system-level failures.
- No server-side validation_error events occurred, so conclusions about form validation are limited.

### 5.3 Future Evaluations

**For Week 10 re-pilots** (post-redesign):
- Focus on fixed issues (A1, A2) to verify improvement
- Use same tasks + protocol for comparability
- Target [n=2] participants (sufficient for regression testing)

**For professional practice**:
- Recruit diverse participants (age, ability, tech literacy)
- Extend to real-world tasks (not lab scenarios)
- Longitudinal studies (usage over weeks/months)

---

## 6. Conclusion

**Summary of key findings**:
1. Keyboard-only access to Edit/Delete is currently broken, making core tasks impossible for some users.
2. Status/confirmation messages are poorly placed and styled, leaving users unsure whether tasks have been added/edited/deleted.
3. The Safari + no-JS combination is not robust, blocking all tasks due to file-download behaviour rather than page updates.


**Recommended actions**:
- Week 10 Lab 1: Detailed analysis with `Analyse.kt`, prioritise fixes
- Week 10 Lab 2: Implement [2-3] priority fixes, re-verify with regression testing + re-pilots
- Week 11: Present evidence-led redesign in studio critique

**Learning Outcomes addressed**:
- **LO6**: Iterative design (pilot → findings → redesign)
- **LO8**: Evaluation execution (protocol, metrics, analysis)
- **LO11**: Collaboration (peer pilots, observer role)
- **LO12**: Professionalism (consent, evidence chains, honest reporting)

---

## Appendices

### Appendix A: WCAG 2.2 References

- **3.2.1 On Focus (A)**: Focus changes must not trigger unexpected context changes
- **3.3.1 Error Identification (A)**: Errors must be identified and described in text
- **3.3.3 Error Suggestion (AA)**: Error messages should suggest corrections
- **4.1.3 Status Messages (AA)**: Status changes must be announced to assistive tech

See [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/) for full criteria.

### Appendix B: Definitions

- **MAD** (Median Absolute Deviation): Robust measure of variability (less affected by outliers than standard deviation)
- **PRG** (POST-Redirect-GET): Pattern to prevent form resubmission on browser refresh
- **SR** (Screen Reader): Assistive tech that reads screen content aloud (e.g., NVDA, JAWS, VoiceOver)
- **HTMX**: Library for AJAX updates via HTML attributes (progressive enhancement)

See [Glossary](../../references/glossary.md) for full definitions.

---

**Author**: [Fareedah Fashola]
**Date**: [2025-12-08]
**Version**: Draft for Task 1 submission
**Next review**: Week 11 (finalize for portfolio)
