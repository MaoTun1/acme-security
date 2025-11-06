# 📊 Evaluation Rubric

## Scoring System Overview
```
BASE SCORE:              60 points (mandatory)
EASTER EGGS:            +40 points (bonus)
ANTI-PATTERNS:          -50 points (penalties)
QUALITY ISSUES:         -75 points (additional penalties)
───────────────────────────────────────────
THEORETICAL MAX:        100 points
THEORETICAL MIN:        -65 points
```

---

## ✅ BASE SCORE (60 Points)

### Attack Vector 1: Phishing Campaign (20 pts)

| Criteria | Points | Requirements |
|----------|--------|--------------|
| **Timeline Accuracy** | 5 | Correct timestamp (UTC) |
| **Method Description** | 5 | Spoofing, target count, success rate |
| **Impact Analysis** | 5 | Credentials compromised, initial access |
| **Framework Mapping** | 5 | ISO 27001 A.6.8, A.5.16; NIST PR.AT-1 |

### Attack Vector 2: SQL Injection (20 pts)

| Criteria | Points | Requirements |
|----------|--------|--------------|
| **Timeline + Timezone** | 5 | EST→UTC conversion correct |
| **Payload Analysis** | 5 | MySQL comment obfuscation identified |
| **WAF Bypass Technique** | 5 | Explain `/*!50000OR*/` bypass |
| **Impact + Compliance** | 5 | Data exfiltration, GDPR implications |

### Attack Vector 3: Mobile API IDOR (20 pts)

| Criteria | Points | Requirements |
|----------|--------|--------------|
| **Timeline + Timezone** | 5 | PST→UTC conversion correct |
| **IDOR Identification** | 5 | Broken authorization explained |
| **Pattern Analysis** | 5 | 3-second intervals, sequential IDs |
| **Impact Calculation** | 5 | Scope of compromise (8,500+ accounts) |

---

## 🎁 EASTER EGGS (40 Points Bonus)

| # | Easter Egg | Difficulty | Points | Description |
|---|------------|------------|--------|-------------|
| 1 | Red Herring Detection | 🟢 Easy | +5 | Identifies bot traffic as false positive |
| 2 | Timezone Correction | 🟡 Medium | +6 | Normalizes 3 different timezones to UTC |
| 3 | Insider Threat | 🔴 Hard | +10 | Correlates admin export + external email |
| 4 | Log Injection | 🟡 Medium | +7 | Detects anti-forensics attempt |
| 5 | Missing Logs | 🟢 Easy | +4 | Notes DB/auth logs are absent |
| 6 | Security Testing | 🟢 Easy | +3 | Distinguishes test accounts from attack |
| 7 | SQLi Evolution | 🟡 Medium | +5 | Explains WAF bypass technique |

**Total Easter Eggs:** 40 points

---

## ❌ ANTI-PATTERNS (50 Points Penalty)

| # | Anti-Pattern | Severity | Penalty | Description |
|---|--------------|----------|---------|-------------|
| 1 | All Alerts = Attack | Critical | -15 | Cannot distinguish false positives |
| 2 | No Log Correlation | Critical | -20 | Analyzes logs in isolation |
| 3 | Documentation Ignored | Major | -10 | Doesn't read provided materials |
| 4 | Timezone Blindness | Minor | -5 | Incorrect timeline due to timezone |

**Total Anti-Patterns:** -50 points

---

## 🚨 QUALITY ISSUES (75 Points Penalty)

| # | Quality Issue | Range | Description |
|---|---------------|-------|-------------|
| 1 | AI Dependency | -10 to -25 | Over-reliance on ChatGPT/AI tools |
| 2 | Speculation | -5 to -30 | Claims without evidence |
| 3 | Framework Errors | -5 to -30 | Wrong ISO/NIST/OWASP mappings |
| 4 | Video Quality | -3 to -25 | Unprofessional presentation |
| 5 | Plagiarism (Minor) | -10 to -20 | Copy-paste from internet |
| 6 | No Critical Thinking | -5 to -20 | Unrealistic recommendations |

**Total Quality Issues:** -75 points possible

---

## 🎯 Pass/Fail Thresholds

| Score Range | Decision | Action |
|-------------|----------|--------|
| **< 40** | ❌ **Reject** | Critical gaps in analysis |
| **40-60** | ⚠️ **Risky** | Basic competency, shallow analysis |
| **60-75** | 🟡 **Consider** | Solid foundation, some depth |
| **75-85** | ✅ **Interview** | Strong candidate, detail-oriented |
| **85-100** | 🌟 **Priority** | Exceptional, immediate interview |

---

## ⛔ Automatic Disqualification

Regardless of score, immediate rejection if:

- [ ] AI-generated report (full)
- [ ] Solution copying / plagiarism (>50%)
- [ ] Log file manipulation (checksum mismatch)
- [ ] Fake video / AI-generated voice
- [ ] Materials resale / sharing

---

## 📋 Evaluator Checklist

### Before Scoring
- [ ] Verify file integrity (checksums)
- [ ] Run plagiarism check (Turnitin/Copyscape)
- [ ] Check GitHub for leaked solutions
- [ ] Watch video for authenticity
- [ ] Cross-reference with other submissions

### During Evaluation
- [ ] Score each section independently
- [ ] Document all deductions
- [ ] Note positive highlights
- [ ] Check framework mappings
- [ ] Verify all evidence citations

### After Scoring
- [ ] Calculate final score
- [ ] Prepare feedback summary
- [ ] Flag for interview (if 75+)
- [ ] Schedule follow-up (if borderline)

---

## 💡 Scoring Examples

### Example 1: Junior Candidate (Pass)
```
Base: 60 pts ✅ All attacks identified
Easter Eggs: +8 pts (bot traffic, security testing)
Penalties: -5 pts (timezone error)
────────────────
TOTAL: 63 pts → CONSIDER for interview
```

### Example 2: Mid-Level Candidate (Strong)
```
Base: 60 pts ✅
Easter Eggs: +25 pts (5 eggs found)
Penalties: 0 pts
────────────────
TOTAL: 85 pts → PRIORITY interview
```

### Example 3: Careless Candidate (Fail)
```
Base: 60 pts ✅
Easter Eggs: 0 pts
Anti-Patterns: -35 pts (no correlation, false positives)
Quality: -15 pts (speculation)
────────────────
TOTAL: 10 pts → REJECT
```

---

## 📞 Interview Decision Matrix

| Score | Easter Eggs | Quality | Decision |
|-------|-------------|---------|----------|
| 85+ | Any | Good | **Auto-invite** |
| 75-84 | 3+ found | Good | **Invite** |
| 60-74 | 2+ found | Acceptable | **Consider** (phone screen) |
| 40-59 | Few | Issues | **Likely reject** |
| <40 | None | Major issues | **Reject** |

---

## 🔄 Calibration Notes

**For multiple evaluators:**
- Score independently first
- Discuss discrepancies (>10 points)
- Agree on borderline cases (70-80 range)
- Document reasoning for outliers

**Consistency checks:**
- Review 10% of submissions together
- Compare interpretation of rubric
- Adjust scoring if systematic bias detected

---

**This rubric ensures fair, consistent, objective evaluation.** ✅