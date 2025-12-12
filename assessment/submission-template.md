# COMP2850 HCI Assessment: Evaluation & Redesign Portfolio

> **📥 Download this template**: [COMP2850-submission-template.md](/downloads/COMP2850-submission-template.md)
> Right-click the link above and select "Save link as..." to download the template file.

**Student**: Fareedah Fashola [201830811]
**Submission date**: [12/12/2025]
**Academic Year**: 2025-26

---
## Privacy & Ethics Statement

- [ ] I confirm all participant data is anonymous (session IDs use P1_xxxx format, not real names)
- [ ] I confirm all screenshots are cropped/blurred to remove PII (no names, emails, student IDs visible)
- [ ] I confirm all participants gave informed consent
- [ ] I confirm this work is my own (AI tools used for code assistance are cited below)

**AI tools used** (if any): [e.g., "Copilot for route handler boilerplate (lines 45-67 in diffs)"]

---

## 1. Protocol & Tasks

### Link to Needs-Finding (LO2)

**Week 6 Job Story #1**:
> S3: "When i add/edit/delete a task, I want confirmation that the task succeeded"
**How Task 1 tests this**:
We check to see the confidence level of participants after the task which indicates if theyre confident the task succeeded

> S4: When tasks pile up it becomes a very long list. 
**How Task 2 tests this**:
Making sure filtering works so when theres a long list of tasks, it can be broken down.

>  S1: "When I'm Using my laptop without a trackpad, i want every core function to be accessible through the keyboard"
Tasks 1, 2, 3 and 4 test this so testing editing, adding, filtering and deleting.

---

### Evaluation Tasks (4-5 tasks)
## Task 3 (T3): Add task

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

- **Linked to**: - S3 confirmation feedback

---

## Task 1 (T1): [Filter tasks]

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

**Linked to**: 
- S4 organising very long list of tasks
- S1 keyboard accessibility

---

## Task 2 (T2): Edit Task

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
- Potential issue 1: "Inline edit form not keyboard-accessible

- **Linked to**: - S1 keyboard accessibility


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

- **Linked to**: 
- S1 keyboard accessibility

---

### Consent Script (They Read Verbatim)

**Introduction**:
"Thank you for participating in my HCI evaluation. This will take about 15 minutes. I'm testing my task management interface, not you. There are no right or wrong answers."

**Rights**:
- [ ] "Your participation is voluntary. You can stop at any time without giving a reason."
- [ ] "Your data will be anonymous. I'll use a code (like P1) instead of your name."
- [ ] "I may take screenshots and notes. I'll remove any identifying information."
- [ ] "Do you consent to participate?" [Wait for verbal yes]

**Recorded consent timestamp**: [e.g., "P1 consented 22/11/2025 14:05"]
- P1 consented 07-12-2025 19:30
- P2 consented 07-12-2025 20:12
- P3 consented 08-12-2025 12:51
---

## 2. Findings Table

**Instructions**: Fill in this table with 3-5 findings from your pilots. Link each finding to data sources.

| Finding | Data Source | Observation (Quote/Timestamp) | WCAG | Impact (1-5) | Inclusion (1-5) | Effort (1-5) | Priority |
|---------|-------------|------------------------------|------|--------------|-----------------|--------------|----------|
| Edit and delete buttons are not keyboard accessible using safari default settings| metrics.csv no T2/T4 entries pilot-notes(L49-51) | P1: “Pilot could not navigate to Edit or Delete… kept tabbing between Add and Filter.” | 2.1.1 Keyboard A | 5 | 5 | 3 | 7 |
| Confirmation messages not visible enough | Pilot-notes(L36-37) | On |  | [1-5] | [1-5] | [1-5] | [Score] |
| Edit doesnt work with js off | Pilot-notes(P3L208-217) | "I don't understand whats happening everytime i push the edit button, it just reloads the page and doesn't show my edit" | - | 5 | 4 | 4 | 5 |
| Edit and delete buttons closely resemble each other (have the same colour ) | Pilot notes (P2L129 - 133)| 1.4.3 Contrast minimum | it would be helpful if edit button was a different colour from delete button | 3 | 3 | 2 | 4|

