# Task 1: Evaluation Tasks

**Purpose**: Define the specific tasks participants will perform during usability testing.

---

## Task Design Principles

- **Realistic**: Tasks should reflect real-world use cases
- **Specific**: Clear success criteria (not open-ended)
- **Independent**: Tasks don't depend on each other
- **Measurable**: Can capture time, errors, completion
- **Inclusive**: Consider keyboard-only, screen reader, no-JS access

---

## Task 1 (T1): Add task

### Scenario
> You need to add a new task for your deadline coming up 

### Instructions (read to participant)
> "Add a task with title 'complete 2860 worksheet 7' to your task list"

### Success Criteria
- [ ] Task appears in list 
- [ ] Title matches exactly 'complete 2860 worksheet 7'
- [ ] Confirmation message is shown
- [ ] No validation errors occured
 


### Expected Duration
**Target**: < 20 seconds

### Known Risks
- "Blank submission triggers validation error"
- "No confirmation message displayed"

---

## Task 2 (T2): [Filter tasks]

### Scenario
> You have a lot of tasks and want to only see the ones in one module

### Instructions (read to participant)
> "Use the filter to show only tasks containing the word '2860'."

### Success Criteria
- [ ] Filter input contains "2860"
- [ ] Task list shows only matching tasks

### Expected Duration
**Target**: < 20 seconds

### Known Risks
- "Auto-filter not obvious (participant expects button)"
- Cant tell its been filtered due to lack of other inputs or tasks in the list 
- "Status announcement missing for no-JS mode"
---

## Task 3 (T3): Edit Task

### Scenario
> "You notice a typo in one of your tasks and need to correct it."

### Instructions (read to participant)
> "Edit the task titled 'complete 2860 worksheet 7' and change it to 'complete 2870 worksheet 7'"

### Success Criteria
- [ ] Edit mode activated (form appears)
- [ ] Task title updated successfully
- [ ] Changes reflected in task list

### Expected Duration
**Target**: < 30 seconds

### Known Risks
- [Potential issue 1, e.g., "Inline edit form not keyboard-accessible"]
- [Potential issue 2, e.g., "Cancel button doesn't restore original value"]

---

## Task 4 (T4): Delete Task

### Scenario
> "You've completed a task and want to remove it from your list."

### Instructions (read to participant)
"Delete the task titled 'complete 2870 worksheet 7'."

### Success Criteria
- [ ] Confirmation dialog appears 
- [ ] Task is removed from the list
- [ ] Deletion confirmed visually

### Expected Duration
**Target**: < 20 seconds

### Known Risks
- No confirmation—accidental deletion possible"
- "Delete button not keyboard-accessible"

---

## Task Order Rationale

| Task | Complexity | Rationale |
|------|-----------|-----------|
| **T1** | Low | Warm-up task, builds confidence |
| **T2** | Medium | Tests search/filter interaction |
| **T3** | Medium-High | Tests inline editing (more complex interaction) |
| **T4** | Low-Medium | Tests destructive action (confirmation flow) |

---

## Accessibility Considerations

### Keyboard-Only Pilot
- All tasks must be completable via Tab, Enter, Spacebar, Escape
- Focus must be visible at all times
- Tab order must be logical
- No keyboard traps

### Screen Reader Pilot
- All interactive elements must have accessible names
- Status messages must be announced (`aria-live`, `role="status"`)
- Errors must be associated with fields (`aria-describedby`)
- Dynamic content changes must be announced

### No-JS Pilot
- All tasks must work without JavaScript (full page refreshes)
- Form submission must use standard POST/Redirect/GET
- Validation errors must be displayed after redirect
- Navigation must use standard links

---

## Metrics Collected Per Task

| Metric | Unit | How Measured |
|--------|------|--------------|
| **Time-on-task** | Seconds | Stopwatch (start = first action, end = success or abandon) |
| **Completion rate** | % | success / total attempts |
| **Error rate** | Count | Validation errors, incorrect submissions, wrong buttons clicked |
| **Confidence** | 1-5 scale | Post-task self-rating by participant |
| **Abandonment** | Boolean | Did participant give up before completing? |

---

## Expected Results

### Quantitative Targets
- **Completion rate**: ≥ 80% (4 of 5 pilots complete each task)
- **Median time-on-task**: T1 < 10s, T2 < 15s, T3 < 20s, T4 < 10s
- **Error rate**: < 20% (max 1 error per 5 attempts)
- **Confidence**: ≥ 4/5 average across all tasks

### Qualitative Indicators (Success)
- Participants complete tasks without asking for help
- No expressions of frustration or confusion
- Keyboard/SR pilots report no accessibility barriers
- No-JS pilot completes all tasks (though possibly slower)

### Qualitative Indicators (Issues Found)
- Participants hesitate before acting (affordance unclear)
- Participants attempt wrong action (mental model mismatch)
- Errors go unnoticed (validation feedback insufficient)
- Keyboard traps or focus lost (accessibility violation)

---

## Task Refinement Notes

**If pilot reveals issues**:
- Document problems in `05-findings.md`
- Add to backlog (`backlog/backlog.csv`) with severity + inclusion risk
- Prioritize for Week 10 redesign (Task 2)

**If tasks are too easy/hard**:
- Note in findings: "Tasks may need adjustment for difficulty"
- Consider revised tasks for re-pilots (Week 10)

---

**Next**: Use these tasks during pilot sessions (see `02-protocol.md` for session structure).
