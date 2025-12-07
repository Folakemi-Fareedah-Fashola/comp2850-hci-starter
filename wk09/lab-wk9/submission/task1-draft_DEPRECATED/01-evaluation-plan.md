# Task 1: Evaluation Plan

**Student ID**: [201830811]
**Date**: [2025-12-05]
**Module**: COMP2850 HCI

---

## 1. Evaluation Objectives

**What are you evaluating?**
- How users interact with Task manager, i.e. adding, editing and deleting tasks and the accessibility 
- Mainly evaluating add, edit and delete and navigating with the keyboard

**Why evaluate now?**
- Identifying issues that need fixing before redesigning
- determine whether current UI supports users who need accessibility adjustments such as no touchpad/mouse

---

## 2. Link to Needs-Finding (LO2)

**Connection to Week 6 job stories**:
- S1: "When I'm Using my laptop without a trackpad, i want every core function to be accessible through the keyboard"
- S3: "When i add/edit/delete a task, I want confirmation that the task succeeded"
- S4: When tasks pile up it becomes a very long list. 

**How needs-finding shaped evaluation**:
- Needs finding revealed that participants forget tasks often so adding a task must be quick and confirmed. Due to this we are measure the time it takes to add a task and the confirmation as a primary metric.
- It also showed that participants get overwhelmed or stressed out by long list so testing filtering becomes important.
- Participants also struggle when trying to navigate using just the keyboard so we must test the accessibility of the task manager using solely the keyboard.

**Evidence trail**: Week 6 job stories → backlog items → features implemented → evaluation tasks

---

## 3. Evaluation Method Selection

**Method chosen**: Task-based usability testing

**Rationale**:
- It shows whether the tasks(add,edit,delete) work
- It also reveals accessibility problems, especially for people who are mostly keyboard users
- Can see time based and error based metrics which will be useful for redesign 
- Surveys: difficult to show how users interact with task manager

**Target participants**: Peer students (n=4 minimum)

---

## 4. Success Criteria

**Quantitative metrics**:
- **Time-on-task**: Target < 20 seconds for adding task, < 30 seconds for editing a task, < 20 seconds for deleting a task, <20 second for filtering a task
- **Completion rate**: Target ≥ 80% (participants complete without critical errors)
- **Error rate**: Target < 20% (validation errors, incorrect submissions)
- **Confidence**: Target ≥ 4/5 average (post-task self-rating)

**Qualitative indicators**:
- Participants can complete tasks without asking for help
- No confusion about interface affordances (buttons, links, form fields)
- Errors are recoverable without frustration
- No accessibility barriers (keyboard traps, missing announcements, invisible focus)

---

## 5. Evaluation Scope

**In scope**:
- T1 add task (with confirmation)
- T2 edit task (with confirmation)
- T3 Filter task 
- T4 Delete task with confirmation
- [Feature 3: e.g., Inline editing]
- [Feature 4: e.g., Delete with confirmation]

**Out of scope** (not evaluated in this round):
- [automatic prioritisation]
- [Known limitations accepted as constraints]

---

## 6. Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| Insufficient participants (n<2) | Can't identify patterns | Recruit early, offer flexible scheduling |
| Technical failures during pilots | Lost data, incomplete sessions | Test setup before pilots, have backup device |
| Pilot bias (peers know the system) | Overly positive results | Use structured tasks, observe actions not opinions |
| Privacy breach (PII in logs) | GDPR violation | Use anonymous session IDs, no names/emails in data |

---

## 7. Ethical Considerations

**Consent**: ✅ Participants will read and confirm consent protocol before starting
**Right to withdraw**: ✅ Participants can stop at any time without penalty
**Anonymity**: ✅ Only session IDs recorded, no names/emails in data files
**Data retention**: ✅ Data stored locally, deleted after analysis (6 weeks max)
**PII in screenshots**: ✅ All screenshots cropped/scrubbed before submission

---

## 8. Timeline

| Activity | Date/Time | Duration |
|----------|-----------|----------|
| Finalize protocol & tasks | Week 9 Lab 1 | 1 hour |
| Recruit participants | Week 9 (before Lab 2) | 2 days |
| Conduct pilots | Week 9 Lab 2 | 2 hours |
| Debrief & synthesise findings | Week 9 Lab 2 | 30 mins |
| Assemble Task 1 pack | Week 9 Lab 2 (end) | 20 mins |
| Submit to Gradescope | Week 9 Lab 2 deadline | - |

---

## 9. Expected Outcomes

**What will you learn from this evaluation?**
- Are users able to add tasks quickly 
- Is filtering possible and does it work properly
- What are the main usability constraints
- Are confirmation messages shown
- Are features keyboard accessible

**How will results inform redesign?**
- Findings will be prioritised using (Impact + Inclusion) – Effort matrix
- Top 3 issues will be addressed in Week 10 redesign (Task 2)
- Evidence chains will link raw data → findings → backlog items → fixes

---

## References

- [Nielsen: Usability Testing 101](https://www.nngroup.com/articles/usability-testing-101/)
- [W3C: Measuring Accessibility](https://www.w3.org/WAI/test-evaluate/metrics/)
- Week 9 Lab 1 materials: `wk09/lab-wk9/research/`
