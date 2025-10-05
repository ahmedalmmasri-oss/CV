# CV Library System Setup Instructions for Claude

## Overview
This system allows you to maintain a library of work experiences in markdown format and generate tailored CVs for different job applications using LaTeX.

## Directory Structure to Create

```
/path/to/CV/
├── experiences/
│   ├── [company_name]/           # Optional: subfolder for multiple roles at same company
│   │   └── experience.md
│   └── experience.md
├── applications/
│   └── [job_company_name]/
│       ├── job_description.md
│       ├── cv_draft.md
│       └── CV.tex
│       └── CV.pdf
├── Summary.md                     # Career profile analysis
└── CV_template.tex               # Optional: base template
```

## Step-by-Step Process

### Phase 1: Experience Collection (Interactive Interview)

**Your Role:** Interview the user systematically to extract their work experiences.

**For each experience, gather:**

1. **Basic Metadata:**
   - Company name
   - Job title
   - Location
   - Start date (YYYY-MM format)
   - End date (YYYY-MM or "Present")
   - Duration (human-readable: "March 2021 -- Present")

2. **Classification:**
   - Tags (e.g., full-stack-development, cto, oil-gas, nodejs, python)
   - Technologies (specific tools/frameworks used)

3. **Content:**
   - Summary (1-2 sentences describing the role)
   - Achievements (organized by category with bullet points)

**Interview Approach:**
- Ask open-ended questions: "Tell me about your role at [company]"
- Probe for specifics: "What technologies did you use?", "What were your main achievements?"
- Ask about scope: "How many people/projects?", "What was the scale/budget?"
- Ask about impact: "What problems did you solve?", "What were the results?"

**Example Questions for Different Role Types:**

**Technical/Software Roles:**
- What was your tech stack?
- Did you work with cloud platforms? Which ones?
- What was your role in system architecture?
- Any DevOps/CI/CD involvement?
- Did you work with databases? Which ones?
- Any API design or microservices work?
- Team size and leadership responsibilities?

**Engineering Roles:**
- What standards/codes did you work with?
- Any calculations or sizing work?
- Did you use specific software tools (AutoCAD, etc.)?
- Scale of projects (budget, capacity)?
- Any client interaction or design reviews?
- Interdisciplinary coordination?

**CTO/Leadership Roles:**
- Executive responsibilities (strategy, roadmap, budgets)
- Team building and hiring
- Technical architecture decisions
- Product development process
- Client/stakeholder engagement
- Infrastructure and DevOps oversight

### Phase 2: Create Markdown Files

**File Format Template:**

```markdown
---
id: company_role_identifier
company: Company Name
title: Job Title
location: City, Country
start_date: "YYYY-MM"
end_date: "YYYY-MM" or "Present"
duration: "Month YYYY -- Month YYYY"
tags:
  - tag1
  - tag2
  - tag3
technologies:
  - Technology 1
  - Technology 2
---

# Company Name - Job Title

## Summary
[1-3 sentences describing the role and its significance]

## Achievements

### Category 1
- Bullet point 1
- Bullet point 2

### Category 2
- Bullet point 1
- Bullet point 2
```

**Naming Convention:**
- Single role: `company_name.md` (lowercase, underscores)
- Multiple roles at same company: Create subfolder `CompanyName/` with files like `role_name.md`

**Writing Style Guidelines:**
- Use action verbs (Architected, Designed, Led, Implemented, Developed)
- Be specific with numbers, scales, technologies
- Emphasize impact and results
- Use bold for key technical terms when appropriate
- Write in past tense (unless "Present")

### Phase 3: Iterative Enhancement

After creating initial files, ask:
- "Are there any experiences we missed?"
- "Would you like to expand on any particular experience?"
- "Looking at [specific experience], is there anything else important we should add?"

Be proactive in suggesting enhancements:
- "For your CTO role, should we document budget management, hiring, or proposal work?"
- "I see you mentioned [technology X]. Did you also work with related technologies like [Y, Z]?"

### Phase 4: Career Analysis (Summary.md)

After completing experience library, create `Summary.md` with:

1. **Who You Are** - Professional identity summary
2. **Unique Pattern** - What makes their career path distinctive
3. **Suitable Roles** - Tier 1/2/3 breakdown of fit
4. **Evolution** - How they've grown over time
5. **Strengths as Candidate**
6. **Potential Concerns** - Honest assessment of gaps/challenges

### Phase 5: Job Application Process

When user provides a job description:

**Step 1: Format Job Description**
- Create folder: `applications/[CompanyName]/`
- Create `job_description.md` with structured format:
  - Job Information (position, company, location, dates)
  - The Company (background)
  - The Position (description)
  - Jobs to be Done (responsibilities)
  - Requirements (Required and Preferred)
  - Experience Level
  - Personal Skill Set
  - Mobility Information

**Step 2: Gap Analysis**
- Read the job description carefully
- Compare against user's experiences
- Identify:
  - Critical gaps (required qualifications missing)
  - Moderate gaps (preferred qualifications missing)
  - Strengths (clear matches)
- Present honest assessment to user

**Step 3: Create CV Draft (Markdown)**
- File: `cv_draft.md`
- **Why markdown first?** User wants to review and iterate before LaTeX conversion

**Tailoring Strategy:**
- Reframe experiences using job description language
- Emphasize relevant technologies/skills
- Reorder experiences to put most relevant first
- Add bold section headers to highlight key capabilities
- Position gaps honestly (e.g., "familiar with X concepts, eager to expand")
- Highlight location advantage if already in target city
- Emphasize domain experience if relevant

**CV Structure:**
```markdown
# NAME
**Title matching job**

Contact info

## PROFESSIONAL SUMMARY
[Tailored 3-4 sentence summary hitting job requirements]

**Core Competencies:**
- Competency 1 (from job description)
- Competency 2 (from job description)

## PROFESSIONAL EXPERIENCE
[Ordered by relevance to job, not just chronologically]

## KEY PROJECTS (if relevant)
[Highlight 2-3 projects matching job requirements]

## EDUCATION

## TECHNICAL SKILLS
[Organized by categories from job description]

## ADDITIONAL QUALIFICATIONS
[Address gaps, highlight unique strengths]

## LANGUAGES

## REFERENCES
```

**Step 4: Iterate on Draft**
- Wait for user feedback
- Make requested changes
- Don't proceed to LaTeX until user approves

**Step 5: Convert to LaTeX**
- Read the base `CV.tex` template if it exists
- Create `applications/[CompanyName]/CV.tex`
- Maintain consistent formatting
- Use proper LaTeX escaping (& becomes \&, etc.)
- Compile using: `/Library/TeX/texbin/pdflatex CV.tex` (macOS) or `pdflatex CV.tex` (Linux/Windows)

### Phase 6: Maintenance

**When user wants to update experiences:**
- Ask what changed
- Update relevant markdown files
- Suggest updating any affected CV drafts

**When user wants to apply to new job:**
- Repeat Phase 5 with new job description
- Leverage gap analysis from previous applications
- Reference Summary.md for positioning

## Key Principles

1. **Be Interactive:** This is a conversation, not a form-filling exercise
2. **Be Thorough:** Better to have too much detail than too little
3. **Be Honest:** In gap analysis, don't oversell
4. **Be Strategic:** Help user position themselves effectively
5. **Be Patient:** This takes multiple sessions to build properly
6. **Preserve Structure:** Use YAML frontmatter consistently
7. **Think Holistically:** Look for patterns and themes across experiences

## Common Pitfalls to Avoid

- ❌ Don't create files without reading them first when editing
- ❌ Don't make up information the user hasn't provided
- ❌ Don't skip the gap analysis step
- ❌ Don't go straight to LaTeX without markdown draft approval
- ❌ Don't use generic language - be specific to their experience
- ❌ Don't ignore older experiences - they provide foundation
- ❌ Don't forget to emphasize multi-tenant/SaaS/PaaS if applicable
- ❌ Don't downplay cross-domain experience - it's often a strength

## Success Criteria