**Priority formula**: (Impact + Inclusion) - Effort

**Top 3 priorities for redesign**:
1. Fix keyboard accessibility for Edit/Delete -- Priority 7
2. Improve confirmation visibility  -— Priority 6
3. Fix Edit no-JS behaviour — Priority 5

---

## 3. Pilot Metrics (metrics.csv)

**Instructions**: Paste your raw CSV data here OR attach metrics.csv file

```csv
ts_iso,session_id,request_id,task_code,step,outcome,ms,http_status,js_mode
2025-11-22T14:18:23.456Z,P1_a7f3,req_001,T1_add,success,,890,200,on
[Your metrics data here - all rows from Logger.kt output]

ts_iso,session_id,request_id,task_code,step,outcome,ms,http_status,js_mode
2025-12-07T19:28:51.615928134Z,94ba96,r_3362200c,T0_list,success,,134,200,off
2025-12-07T19:29:48.316560705Z,94ba96,r_f91d32a1,T3_add,success,,38,200,on
2025-12-07T19:29:54.554522613Z,94ba96,r_b86a9229,T2_edit,success,,4,200,on
2025-12-07T19:30:39.354390052Z,94ba96,r_dc729ef6,T3_add,success,,7,200,on
2025-12-07T19:30:57.306419452Z,94ba96,r_c49515af,T3_add,success,,11,200,on
2025-12-07T19:31:07.254263828Z,94ba96,r_5f57b649,T1_filter,success,,18,200,on
2025-12-07T19:31:09.673696580Z,94ba96,r_4228b2e0,T1_filter,success,,8,200,on
2025-12-07T19:31:35.524489732Z,94ba96,r_1a98f746,T3_add,success,,34,200,on
2025-12-07T19:32:03.673223958Z,94ba96,r_942996d3,T3_add,success,,26,200,on
2025-12-07T19:38:14.224050871Z,94ba96,r_e98805ea,T3_add,success,,13,200,on
2025-12-07T19:41:23.424920793Z,94ba96,r_612ebfa2,T4_delete,success,,5,200,on
2025-12-07T19:43:42.415498554Z,94ba96,r_ca3bb52d,T3_add,success,,9,200,on
2025-12-07T19:50:10.531645085Z,94ba96,r_ded49340,T0_list,success,,11,200,off
2025-12-07T19:50:43.995278304Z,94ba96,r_3e5bd098,T1_filter,success,,10,200,on
2025-12-07T19:50:44.455074926Z,94ba96,r_706912cb,T1_filter,success,,7,200,on
2025-12-07T19:50:45.419657514Z,94ba96,r_c5ce8969,T1_filter,success,,4,200,on
2025-12-07T19:50:46.018950996Z,94ba96,r_95458f12,T1_filter,success,,3,200,on
2025-12-07T19:50:46.890075078Z,94ba96,r_ea882a28,T1_filter,success,,10,200,on
2025-12-07T19:50:50.180327592Z,94ba96,r_cfdb468f,T1_filter,success,,4,200,on
2025-12-07T19:50:50.760243658Z,94ba96,r_bf33825d,T1_filter,success,,7,200,on
2025-12-07T19:50:51.013011545Z,94ba96,r_292039ee,T1_filter,success,,7,200,on
2025-12-07T19:50:55.976756453Z,94ba96,r_5aeb3315,T1_filter,success,,6,200,on
2025-12-07T19:50:58.547503124Z,94ba96,r_b058d62f,T1_filter,success,,3,200,on
2025-12-07T19:50:59.238211976Z,94ba96,r_77a981a3,T1_filter,success,,3,200,on
2025-12-07T20:10:25.808428382Z,94ba96,r_f0cc01e4,T1_filter,success,,5,200,on
2025-12-07T20:10:46.362287609Z,94ba96,r_3a001bc7,T4_delete,success,,2,200,on
2025-12-07T20:11:15.764895348Z,94ba96,r_ca084c85,T3_add,success,,11,200,on
2025-12-07T20:14:09.540273145Z,94ba96,r_3d44e961,T1_filter,success,,3,200,on
2025-12-07T20:14:10.068258207Z,94ba96,r_befecbca,T1_filter,success,,3,200,on
2025-12-07T20:14:10.487163842Z,94ba96,r_78d581cd,T1_filter,success,,4,200,on
2025-12-07T20:14:10.796673944Z,94ba96,r_fa9cb274,T1_filter,success,,3,200,on
2025-12-07T20:14:11.378459604Z,94ba96,r_1a51d516,T1_filter,success,,9,200,on
2025-12-07T20:14:14.570796174Z,94ba96,r_8e3808ba,T1_filter,success,,3,200,on
2025-12-07T20:14:23.867531517Z,94ba96,r_517b8c92,T1_filter,success,,7,200,on
2025-12-07T20:16:40.340175318Z,94ba96,r_3f446fc7,T1_filter,success,,6,200,on
2025-12-07T20:16:40.604803730Z,94ba96,r_757f3f48,T1_filter,success,,4,200,on
2025-12-07T20:18:32.203274715Z,94ba96,r_ad323508,T2_edit,success,,3,200,on
2025-12-07T20:21:53.407436823Z,94ba96,r_f93f60c4,T4_delete,success,,2,200,on
2025-12-08T13:10:14.626798788Z,94ba96,r_c57a5f89,T0_list,success,,178,200,off
2025-12-08T13:10:30.621243602Z,94ba96,r_98bcb615,T3_add,success,,16,200,off
2025-12-08T13:10:30.860561268Z,94ba96,r_edeed653,T0_list,success,,44,200,off
2025-12-08T13:10:36.661872759Z,94ba96,r_59dfad44,T3_add,success,,2,200,off
2025-12-08T13:10:36.824292735Z,94ba96,r_77964c46,T0_list,success,,21,200,off
2025-12-08T13:10:53.776129462Z,94ba96,r_3da9daf1,T4_delete,success,,5,200,off
2025-12-08T13:10:53.933065761Z,94ba96,r_e312a9e5,T0_list,success,,28,200,off
2025-12-08T13:10:57.327666231Z,94ba96,r_1e1dd9f1,T4_delete,success,,3,200,off
2025-12-08T13:10:57.464806599Z,94ba96,r_77b9414a,T0_list,success,,18,200,off
2025-12-08T13:11:25.616361161Z,94ba96,r_748eb975,T0_list,success,,20,200,off
2025-12-08T13:16:27.436509642Z,94ba96,r_d10d2527,T0_list,success,,12,200,off
2025-12-08T13:18:28.514480532Z,94ba96,r_bae0bb3e,T3_add,success,,11,200,on
2025-12-08T13:19:43.979750587Z,94ba96,r_1616a2ab,T3_add,success,,3,200,off
2025-12-08T13:19:44.108342989Z,94ba96,r_0bc982be,T0_list,success,,9,200,off
2025-12-08T13:27:59.718610917Z,94ba96,r_b54b5448,T0_list,success,,10,200,off
2025-12-08T13:28:51.091878911Z,94ba96,r_40109338,T0_list,success,,6,200,off
2025-12-08T13:35:17.746523440Z,94ba96,r_8665aef6,T0_list,success,,7,200,off
2025-12-08T13:35:19.036865587Z,94ba96,r_856c45c4,T0_list,success,,6,200,off
2025-12-08T13:35:21.974455254Z,94ba96,r_1f75f248,T0_list,success,,7,200,off
2025-12-08T13:35:46.658073982Z,94ba96,r_e08d460d,T0_list,success,,9,200,off
2025-12-08T13:43:10.644120998Z,94ba96,r_a77707f5,T0_list,success,,11,200,off
2025-12-08T13:44:20.585565888Z,94ba96,r_5cc3efe8,T0_list,success,,12,200,off
2025-12-08T13:44:24.259404342Z,94ba96,r_80eb4789,T0_list,success,,6,200,off
2025-12-08T13:44:27.784536050Z,94ba96,r_52bf35c8,T0_list,success,,7,200,off
2025-12-08T13:44:43.946919736Z,94ba96,r_eae5aa2b,T4_delete,success,,2,200,off
2025-12-08T13:44:43.993015467Z,94ba96,r_acfd33ec,T0_list,success,,6,200,off
2025-12-08T13:44:48.879878395Z,94ba96,r_041f7c7a,T4_delete,success,,3,200,off
2025-12-08T13:44:49.338833577Z,94ba96,r_6a7f130b,T0_list,success,,5,200,off

```

