- Completion (0/1): finished within 180s
- Time-on-task (ms): request start→end
- Errors: validation, server
- A11y confirmations: keyboard-only, status, focus
- UMUX-Lite x2; Confidence 1–5

# Evaluation Metrics — Week 9

## Quantitative Measures

### 1. Time-on-Task (Efficiency)
**Definition**: Seconds from task start to successful completion
**How to collect**: Manual stopwatch OR instrumentation (timestamp diff)
**Analysis**: Mean, median, outliers per task

**Why it matters**: Long times indicate usability problems or confusion

---

### 2. Task Success Rate (Effectiveness)
**Definition**: Percentage of participants who complete task without help
**How to collect**: Binary (1 = success, 0 = fail/abandon)
**Analysis**: Success % per task, identify problematic tasks

**Why it matters**: <80% success = serious usability issue

---

### 3. Error Rate (Accuracy)
**Definition**: Number of validation errors, wrong clicks, back-tracking per task
**How to collect**: Manual tally during observation OR server logs (400 errors)
**Analysis**: Mean errors per task, categorise by type

**Why it matters**: Frequent errors = unclear interface or poor error prevention

---

### 4. Mode Comparison (HTMX vs No-JS)
**Definition**: Time and success differences between JS-enabled and no-JS paths
**How to collect**: Run each participant in one mode, compare groups
**Analysis**: t-test or Mann-Whitney U test (if N > 10 per group)

**Why it matters**: Validates dual-path parity claim

---

## Qualitative Measures

### 5. Post-Task Confidence (Subjective)
**Definition**: 5-point Likert scale: "I am confident I completed the task correctly"
**How to collect**: Verbal question after each task
**Analysis**: Mean score per task, identify low-confidence tasks

**Why it matters**: Low confidence despite success = poor feedback design

---

### 6. Think-Aloud Observations
**Definition**: Verbal comments during task ("Where's the Save button?", "I'm confused")
**How to collect**: Note-taking during pilot
**Analysis**: Thematic coding (confusion points, positive remarks)

**Why it matters**: Reveals WHY metrics are good/bad

---

### 7. Accessibility Barriers (Observational)
**Definition**: Moments where keyboard/SR participant struggles
**How to collect**: Note when Tab order confuses, focus lost, SR silent
**Analysis**: List barriers, map to WCAG criteria

**Why it matters**: Direct evidence of inclusion failures

---

## Data Collection Plan

**Per participant**:
- Task 1-4: Time, success, errors, confidence, mode
- Think-aloud notes: Freeform observations
- Accessibility notes: Specific barriers encountered

**Sample size**: 3-5 participants (peer pilots)

**Storage**: `data/metrics.csv` (local, .gitignored)
