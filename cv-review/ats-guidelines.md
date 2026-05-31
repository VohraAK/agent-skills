# ATS & Structure Guidelines

## ATS Formatting Rules

Flag:
- Tables or multi-column layouts (common in LaTeX CVs — ATS mangles these)
- Text boxes, headers/footers with content
- Icons or images
- Special characters used as separators that don't parse as plain text
- Non-standard fonts (decorative, symbol-heavy)
- Skills embedded only in graphics or tag clouds

Don't flag:
- Hyperlinks — fine, but text must be readable without them
- Bold/italic — survive most ATS parsers

### LaTeX-specific risks
- `tabular` or `multicol` for layout → flag
- `\textbar{}` as visual separator is fine
- Custom `\newcommand` wrappers — verify rendered text is plain

---

## Section Naming

ATS-safe names → flag bad alternatives:

| Use | Flag |
|-----|------|
| Experience / Work Experience | My Journey, Career Path, Where I've Been |
| Skills / Technical Skills | Toolkit, Superpowers, What I Know |
| Projects | Things I've Built, Side Quests |
| Education | Academic Background, Schooling |
| Summary | About Me, Profile |

---

## Section Order

### Student / New Grad (< 1 year experience)

Expected order:
1. Header (name, contact, GitHub, LinkedIn)
2. Education
3. Experience (internships, research, part-time)
4. Projects
5. Skills

### Experienced (1+ years)

Expected order:
1. Header
2. Summary
3. Experience
4. Projects
5. Skills
6. Education

Flag mismatches with directive: "Move [Section] above [Section]."

---

## Sections to Exclude

Flag if present:
- References ("available on request" wastes space — recruiters know)
- Full street address (city + country is enough)
- Photo (in US/UK/EU contexts)
- Objective statement (outdated — use Summary instead)
- Hobbies (unless directly relevant to the role)
