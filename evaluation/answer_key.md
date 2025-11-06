# 🔑 Answer Key - Evaluator Guide

⚠️ **CONFIDENTIAL - FOR EVALUATORS ONLY**

This document contains correct answers and common mistakes.

---

## ✅ CORRECT ANSWERS

### Attack Vector 1: Phishing Campaign

**Timeline (UTC):**
```
2024-10-15 09:00:23 UTC - Phishing email sent
Target: 500 employees
Success: 3 users clicked
Credentials: user1@acme.com / password harvested
```

**ISO 27001:2022:**
- A.6.8 - Information security awareness training ✅
- A.5.16 - Identity management ✅

**NIST CSF:**
- PR.AT-1 - Security awareness training ✅

**MITRE ATT&CK:**
- T1566 - Phishing ✅

---

### Attack Vector 2: SQL Injection

**Timeline (EST → UTC):**
```
09:20:30 EST = 14:20:30 UTC - First attempt (blocked)
09:21:15 EST = 14:21:15 UTC - Second attempt (blocked)
09:23:45 EST = 14:23:45 UTC - SUCCESS (WAF bypass)
```

**Payload:**
```sql
ticker=AAPL' /*!50000OR*/ 1=1--
```

**Technique:** MySQL inline comment obfuscation  
**Bypass:** `/*!50000OR*/` comment syntax bypasses WAF

**ISO 27001:2022:**
- A.8.3 - Information access restriction ✅
- A.8.16 - Monitoring activities ✅

**OWASP:**
- A03:2021 - Injection ✅

---

### Attack Vector 3: IDOR

**Timeline (PST → UTC):**
```
06:45:10 PST = 14:45:10 UTC - Login
06:46:30 PST = 14:46:30 UTC - Own account (legitimate)
06:47:15 PST = 14:47:15 UTC - Attack starts
06:47:15-57 PST - 15 accounts in 42 seconds (3-sec intervals)
```

**Pattern:**
- Sequential account IDs (1524-1538)
- Same session token
- No authorization check

**ISO 27001:2022:**
- A.5.15 - Access control ✅
- A.8.3 - Information access restriction ✅

**OWASP API:**
- API1:2023 - Broken Object Level Authorization ✅

---

## 🎁 EASTER EGG SOLUTIONS

### #1: Red Herring (Bot Traffic)

**Location:** `api_logs.csv` lines 2-6

**Evidence:**
```
Timestamp: 01:30:15-19 PST
IP: 192.168.1.100 (internal)
Response: All 401 (failed)
User-Agent: Python-requests
```

**Conclusion:** Scheduled penetration test (NOT attack)

**Points:** +5 if correctly identified as false positive

---

### #2: Timezone Correction

**Timezones:**
- api_logs.csv: PST (UTC-8)
- web_logs.csv: EST (UTC-5)
- email_logs.csv: UTC

**Correct Timeline (UTC):**
```
09:00 - Phishing
14:20 - SQLi attempts start
14:23 - SQLi success
14:45 - IDOR attack
```

**Points:** +6 if all timezones correctly normalized

---

### #3: Insider Threat

**Evidence:**
```
email_logs.csv:
08:55:12 UTC - admin@acme → external_attacker@proton.me

web_logs.csv:
09:00:00 EST - /admin/user-export

Timeline:
08:55 - Admin sends file externally
09:00 - Admin exports user list
09:00 - Phishing starts (with exact user list)
```

**Conclusion:** Internal employee facilitated attack

**Points:** +10 if correlation found

---

### #4: Log Injection

**Location:** `web_logs.csv`

**Evidence:**
```csv
09:30:00,1523,/dashboard/home,200",200,203.0.113.45
                                ^^^
           Newline character injected here
```

**Attacker Goal:** Hide tracks by injecting fake legitimate entry

**Points:** +7 if anti-forensics detected

---

### #5: Missing Logs

**Missing:**
- Database query logs
- Authentication service logs

**Impact:**
- Cannot verify actual SQL executed
- Blind spots in investigation

**Points:** +4 if noted in architecture review

---

### #6: Security Testing

**Location:** `api_logs.csv` lines 7-10

**Evidence:**
```
User: sec_team
Accounts: 5001-5004 (test range)
IP: 10.0.0.50 (internal)
Documented in: security_test_schedule.pdf
```

**Conclusion:** Legitimate scheduled test

**Points:** +3 if distinguished from attack

---

### #7: SQLi Evolution

**Failed Attempts:**
```
09:20:30 - ticker=AAPL' OR 1=1-- → 403
09:21:15 - ticker=AAPL'; DROP TABLE-- → 403
09:22:00 - ticker=AAPL' UNION SELECT-- → 403
```

**Success:**
```
09:23:45 - ticker=AAPL' /*!50000OR*/ 1=1-- → 200
```

**Technique:** MySQL comment-based WAF evasion

**Points:** +5 if bypass technique explained

---

## ❌ COMMON MISTAKES

### Timeline Errors
❌ "Attack started at 01:30" (PST not converted)
❌ "Phishing happened after SQLi" (wrong order)
❌ Ignoring timezone differences entirely

### False Positives
❌ "Bot traffic is part of attack"
❌ "Security team was compromised"
❌ Cannot distinguish test from real

### Framework Errors
❌ ISO 27001:2013 (outdated)
❌ A.99.1 (doesn't exist)
❌ OWASP Top 10 #15 (only 10 items)

### Speculation
❌ "Attacker is probably from Russia"
❌ "This looks like nation-state APT"
❌ Claims without log evidence

---

## 🎯 INTERVIEW VERIFICATION QUESTIONS

Ask candidates who score 75+:

1. **"Walk me through your timeline construction."**
   - Should mention timezone normalization
   - Reference specific log entries

2. **"How did you identify the insider threat?"**
   - Should explain correlation method
   - Cite specific evidence

3. **"Why did you classify this as IDOR vs other vulnerability?"**
   - Should explain OWASP API1:2023
   - Describe authorization vs authentication

4. **"What tools did you use for analysis?"**
   - Acceptable: Excel, Python, grep, etc.
   - Red flag: "ChatGPT analyzed it for me"

5. **"How would you prioritize your remediation steps?"**
   - Should show risk-based thinking
   - Consider cost/benefit

---

## 📊 SCORING CALCULATOR
```python
# Pseudo-code for quick scoring

base_score = 60  # If all 3 attacks found

# Easter eggs
easter_eggs = 0
if red_herring_detected: easter_eggs += 5
if timezone_correct: easter_eggs += 6
if insider_found: easter_eggs += 10
if log_injection: easter_eggs += 7
if missing_logs: easter_eggs += 4
if security_test: easter_eggs += 3
if sqli_bypass: easter_eggs += 5

# Anti-patterns (penalties)
penalties = 0
if all_alerts_are_attacks: penalties += 15
if no_correlation: penalties += 20
if documentation_ignored: penalties += 10
if timezone_blind: penalties += 5

# Quality issues
quality = 0
if ai_dependency_high: quality += 25
if heavy_speculation: quality += 30
if framework_errors_many: quality += 30
if video_poor: quality += 25
if plagiarism: quality += 20
if no_critical_thinking: quality += 20

final_score = base_score + easter_eggs - penalties - quality
```

---

## 🚨 RED FLAGS (Immediate Review)

- Perfect score (100) on first try
- Report too polished (professional template)
- Video quality mismatch (perfect report, terrible video)
- Cannot explain findings in interview
- Submission timestamp shows <3 hours work
- Multiple identical phrase structures (AI)
- Verbatim text from Wikipedia/OWASP

---

**Use this guide to ensure consistent, fair evaluation.** ✅