# Complete User Guide: CV Library System

## What Is This System?

This is a **smart CV management system** that helps you:
1. Store all your work experiences once in organized markdown files
2. Generate customized CVs for different job applications
3. Reuse and remix your experiences without rewriting them
4. Keep everything version-controlled and organized

Think of it as a **CV factory** - you build your experience library once, then use it to manufacture tailored CVs on demand.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Understanding the Folder Structure](#understanding-the-folder-structure)
3. [Step-by-Step: Building Your Experience Library](#step-by-step-building-your-experience-library)
4. [How to Apply for a Job](#how-to-apply-for-a-job)
5. [Working with Claude](#working-with-claude)
6. [Technical Setup](#technical-setup)
7. [Tips & Best Practices](#tips--best-practices)
8. [Troubleshooting](#troubleshooting)

---

## Getting Started

### What You Need

**Software:**
- A LaTeX distribution (for PDF generation):
  - **Windows:** [MiKTeX](https://miktex.org/download)
  - **Mac:** [MacTeX](https://www.tug.org/mactex/)
  - **Linux:** `sudo apt-get install texlive-full`
- A text editor (VS Code, Notepad++, or any editor)
- Git (optional, for version control)
- Claude AI access (to help manage the system)

**Time Investment:**
- Initial setup: 2-4 hours to document all experiences
- Per job application: 30-60 minutes for a tailored CV

### The Big Picture

Here's how the system works:

```
┌─────────────────────────────────────────────────────────────┐
│ STEP 1: Build Your Experience Library (ONE TIME)           │
│ Talk to Claude → Create markdown files for each job/project│
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│ STEP 2: Get Your Career Analysis (ONE TIME)                │
│ Claude analyzes your experiences → Creates Summary.md      │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│ STEP 3: Apply for Jobs (REPEAT FOR EACH APPLICATION)       │
│ Give Claude job description → Get tailored CV draft → PDF  │
└─────────────────────────────────────────────────────────────┘
```

---

## Understanding the Folder Structure

Your CV system will look like this:

```
CV-master/
│
├── experiences/                    # Your experience library (build once, use forever)
│   ├── CompanyA/                  # If you had multiple roles at one company
│   │   ├── role1.md
│   │   └── role2.md
│   ├── company_b.md               # Single role = single file
│   └── company_c.md
│
├── applications/                   # One folder per job you apply to
│   ├── company_x_job_title/
│   │   ├── job_description.md     # The job posting (formatted)
│   │   ├── cv_draft.md            # Markdown draft (review this first)
│   │   ├── CV.tex                 # LaTeX source (generated from draft)
│   │   └── CV.pdf                 # Final PDF (compiled from .tex)
│   │
│   └── company_y_job_title/
│       └── [same files as above]
│
├── Summary.md                      # Career analysis (who you are, best roles)
├── Summary_new.md                  # Updated analysis (if career evolves)
├── CV_template.tex                 # Base LaTeX template
└── INSTRUCTIONS_FOR_CLAUDE.md      # Instructions for Claude (you can read this too!)
```

**Key Points:**
- **experiences/** = Your permanent library (rarely changes)
- **applications/** = Job-specific CVs (created on demand)
- **Summary.md** = Your career "cheat sheet" for positioning

---

## Step-by-Step: Building Your Experience Library

This is the foundation. Do this ONCE, and you'll reuse it forever.

### Step 1: Start a Conversation with Claude

Say something like:

> "I want to build a CV library system. Let's start collecting my work experiences."

Claude will guide you through an interview process.

### Step 2: Answer Claude's Questions

Claude will ask about each job/role you've had. Be prepared to discuss:

**Basic Info:**
- Company name
- Your job title
- Location
- Dates (start and end)

**Technical Details:**
- What technologies/tools did you use?
- What software, platforms, frameworks?
- Any certifications or standards you worked with?

**Achievements & Impact:**
- What problems did you solve?
- What were the results? (numbers are gold!)
- How many people/projects/dollars were involved?
- What made this role special or challenging?

### Step 3: Review the Markdown Files

After each experience, Claude will create a file like this:

```markdown
---
id: gamyra_project_engineer
company: Gamyra
title: Project Engineer
location: Doha, Qatar
start_date: "2022-01"
end_date: "2024-12"
duration: "January 2022 -- December 2024"
tags:
  - program-management
  - education
  - vr-technology
technologies:
  - VR Systems
  - Monday.com
  - Event Management
---

# Gamyra - Project Engineer

## Summary
Managed Qatar's first immersive educational VR program engaging 3,741
participants. Coordinated 6 major sponsors and achieved 63% cost reduction
through logistics optimization.

## Achievements

### Program Management
- Managed program engaging **3,741 participants** over 3 years
- Coordinated **6 oil & gas sponsors** (QatarGas, Qatar Energy, etc.)
- Achieved **63% cost reduction** in logistics (4,560 → 1,680 QAR per move)

### Event Operations
- Transformed program into Qatar Toy Festival 2024's most popular activity
- Standardized processes using Monday.com
- Hired and trained operators
```

**What to Check:**
- ✅ Dates are correct
- ✅ Technologies/tools are complete
- ✅ Numbers are accurate
- ✅ Nothing important is missing

### Step 4: Iterate Until Complete

Claude will ask:
- "Are there any experiences we missed?"
- "Should we expand on anything?"

Keep going until all your jobs, internships, major projects, and volunteer work are documented.

### Step 5: Get Your Career Analysis

Once all experiences are documented, Claude will create **Summary.md** with:

1. **Who You Are** - Your professional identity
2. **Your Unique Pattern** - What makes your career special
3. **Suitable Roles** - What jobs are best for you (Tier 1/2/3)
4. **Your Evolution** - How you've grown
5. **Strengths as Candidate** - What you bring to the table
6. **Potential Concerns** - Honest gaps/challenges
7. **Recommendations** - Next steps for your career

**This file is gold!** Read it carefully. It's your positioning guide for job applications.

---

## How to Apply for a Job

Now that your library is built, applying for jobs is fast and systematic.

### Step 1: Find a Job You Want

Copy the entire job description (company info, requirements, responsibilities, etc.)

### Step 2: Give It to Claude

Say:

> "I want to apply for [Job Title] at [Company]. Here's the job description: [paste]"

### Step 3: Claude Creates Job Folder

Claude will create:

```
applications/company_name_job_title/
├── job_description.md    # Formatted version of the posting
```

The job description will be structured with sections like:
- Job Information
- The Company
- The Position
- Responsibilities
- Required Skills
- Preferred Skills

### Step 4: Gap Analysis

Claude will analyze:
- ✅ **Strengths:** Where you match perfectly
- ⚠️ **Moderate Gaps:** Preferred skills you lack
- ❌ **Critical Gaps:** Required skills you don't have

**This is honest feedback.** Claude won't sugarcoat it. If the job is a bad fit, you'll know.

### Step 5: Review the CV Draft (Markdown)

Claude will create **cv_draft.md** - a tailored CV in markdown format.

**Why markdown first?**
- Easy to read and edit
- Fast to iterate
- No LaTeX compilation needed yet

The draft will:
- Reframe your experiences using the job's language
- Emphasize relevant skills/technologies
- Reorder experiences (most relevant first, not just chronological)
- Include a professional summary targeting the role
- Address gaps honestly

**IMPORTANT:** Review this carefully! Give feedback:
- "Add more emphasis on [skill X]"
- "Reword the summary to highlight [Y]"
- "Remove [project Z], it's not relevant"

### Step 6: Iterate Until Perfect

Go back and forth with Claude until the markdown draft is exactly what you want.

**Don't skip this step!** LaTeX compilation takes time. Get the content right first.

### Step 7: Convert to LaTeX & PDF

Once you approve the markdown draft, say:

> "This looks great. Let's convert it to PDF."

Claude will:
1. Read the base template (`CV_template.tex`)
2. Create `CV.tex` with your content
3. Compile to `CV.pdf` using pdflatex

**On Windows:** Claude will run:
```bash
pdflatex CV.tex
```

**On Mac:** Claude will run:
```bash
/Library/TeX/texbin/pdflatex CV.tex
```

### Step 8: Download Your PDF

Your final CV is ready! Find it at:
```
applications/company_name_job_title/CV.pdf
```

---

## Working with Claude

### Starting a New Session

Claude doesn't remember previous conversations, so you need to give context:

**First time using the system:**
> "I want to build a CV library system. Let's start by collecting my work experiences."

**Applying for a new job:**
> "I want to apply for [Job Title] at [Company]. My experience library is in the 'experiences/' folder, and my career analysis is in 'Summary.md'. Here's the job description: [paste]"

**Updating an experience:**
> "I want to update my experience at [Company] to add [new achievement]. The file is at experiences/company/role.md"

### What Claude Can Do

✅ Interview you to extract work experiences
✅ Create/edit markdown experience files
✅ Analyze your career and create Summary.md
✅ Format job descriptions
✅ Perform gap analysis (you vs. job requirements)
✅ Create tailored CV drafts in markdown
✅ Convert markdown to LaTeX
✅ Compile LaTeX to PDF
✅ Suggest improvements and positioning strategies

### What Claude Won't Do

❌ Make up achievements or experiences
❌ Lie about your qualifications
❌ Skip the gap analysis
❌ Compile PDFs before you approve the markdown draft

---

## Technical Setup

### Installing LaTeX

**Windows (MiKTeX):**
1. Download from https://miktex.org/download
2. Run installer
3. Choose "Install missing packages on-the-fly: Yes"
4. Add to PATH during installation

**Mac (MacTeX):**
1. Download from https://www.tug.org/mactex/
2. Run installer (large download, ~4GB)
3. Wait for installation to complete
4. LaTeX will be available at `/Library/TeX/texbin/pdflatex`

**Linux:**
```bash
sudo apt-get update
sudo apt-get install texlive-full
```

### Verifying LaTeX Installation

Open a terminal/command prompt and run:

```bash
pdflatex --version
```

You should see version information. If not, LaTeX isn't installed correctly.

### Folder Setup

Create your main folder:

```bash
mkdir CV-master
cd CV-master
```

Create subfolders:

```bash
mkdir experiences
mkdir applications
```

Copy the template file (`CV_template.tex`) into the root folder.

### Optional: Git Version Control

Track your CV history:

```bash
cd CV-master
git init
git add .
git commit -m "Initial CV library setup"
```

Create `.gitignore`:

```
*.aux
*.log
*.out
*.synctex.gz
```

This prevents LaTeX temporary files from being tracked.

---

## Tips & Best Practices

### Building Your Experience Library

**Be Specific:**
- ❌ "Worked on projects"
- ✅ "Led development of 6km 3D road environment for university research"

**Use Numbers:**
- ❌ "Managed large program"
- ✅ "Managed program engaging 3,741 participants over 3 years"

**Include Technologies:**
- List every tool, language, platform, software you used
- These become searchable keywords for recruiters

**Organize by Impact:**
- Problem → What You Did → Impact
- This makes it easy to tailor later

### Applying for Jobs

**Read the Job Description Carefully:**
- Highlight keywords and required skills
- Note the tone and language they use

**Trust the Gap Analysis:**
- If Claude says there are critical gaps, listen
- Better to know upfront than waste time

**Customize, Don't Just Copy:**
- Each CV should feel written specifically for that job
- Reorder experiences based on relevance
- Use the company's language

**Ask Claude for Help:**
- "How should I position my [X experience] for this [Y role]?"
- "What's the best way to address this gap in [skill Z]?"

### Maintaining Your Library

**Update After Major Projects:**
- Add new achievements as they happen
- Don't wait until job hunting season

**Review Annually:**
- Refresh Summary.md as your career evolves
- Add new skills/technologies you've learned

**Keep It Organized:**
- Use consistent naming conventions
- One company folder if you had 3+ roles there
- Single files for single roles

---

## Troubleshooting

### "pdflatex not found"

**Problem:** LaTeX isn't installed or not in PATH.

**Solution:**
- Re-install LaTeX
- On Windows, manually add MiKTeX to PATH
- On Mac, use full path: `/Library/TeX/texbin/pdflatex CV.tex`

### "LaTeX compilation failed"

**Problem:** Syntax error in the .tex file (usually special characters).

**Common fixes:**
- `&` should be `\&`
- `%` should be `\%`
- `_` in text should be `\_`
- `$` should be `\$`

Ask Claude to fix the LaTeX escaping.

### "Claude doesn't remember my previous work"

**Problem:** Claude doesn't retain memory between sessions.

**Solution:**
Always provide context:
> "My experience library is in the 'experiences/' folder. I want to apply for [job]."

### "My CV is too long"

**Problem:** Trying to include everything.

**Solution:**
- For each job, only include the most relevant 3-5 experiences
- Focus on quality over quantity
- Ask Claude: "This is too long. What should we cut for this specific role?"

### "I need to update an experience file"

**Solution:**
> "I want to update experiences/company/role.md to add [new achievement]. Please read the file first, then add this to the [section name] section."

### "How do I choose which experiences to include?"

**Solution:**
Ask Claude to analyze:
> "I'm applying for [job title]. Which of my experiences from the library are most relevant? Should we include [X] or skip it?"

---

## Real-World Example Walkthrough

Let's walk through a complete example.

### Scenario

You're applying for a **Program Manager** role at **Qatar Foundation**.

### Step 1: Give Claude the Job Description

> "I want to apply for Program Manager at Qatar Foundation. Here's the job description: [paste full JD]"

### Step 2: Claude Creates Job Folder

```
applications/qatar_foundation_program_manager/
└── job_description.md
```

### Step 3: Gap Analysis

Claude analyzes and reports:

**Strengths:**
- ✅ 8 years of program management experience
- ✅ Managed programs with 3,741 participants
- ✅ Government relations experience in Qatar
- ✅ Multi-stakeholder coordination (6 sponsors)
- ✅ Budget management (63% cost reduction)

**Moderate Gaps:**
- ⚠️ PMP certification (preferred but not required)
- ⚠️ Experience with teams of 20+ people

**Critical Gaps:**
- ❌ None

**Verdict:** Excellent fit. Should apply.

### Step 4: Review CV Draft

Claude creates `cv_draft.md` with:

**Professional Summary:**
> "Program Manager with 8+ years delivering complex multi-stakeholder initiatives in Qatar's education and government sectors. Proven track record managing programs engaging 3,741+ participants, coordinating 6 major sponsors, and achieving 63% cost reductions. Expert in stakeholder management, government relations, and educational program delivery."

**Experience Ordering:**
1. **Most relevant first:** Magic Carpet Program (matches the role)
2. **Second:** QF Driving Club (it's Qatar Foundation!)
3. **Third:** Other project management roles
4. **Last:** Technical internship (less relevant, but shows growth)

**Highlighted Skills:**
- Multi-stakeholder coordination
- Budget optimization
- Government relations
- Educational program delivery

### Step 5: You Give Feedback

> "This looks great! Can you add more emphasis on the QF relationship in the Driving Club section? That's directly relevant."

Claude updates the draft.

### Step 6: Approval & Compilation

> "Perfect! Let's convert to PDF."

Claude creates `CV.tex` and compiles to `CV.pdf`.

### Step 7: Result

You have a tailored CV that:
- Speaks Qatar Foundation's language
- Emphasizes your QF experience
- Highlights program management achievements
- Shows measurable impact (numbers)
- Addresses their requirements directly

**Time spent:** 45 minutes (vs. 3+ hours writing from scratch)

---

## Advanced Tips

### Handling Multiple Roles at One Company

If you worked at **Gamyra** for 8 years with different titles:

```
experiences/
└── Gamyra/
    ├── development_engineer_intern.md
    ├── project_engineer.md
    ├── program_manager.md
    └── office_manager.md
```

Each file documents one distinct role, even at the same company.

### Creating "Project" Experience Files

Sometimes you want to highlight specific projects, not just job titles:

```
experiences/
└── Gamyra/
    ├── magic_carpet_program.md        # Major project
    ├── qf_driving_club.md             # Another major project
    ├── stiscan_simulator.md           # Client project
    └── web_summit_2024.md             # Event/networking
```

This gives you granular control when tailoring CVs.

### Using Tags for Smart Filtering

In your markdown files, use tags wisely:

```yaml
tags:
  - program-management
  - education
  - government-relations
  - vr-technology
  - budget-optimization
  - stakeholder-management
```

Later, you can ask Claude:
> "For this job, only include experiences tagged with 'program-management' or 'education'."

### Creating Role-Specific Templates

If you apply to similar roles often (e.g., always "Project Engineer"), save a base CV:

```
applications/
└── _templates/
    └── project_engineer_base.md
```

Then ask Claude:
> "Use the project engineer template as a starting point, but customize for this specific company."

---

## Maintenance Schedule

### Weekly
- ❌ Nothing (unless actively job hunting)

### Monthly
- ✅ Review recent achievements at current job
- ✅ Add new projects/accomplishments to your experience file

### Quarterly
- ✅ Update technical skills list
- ✅ Add any new certifications or training

### Annually
- ✅ Review and update Summary.md
- ✅ Archive old application folders you no longer need
- ✅ Refresh CV_template.tex if design feels dated

---

## Quick Reference Commands

### For Claude

**Start building library:**
> "I want to build a CV library system. Let's collect my work experiences."

**Apply for a job:**
> "I want to apply for [Job Title] at [Company]. My experiences are in the 'experiences/' folder. Here's the job description: [paste]"

**Update an experience:**
> "Update experiences/[company]/[role].md to add [achievement] in the [section] section."

**Compile PDF:**
> "Compile the CV to PDF."

**Get positioning advice:**
> "Based on my Summary.md, how should I position myself for this [role type]?"

### For Terminal/Command Prompt

**Compile LaTeX manually:**
```bash
cd applications/company_job_title/
pdflatex CV.tex
```

**Clean up LaTeX temp files:**
```bash
rm *.aux *.log *.out
```

**Check folder structure:**
```bash
ls -R
```

---

## Getting Help

### From Claude

Claude is your co-pilot. Ask questions like:

- "Is this experience relevant for this job?"
- "How should I reframe my [X] experience for a [Y] role?"
- "What are my strongest achievements for program management roles?"
- "Am I missing anything in this CV draft?"
- "Which experiences should I cut to keep the CV to 2 pages?"

### From the System Files

- **INSTRUCTIONS_FOR_CLAUDE.md** - Technical reference (you can read too)
- **Summary.md** - Your career positioning guide
- **cv_draft.md** - Preview before PDF compilation

### Common Questions

**Q: How many experiences should I include per CV?**
A: 4-7 experiences, each with 3-5 bullet points. Quality over quantity.

**Q: Should I include old internships?**
A: Only if relevant or if you're early career. If you have 10+ years experience, probably skip.

**Q: Can I use the same CV for multiple jobs?**
A: You *can*, but you *shouldn't*. Tailoring increases your chances significantly.

**Q: How often should I update my library?**
A: Add major achievements as they happen. Full review once a year.

**Q: What if I made a mistake in an experience file?**
A: Just ask Claude to update it. The library is living documentation.

---

## Final Checklist

Before you start job hunting, make sure:

- ✅ LaTeX is installed and working (`pdflatex --version`)
- ✅ All your work experiences are documented in `experiences/`
- ✅ Each experience file has accurate dates, technologies, and achievements
- ✅ You have a `Summary.md` with your career analysis
- ✅ You understand the folder structure
- ✅ You know how to start a conversation with Claude

**You're ready!** The system is designed to save you hours per application while producing better, more tailored CVs.

---

## Appendix: Markdown Syntax Reference

Your experience files use **Markdown** - a simple text formatting language.

### Headings
```markdown
# Heading 1 (largest)
## Heading 2
### Heading 3
```

### Bold & Italics
```markdown
**bold text**
*italic text*
```

### Bullet Points
```markdown
- Item 1
- Item 2
  - Sub-item 2.1
  - Sub-item 2.2
```

### Links
```markdown
[Link text](https://example.com)
```

### Code/Technical Terms
```markdown
Use `backticks` for inline code or technical terms
```

That's all you need! Markdown is intentionally simple.

---

## Appendix: YAML Frontmatter Reference

The top of each experience file has **YAML frontmatter** (between the `---` lines):

```yaml
---
id: unique_identifier
company: Company Name
title: Your Job Title
location: City, Country
start_date: "2022-01"
end_date: "2024-12"
duration: "January 2022 -- December 2024"
tags:
  - tag1
  - tag2
technologies:
  - Tech 1
  - Tech 2
---
```

**Important rules:**
- Dates use quotes: `"2022-01"`
- Lists use hyphens with 2-space indent
- No tabs, only spaces
- Keep the `---` separators

---

## You're All Set!

This system will save you **hours per job application** while producing **higher quality, better-targeted CVs**.

The key is:
1. **Build your library once** (invest the time upfront)
2. **Maintain it regularly** (add achievements as they happen)
3. **Let Claude do the heavy lifting** (tailoring, formatting, compilation)

**Good luck with your job hunt!** 🚀

---

*Last updated: October 2025*
*System version: 2.0*