**Participant summary**:
- **P1**: Keyboard-only, HTMX-on
- **P2**: Standard mouse and track-pad with HTMX-on
- **P3**: Standard mouse and track-pad with js-off

**Total participants**: [n=3]

---

## 4. Implementation Diffs

**Instructions**: Show before/after code for 1-3 fixes. Link each to findings table.

### Fix 1: Change colour of delete button so its easily  distinguishable

**Addresses finding**: [Finding 4 from table above]

**Before** (/workspaces/comp2850-minimal-solution/src/main/resources/templates/tasks/_item.peb [L11-18]):
```kotlin
// ❌ Problem code
  <form action="/tasks/{{ task.id }}/delete" method="post" style="display: inline;"
        hx-delete="/tasks/{{ task.id }}"
        hx-target="#task-{{ task.id }}"
        hx-swap="outerHTML"
        hx-confirm="Delete the task '{{ task.title }}'?">
    <button type="submit" aria-label="Delete task: {{ task.title }}">Delete</button>
  </form>

```

**After** (/workspaces/comp2850-minimal-solution/src/main/resources/templates/tasks/_item.peb [L11-18]):
```kotlin
// ✅ Fixed code
<form action="/tasks/{{ task.id }}/delete" method="post" style="display: inline;"
        hx-delete="/tasks/{{ task.id }}"
        hx-target="#task-{{ task.id }}"
        hx-swap="outerHTML"
        hx-confirm="Delete the task '{{ task.title }}'?">
    <button type="submit" aria-label="Delete task: {{ task.title }}"
    style="background-color: #d32f2f; border-color: #d32f2f; color: white;">Delete</button>
  </form>
```