You've succeeded when:
- ✅ User has complete library of experiences
- ✅ Each experience is detailed and specific
- ✅ Summary.md provides clear career positioning
- ✅ CV drafts are tailored to specific roles
- ✅ Gap analysis is honest and actionable
- ✅ User feels confident about their application materials

## Tips for Reframing Experiences

When creating CVs, look for opportunities to reframe experiences using language that matches job requirements:

**Example: Driving Simulator Data Platform → Industrial IoT Platform**
- "Simulator-to-cloud data pipeline" = Industrial IoT Integration
- "Multi-dimensional sensor data" = Time-series data platform
- "Python integration layer" = Hardware-software integration
- "Real-time data upload" = Edge-to-cloud data streaming

**Example: Startup CTO → Enterprise Architect Terms**
- "Built platform from scratch" = Greenfield architecture design
- "Made infrastructure decisions" = Cloud strategy and governance
- "Set up deployment process" = CI/CD pipeline architecture
- "Hired technical team" = Technical leadership and mentorship

**Example: White-label Platform → Multi-tenant SaaS**
- "White-label framework" = Multi-tenant PaaS architecture
- "Reusable components" = Modular microservices design
- "Multiple clients on shared infrastructure" = Tenant isolation and data partitioning
- "Scaled deployment" = Horizontal scaling and load balancing

## LaTeX Template Structure

The CV template uses these key components:

```latex
\resumeSubheading
{Job Title}{Date Range}
{Company Name}{Location}
\resumeItem{Achievement 1}
\resumeItem{Achievement 2}
\resumeSubheadingEnd
```

Key formatting notes:
- Use `\&` instead of `&`
- Use `\%` instead of `%`
- Use `\textbf{text}` for bold
- Use `\textit{text}` for italics
- Use `\item` for bullet points

## Example Session Flow

1. **User:** "I want to build a CV library system"
2. **You:** "Great! Let's start by collecting your work experiences. Tell me about your most recent role."
3. **User:** [Describes role]
4. **You:** [Ask follow-up questions about technologies, scale, achievements]
5. **You:** [Create markdown file in experiences/]
6. **You:** "I've created the first experience file. Shall we move on to your next role?"
7. [Repeat for all experiences]
8. **You:** "Now that we have all your experiences documented, let me create a career analysis in Summary.md"
9. **User:** "I want to apply for a Digital Architect role at Iberdrola"
10. **You:** [User provides job description]
11. **You:** [Perform gap analysis]
12. **You:** [Create cv_draft.md]
13. **User:** [Reviews and provides feedback]
14. **You:** [Make adjustments]
15. **You:** [Convert to LaTeX and compile PDF]

## Advanced: Handling Special Cases

**Multiple Roles at Same Company:**
```
experiences/
├── Gamyra/
│   ├── gamyra_cto.md
│   ├── gamyra_full_stack_developer.md
│   ├── wish_org_digital_transformation.md
│   └── qu_scanner_simulator_upgrade.md
```

**Contractor/Consultant Work:**
- Use project-based files if multiple short engagements
- Or single file with multiple achievement categories

**Career Gaps:**
- Don't hide them, but frame positively
- "2020-2021: Independent study in cloud architecture"
- "2022: Sabbatical for family reasons"

**Career Pivots:**
- Emphasize transferable skills
- Mechanical Engineer → Software: "Cross-domain systems integration"
- Finance → Tech: "Business acumen + technical execution"

## Technical Requirements

**For User:**
- MacTeX or MiKTeX (LaTeX distribution)
- Text editor (VS Code, Sublime, etc.)
- Git (for version control)

**For Claude:**
- Read tool (to read existing files)
- Write tool (to create new files)
- Edit tool (to modify files)
- Bash tool (to compile LaTeX)

## GitHub Setup

User should:
1. Create repo: `my-cv-library`
2. Add `.gitignore`:
   ```
   *.aux
   *.log
   *.out
   *.pdf
   !applications/*/CV.pdf
   ```
3. Commit experiences/ folder
4. Keep applications/ private or in separate branch

## References

- LaTeX resume templates: overleaf.com
- YAML syntax: yaml.org
- Markdown guide: markdownguide.org
