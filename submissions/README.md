# 📤 Submission Guidelines

## 📋 Required Deliverables

### 1. Incident Report (PDF)

**Format:** PDF, max 5 pages  
**File name:** `FirstName_LastName_Report.pdf`

**Required Sections:**

#### Section 1: Incident Analysis (2-3 pages)
- Timeline reconstruction (UTC normalized)
- Attack vector identification
- Attack classification (MITRE ATT&CK, OWASP)
- Root cause analysis
- Impact assessment

#### Section 2: Architecture Review (1-2 pages)
- Current architecture weaknesses
- Improved security architecture diagram
- Recommended security controls (with justification)
- Defense-in-depth strategy

#### Section 3: Response & Remediation (1 page)
- Immediate actions (0-24 hours)
- Short-term fixes (1-2 weeks)
- Long-term improvements (1-3 months)
- Compliance considerations

**Formatting:**
- Professional appearance
- Clear structure with headers
- Evidence-based (reference logs)
- No excessive bullet points (use prose)

---

### 2. Video Presentation (MP4)

**Format:** MP4, 10-15 minutes  
**File name:** `FirstName_LastName_Video.mp4` (or link)

**Required Content:**

1. **Introduction (1 min)**
   - Brief self-introduction
   - Incident overview

2. **Attack Walkthrough (4-5 min)**
   - Show timeline
   - Explain attack techniques
   - Demonstrate with log examples
   - Root cause explanation

3. **Architecture Improvements (4-5 min)**
   - Present improved architecture
   - Explain design decisions
   - Walk through security layers

4. **Key Recommendations (2-3 min)**
   - Top 3 immediate actions
   - Long-term strategy summary

5. **Closing (1 min)**
   - Summary of key findings

**Video Guidelines:**
- ✅ Screen recording (no camera required, but welcome)
- ✅ Clear audio (use decent microphone)
- ✅ Readable slides/screen (1080p minimum)
- ✅ Professional background (if on camera)
- ❌ Do NOT upload large video files to GitHub

**Video Hosting:**
- Upload to YouTube (unlisted), Vimeo, or Loom
- Include link in your submission

---

## 🚀 Submission Methods

### Option 1: Pull Request (Public, Recommended)

**Steps:**

1. **Fork this repository**
```bash
   # Click "Fork" button on GitHub
```

2. **Clone your fork**
```bash
   git clone https://github.com/YOUR_USERNAME/acme-security-incident-lab.git
   cd acme-security-incident-lab
```

3. **Create your submission branch**
```bash
   git checkout -b submission/firstname-lastname
```

4. **Create your folder**
```bash
   mkdir submissions/firstname-lastname
   cd submissions/firstname-lastname
```

5. **Add your files**
```
   submissions/firstname-lastname/
   ├── report.pdf
   ├── video_link.md
   └── notes.md (optional)
```

   **video_link.md format:**
```markdown
   # Video Presentation
   
   **Link:** https://youtu.be/xxxxx
   **Duration:** 12 minutes
   **Password:** (if applicable)
```

6. **Commit and push**
```bash
   git add .
   git commit -m "Add submission: FirstName LastName"
   git push origin submission/firstname-lastname
```

7. **Open Pull Request**
   - Go to original repository
   - Click "New Pull Request"
   - Use the provided template

---

### Option 2: Email (Private)

If you prefer privacy:

1. **Package your submission**
```
   FirstName_LastName_Submission.zip
   ├── report.pdf
   ├── video_link.txt (or include video file)
   └── notes.txt (optional)
```

2. **Email to:** `security-hiring@acme.com`
   - Subject: "Security Lab Submission - [Your Name]"
   - Include: Name, Email, LinkedIn (optional)

---

## ⏱️ Timeline

- **No strict deadline** - Submit when ready
- **Expected time:** 4-6 hours total work
- **Evaluation:** Within 1 week of submission
- **Interview:** Selected candidates contacted within 2 weeks

---

## ✅ Submission Checklist

Before submitting, verify:

- [ ] Report is PDF, max 5 pages
- [ ] Video is 10-15 minutes
- [ ] All log files were used in analysis
- [ ] Timeline is timezone-corrected
- [ ] Framework mappings are correct (ISO 27001:2022, NIST, OWASP)
- [ ] Evidence cited for all claims
- [ ] Architecture diagram included
- [ ] Video link works (test in incognito)
- [ ] File names follow convention
- [ ] No plagiarism / proper citations

---

## 🎯 What Happens Next?

1. **Acknowledgment** - We confirm receipt within 24 hours
2. **Evaluation** - Your submission is scored (1 week)
3. **Feedback** - You receive initial feedback
4. **Interview** - Strong candidates invited (top 30%)
5. **Decision** - Final hiring decision (2-3 weeks total)

---

## ❓ Common Questions

**Q: Can I submit before finishing everything?**  
A: No, submit only when both report and video are complete.

**Q: What if my video is 16 minutes?**  
A: 10-15 minutes is a guideline, but don't exceed 20 minutes.

**Q: Can I update my submission?**  
A: Yes, create a new commit before evaluation. We review latest version.

**Q: Will my submission be public?**  
A: Only if you choose Pull Request method. Email submissions are private.

**Q: Can I withdraw my submission?**  
A: Yes, close your PR or email us. We'll delete your materials.

---

## 📧 Contact

- **Technical questions:** Open an [issue](../../issues)
- **Private inquiries:** security-hiring@acme.com
- **Submission problems:** Same email

---

**Ready to submit?** Follow the steps above and good luck! 🚀