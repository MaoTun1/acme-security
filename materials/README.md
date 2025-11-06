# 📦 Lab Materials

This folder contains all materials needed for your security incident investigation.

## 📁 Files Overview

### Log Files

**⚠️ IMPORTANT: Use these EXACT files without modification**

| File | Description | Timezone | Rows | Format |
|------|-------------|----------|------|--------|
| `api_logs.csv` | Mobile API requests | PST (UTC-8) | ~30 | CSV |
| `email_logs.csv` | Email gateway logs | UTC | ~10 | CSV |
| `web_logs.csv` | Web application logs | EST (UTC-5) | ~25 | CSV |
| `waf_logs.csv` | WAF alerts | UTC | ~15 | CSV |

### Documentation

| File | Description |
|------|-------------|
| `current_architecture.png` | Current system architecture diagram |
| `api_docs.pdf` | API endpoint documentation |
| `security_test_schedule.pdf` | Scheduled security testing information |

## 🔐 File Integrity

**SHA-256 Checksums:**
```
[CHECKSUMS WILL BE ADDED AFTER FILES ARE CREATED]
api_logs.csv: b83b3021aa32666afbf4924d3fa34bb5654f783871469b21ae50e4abfcfbe0fc
email_logs.csv: 7647e9fbe7f94ebf58b67cdc4c73cebcd167b0a8431039145900982ab2dba9d0
web_logs.csv: b166c5f8fd9f2584ef8f06e2a51da1ef562db56c54e01d0678f7462aa4202445
waf_logs.csv: 0ce0555f0f205922234fc1d5685cf8ec0248f95271fd676d60402be7b58d48d3
```

**Verify file integrity before starting:**
```bash
sha256sum api_logs.csv
# Expected: <hash>
```

⚠️ **Any file modification will be detected and may result in disqualification.**

## 📋 What You'll Find

### In the Logs
- Normal user activity
- Suspicious patterns
- Attack indicators
- False positives (be careful!)
- Missing information (identify gaps)

### Key Challenges
- **Multiple timezones** - Logs use different time references
- **Noise and signal** - Distinguish real attacks from normal activity
- **Correlation required** - No single log tells the whole story
- **Incomplete data** - Some information is intentionally missing

## 🎯 Investigation Tips

1. **Start with the big picture** - What systems are involved?
2. **Timeline everything** - Normalize timezones first
3. **Cross-reference** - Correlate events across log sources
4. **Question assumptions** - Not all anomalies are attacks
5. **Document evidence** - Every claim needs log references
6. **Read all materials** - Documentation contains important context

## 🛠️ Recommended Tools

You can use any tools you're comfortable with:
- **Analysis:** Excel, Python (pandas), grep, awk
- **Diagrams:** draw.io, Lucidchart, PowerPoint
- **Timeline:** Spreadsheets, specialized forensic tools

## ⚠️ Common Mistakes

- ❌ Ignoring timezone differences
- ❌ Treating all anomalies as attacks
- ❌ Not reading documentation
- ❌ Working from a single log source
- ❌ Making assumptions without evidence

## 📚 Useful References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP API Security Top 10](https://owasp.org/www-project-api-security/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [ISO/IEC 27001:2022](https://www.iso.org/standard/27001)

## 🔍 Getting Started

1. Download all files
2. Verify checksums
3. Read documentation first
4. Open logs in your preferred tool
5. Start investigating!

## ❓ Questions?

Open an issue or email `security-hiring@acme.com`

---

**Good luck with your investigation!** 🔍🕵️