**What changed**: [1 sentence - what you added/removed/modified]
- I added a red colour to the delete button so it wasn't on the default blue colour.
**Why**: [1 sentence - which WCAG criterion or usability issue this fixes]
- WCAG 1.4.3 Contrast (Minimum), easily distinguishable buttons
**Impact**: [1-2 sentences - how this improves UX, who benefits]
- The high contrast red improves the UX by making the action such as delete easier to recognise and reducing the chance of accidental clicks. This benefits every users but mostly users with poor vision.
---

### Fix 2: This is a non code fix but the default safari settings don't automatically enable using tab to navigate through the website 

**Addresses finding**: [Finding 1]

**Before**:
```kotlin
N/A
see image in screenshots folder
```

**After**:
```kotlin
N/A
see image in screenshots folder
```

**What changed**:
Can use tab to navigate through 
**Why**: so keyboard-only can be used 

**Impact**: WCAG 2.1.1 keyboard accesibility, means all actions are now accessible through the keyboard 

---
---

## 5. Verification Results

### Part A: Regression Checklist (20 checks)

**Instructions**: Test all 20 criteria. Mark pass/fail/n/a + add notes.

| Check | Criterion | Level | Result | Notes |
|-------|-----------|-------|--------|-------|
| **Keyboard (5)** | | | | |
| K1 | 2.1.1 All actions keyboard accessible | A | [pass] | "Tested Tab/Enter on all buttons" (FIXED in fix#2)|
| K2 | 2.4.7 Focus visible | AA | [pass] | ["blue outline on all interactive elements"] |
| K3 | No keyboard traps | A | [pass] | ["Can Tab through filter, edit, delete without traps"] |
| K4 | Logical tab order | A | [pass] | ["Top to bottom, left to right"] |
| K5 | Skip links present | AA | [pass] | ["Skip to main content works"] |
| **Forms (3)** | | | | |
| F1 | 3.3.2 Labels present | A | [pass] | []"All inputs have <label> or aria-label"] |
| F2 | 3.3.1 Errors identified | A | [pass] | ["Errors have role=alert"] |
| F3 | 4.1.2 Name/role/value | A | [pass] | ["All form controls have accessible names"] |
| **Dynamic (3)** | | | | |
| D1 | 4.1.3 Status messages | AA | [fail] | ["Status div has role=status"] |
| D2 | Live regions work | AA | [pass] | [ "announces 'Task added'"] |
| D3 | Focus management | A | [pass] | ["Focus moves to input when a task input field is empty"] |
| **No-JS (3)** | | | | |
| N1 | Full feature parity | — | [fail] | ["All CRUD ops work without JS"] |
| N2 | POST-Redirect-GET | — | [fail] | ["No double-submit on refresh"] |
| N3 | Errors visible | A | [fail] | ["Error summary shown in no-JS mode"] |
| **Visual (3)** | | | | |
| V1 | 1.4.3 Contrast minimum | AA | [pass] | All text contrast with colour of boxes and edit and delete different colours(FIXED in Fix #1)] |
| V2 | 1.4.4 Resize text | AA | [pass] | ["200% zoom, no content loss"] |
| V3 | 1.4.11 Non-text contrast | AA | [pass] | ["Focus indicator 4.5:1"] |
| **Semantic (3)** | | | | |
| S1 | 1.3.1 Headings hierarchy | A | [pass] | [e.g., "h1 → h2 → h3, no skips"] |
| S2 | 2.4.1 Bypass blocks | A | [pass] | [e.g., "<main> landmark, <nav> for filter"] |
| S3 | 1.1.1 Alt text | A | [pass] | [e.g., "No images in interface OR all have alt"] |

**Summary**: [16/20 pass], 4/20 fail]
**Critical failures** (if any): [List any Level A fails]
- Errors not visible in no-JS mode
---

