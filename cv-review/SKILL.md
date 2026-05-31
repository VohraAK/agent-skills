---
name: cv-review
description: Evaluates CS industrial CVs/resumes against role-specific rubrics for SWE, ML/AI, Data Science, Systems, Security, DevOps/SRE, and NLP roles. Use when user asks to review, evaluate, critique, or improve their CV or resume, or passes a .tex, .txt, .md, or .pdf file for evaluation.
---

# CV Review

## Quick Start

```
/cv-review path/to/cv.tex
/cv-review path/to/resume.pdf
```

Natural language ("review my CV") → ask for file path.

## Workflow

**1. Read CV**
- `.tex` / `.txt` / `.md` → read directly, strip markup
- `.pdf` → run `pdftotext file.pdf -` via Bash; if unavailable, use Read tool
- Warn once for PDFs: formatting analysis limited

**2. Detect experience level**
- Student/new grad: < 1 year total work experience
- Experienced: 1+ years
- Calibrates section order expectations and flagging threshold

**3. Detect niche** from stack, job titles, project descriptions
- Clear signal → proceed
- Two niches compete → ask: *"Your CV shows signals of both [X] and [Y]. Which role are you targeting?"*
- Supported: SWE, ML/AI Engineering, Data Science, Systems, Security, DevOps/SRE, NLP/Research
- See [rubric-niches.md](rubric-niches.md)

**4. Run base rubric** — applies to all niches
- See [rubric-base.md](rubric-base.md)

**5. Run niche rubric**
- See [rubric-niches.md](rubric-niches.md)

**6. Run ATS + structure checks**
- See [ats-guidelines.md](ats-guidelines.md)

**7. Output** (format below)

**8. Offer rewrites** — after output, ask:
*"Want rewrite suggestions for any flagged bullets?"*

## Output Format

```
NICHE: [niche] | LEVEL: [student / experienced]

SECTION VERDICTS
----------------
[Section Name]    Pass / Weak / Fix — one-line reason if not Pass

TOP FIXES
---------
1. [Specific, actionable fix]
2. ...
(max 5 — only issues a recruiter would notice)
```

## Flagging Rules

- Only flag if recruiter would actually stop or skip because of it
- Calibrate to experience level — thin experience on student CV is not a flaw
- Don't flag absent elements not expected for the role or level
- 3 real fixes beat 8 nitpicks
