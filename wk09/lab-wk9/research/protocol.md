# Evaluation Protocol — Week 9 Pilots

**Module**: COMP2850 HCI
**Activity**: Task-based usability pilots
**Date**: [2025-12-05]
**Researcher**: [Fareedah Fashola]

---

## Purpose

Evaluate task manager usability and accessibility through structured pilots. Data will inform Week 10 redesign and assessment submission.

## Consent (GDPR/Data Protection Act 2018)

**Lawful basis**: Legitimate interest (educational research) + informed consent

**Before starting**, confirm:
- [ ] Purpose explained (evaluate task manager, not testing you)
- [ ] Tasks described (4 scenarios, ~15 minutes)
- [ ] Data collected listed (times, clicks, observations - no PII)
- [ ] Right to withdraw explained (stop anytime, data deleted)
- [ ] Participant verbally consents

**Record**: Participant pseudonym (P1, P2...), date, consent confirmed (initials)

---

## Procedure

### Setup (5 minutes)
1. **Assign mode**: Participant 1 → HTMX, Participant 2 → No-JS (alternate)
2. **Disable JS if needed**: Chrome DevTools → Settings → Disable JavaScript
3. **Set session ID**: Open browser DevTools Console, paste:
   ```javascript
   document.cookie = "sid=P1_7a9f; path=/";  // P1 = Participant 1, random suffix



**Module**: COMP2850 HCI
**Week**: 9
**Pilot ID**: [e.g., P1, P2, P3, P4]
**Date**: [YYYY-MM-DD]
**Researcher**: [Your Name]

---

## Pre-Pilot Setup (5 minutes)

### 1. Generate Session ID
```bash
# Generate random 6-char hex ID
openssl rand -hex 3
# Example output: 7a9f2c
```

**Session ID**: `P#_______` (e.g., `P1_7a9f2c`)

### 2. Set Cookie (Browser Console)
```javascript
document.cookie = "sid=P1_7a9f2c; path=/";
```

**Verify**: Refresh page; check Application → Cookies → `sid` = `P1_7a9f2c`

### 3. Confirm Setup
- [ ] Application running on `http://localhost:8080/tasks`
- [ ] Browser configured (JS on/off, assistive tech if needed)
- [ ] `data/metrics.csv` ready (headers present)
- [ ] Consent script completed
- [ ] Pilot notes file created: `pilot-notes/P#_notes.md`

---

## Task Execution Protocol

For each task (T3, T1, T2, T4):

1. **Read task aloud**:
   > "Your task is to [describe task]. Let me know when you're done."
   
2. **Start timer** (manual or automated):
   ```
   [YYYY-MM-DD HH:MM:SS] Task [T#] START
   ```

3. **Observe silently**:
   - Do NOT guide the pilot unless they ask
   - Note any:
     - Hesitations (e.g., "Pilot paused for 5s")
     - Errors (e.g., "Validation message shown")
     - Unexpected behaviour (e.g., "Pilot used Back button")

4. **Stop timer when pilot says "done"**:
   ```
   [YYYY-MM-DD HH:MM:SS] Task [T#] END
   Duration: [##] seconds
   ```

5. **Check Logger output** (browser console or `data/metrics.csv`):
   ```
   ts_iso,session_id,request_id,task_code,step,outcome,ms,http_status,js_mode
   2025-01-10T14:35:22Z,P1_7a9f2c,req_001,T3_add,submit,success,450,200,js-on
   ```

6. **Ask confidence rating**:
   > "On a scale of 1 (not confident) to 5 (very confident), how confident are you that you completed this task correctly?"

   **Rating**: [ ] 1  [ ] 2  [ ] 3  [ ] 4  [ ] 5

7. **Record in pilot notes** (see template below)

---

## Task Definitions

### T1: Add Task (Baseline)
> "add complete 2860 worksheet 7 to the task manager"


**Success criteria**:
- Task appears in list
- Title exactly matches "Buy milk"
- Status message confirms addition (if applicable)

### T2: Filter Tasks
> "Show only 2860 tasks"

**Success criteria**:
- Filter applied (only 2870 tasks show or tasks that have "2870" in them)
- URL includes `?filter=2870` (no-JS) or status updated (HTMX)
- 2870 tasks visible

### T3: Edit Task (Accessibility-critical)
> "Change the title of 2860 worksheet 6 to 2860 worksheet 7"

**Success criteria**:
- Inline edit activated (button clicked or keyboard shortcut)
- New title saved
- List updates to show "2860 worksheet 7"

### T4: Delete Task (Confirmation)
> "Delete the complete 2860 worksheet 7 task."

**Success criteria**:
- Task removed from list
- Status message confirms deletion (if applicable)

---