### Part B: Before/After Comparison

**Instructions**: Compare Week 9 baseline (pre-fix) to Week 10 (post-fix). Show improvement.

| Metric | Before (Week 9, n=3) | After (Week 10, n=1) | Change | Target Met? |
|--------|----------------------|----------------------|--------|-------------|
| SR / status visibility | [1/3 (33%)] | [e.g., 1/1 (100%)] |  +17% | [X] |
| Accidental edit/delete clicks | [1/3 (33%)] | [0/1 0%] | [-33%] | [✅] |
| Median time -- Delete task | [6000ms] | [4500ms] | [-15000ms] | [✅] |
| Keyboard navigation | 2/4 tasks 0%| 4/4 tasks 100% | [+75%] | [X] |
| WCAG 1.4.3 (contrast minimum) pass | [fail] | [pass] | 100% | [✅] |

**Re-pilot details**:
- **P4* (post-fix): [Variant -  mouse + keyboard (standard HTMX)"] - [11/12/2025]
- Participant correctly identified Delete button immediately
- No accidental clicks on Edit
- Task completed faster with less hesitation

**Limitations / Honest reporting**:
[If metrics didn't improve or only modestly: explain why. Small sample size? Wrong fix? Needs more iteration? Be honest - valued over perfect results.]

- Small sample – Only 3 pilots before fixes and 1 after, so improvements can’t be generalised.
- I used a very small sample of people for the first pilot(3) and an even smaller sample for the repilot(1), this negatively affects the measure of success/improvements and makes results less reliable.
- Safari keyboard issue – Many keyboard failures were caused by Safari’s default setting that disables Tab navigation, not by the interface itself. This limits how accurately keyboard accessibility could be measured.
- Confirmation messages are still easy to miss, even after fixes, the status message appears small at the top of the page, so usability around feedback remains partially unresolved.
– Tasks were short and controlled; real usage may reveal different issues.


---

## 6. Evidence Folder Contents

**Instructions**: List all files in your evidence/ folder. Provide context.

### Screenshots

| Filename | What it shows | Context/Link to finding |
|----------|---------------|-------------------------|
| before-button-colours.png | Colour of delete buttons before code fix | Finding #4 |
| after-button-colours.png | Colour of delete buttons changed to red after code fix | Fix #1 verification |
| keyboard-setting-before.png | Default safari keyboard settings | Finding #1  |
| keyboard-settings-after.png | Keyboard settings after change | Fix #2 |

**PII check**:
- [ ] All screenshots cropped to show only relevant UI
- [ ] Browser bookmarks/tabs not visible
- [ ] Participant names/emails blurred or not visible

---

### Pilot Notes

**Instructions**: Attach pilot notes as separate files (P1-notes.md, P2-notes.md, etc.). Summarize key observations here.

**P1** ([ Variant - "keyboard only - standard HTMX"]):
- **Key observation 1**: Could not navigate to edit/delete buttons (19::)
- **Key observation 2**: "This is quite confusing to navigate through" (19:43:20)

**P2** ([Variant - trackpad + mouse - standard HTMX]):
- **Key observation 1**: [Quote + timestamp]
- **Key observation 2**: [Quote + timestamp]

**P3* ([ Variant - "Standard mouse + no-js"]):
- **Key observation 1**: [Quote + timestamp - e.g., "Struggled with filter button (09:47)"]
- **Key observation 2**: [Quote + timestamp]
---

## Evidence Chain Example (Full Trace)

**Instructions**: Pick ONE finding and show complete evidence trail from data → fix → verification.

**Finding selected**: ["Finding #4 - Edit and delete buttons too similar"]

**Evidence trail**:
1. **Data**: P3-notes lines 128-132 show P3 accidentally clicked the wrong button
2. **Observation**: P3 pilot notes timestamp 20:18:27 - Quote: "Oh i accidentally hit the delete instead of edit, they look very similar"
3. **Screenshot**: before-button-colours.png shows the colour of the delete buttons before it was chnaged to increase contrast
4. **WCAG**: 1.4.3 Contrast Minimum (Level A) violation - could exclude low-vision users and cause accidental clicks/actions
5. **Prioritisation**: findings-table.csv row 4 - Priority score 4 (Impact 3 + Inclusion 3 - Effort 2)
6. **Fix**: implementation-diffs.md Fix #1 - Changed the colour of the delete button from blue to red so it is different from edit 
7. **Verification**: verification.csv Part A row V1 - 1.4.3 now PASS 
8. **Before/after**: verification.csv Part B row 5 - WCAG 1.4.3 Contrast Minimum now PASS
9. **Re-pilot**: P4 (mouse + standard HTMX) pilot notes - "It was very easy to tell which is the delete button and which is edit"

**Complete chain**: Data → Observation → Interpretation → Fix → Verification ✅

---

## Submission Checklist

Before submitting, verify:

**Files**:
- [ ] This completed template (submission-template.md)
- [ ] metrics.csv (or pasted into Section 3)
- [ ] Pilot notes (P1-notes.md, P2-notes.md, etc. OR summarised in Section 6)
- [ ] Screenshots folder (all images referenced above)
- [ ] Privacy statement signed (top of document)

**Evidence chains**:
- [ ] findings-table.csv links to metrics.csv lines AND/OR pilot notes timestamps
- [ ] implementation-diffs.md references findings from table
- [ ] verification.csv Part B shows before/after for fixes

**Quality**:
- [ ] No PII in screenshots (checked twice!)
- [ ] Session IDs anonymous (P1_xxxx format, not real names)
- [ ] Honest reporting (limitations acknowledged if metrics didn't improve)
- [ ] WCAG criteria cited specifically (e.g., "3.3.1" not just "accessibility")

**Pass criteria met**:
- [ ] n=2+ participants (metrics.csv has 2+ session IDs)
- [ ] 3+ findings with evidence (findings-table.csv complete)
- [ ] 1-3 fixes implemented (implementation-diffs.md shows code)
- [ ] Regression complete (verification.csv has 20 checks)
- [ ] Before/after shown (verification.csv Part B has data)

---

**Ready to submit?** Upload this file + evidence folder to Gradescope by end of Week 10.

**Estimated completion time**: 12-15 hours across Weeks 9-10

**Good luck!** 🎯
