# Writing Style Guide for Primitive Tech Wiki

## 1. Purpose
This guide ensures consistency across all wiki pages, making the knowledge base easy to navigate, cite, and maintain.

---

## 2. Page Structure

Every page must follow this structure (see TEMPLATE.md):

```
# [Category]/[Technology]
---
**Period:** [Period]
**Region(s):** [Region(s)]
**Culture(s):** [Culture(s)]
**Time Range:** [Range]
**Confidence:** [High/Medium/Low/Speculative]
**Evidence Type:** [Material/Ethnographic/Written/Inferred]

## Overview
## History & Development
## Function & Use
## Construction & Technique
## Regional Variations
## Related Technologies
## Sources
## Uncertainties & Research Questions
---
**Tags:** `tag1`, `tag2`, ...
```

---

## 3. Page Naming Conventions

- **Format:** `[Category]/[TechnologyName]`
- **Category Names:** Title Case, e.g., `Lithic Technologies`, `Clothing`
- **Technology Names:** Title Case, e.g., `Choppers`, `Axe`, `Quinoa Domestication`
- **URL Slugs:** Lowercase with hyphens, e.g., `lithic-technologies/choppers`
- **No special characters** except hyphens and numbers
- **No spaces** in slugs

**Examples:**
- ✅ `Lithic Technologies/Choppers` → `lithic-technologies/choppers.md`
- ✅ `Bronze Age/Metallurgy` → `bronze-age/metallurgy.md`
- ❌ `Lithic Technologies/Choppers` with spaces or special chars
- ❌ `Stone Tools/Choppers` (inconsistent naming)

---

## 4. Tag System

### 4.1 Tag Categories

| Category | Examples |
|----------|----------|
| **Period** | `stone-age`, `bronze-age`, `neolithic`, `chalcolithic`, `upper-stone-age`, `lower-stone-age`, `early-bronze-age` |
| **Region** | `europe`, `asia`, `africa`, `americas`, `oceania`, `north-america`, `south-america`, `mesopotamia`, `indus-valley` |
| **Culture** | `indigenous-north-american`, `mesopotamian`, `polynesian`, `andean`, `australian-aboriginal` |
| **Function** | `tool`, `weapon`, `food`, `shelter`, `medicine`, `clothing`, `transport`, `construction`, `symbolic` |
| **Evidence** | `material`, `ethnographic`, `written`, `inferred`, `experimental` |

### 4.2 Tag Usage Rules

1. **Max 15 tags per page**
2. **Required tags:** At least one Period tag and one Function tag
3. **Hierarchy:** Use hierarchical tags (e.g., `region/europe` + `culture/chalcolithic`)
4. **Consistency:** Use the same tag name across all pages (see TAGS.md)
5. **Synonyms:** Merge synonyms (e.g., `axe` and `maul` both under `function/weapon`)

### 4.3 Creating New Tags

1. Check if tag already exists in `/wiki/tags/`
2. If new, add to `/wiki/tags/` with description
3. Update all pages that should use this tag
4. Add to `/docs/TAGS-MAP.md` if needed

---

## 5. Citation Standards

### 5.1 Format

```
[Author(s)] ([Year]). "[Title]." *[Journal/Publisher]*, *Volume*(Issue), pages.
```

**Examples:**
```
[Smith, J. and Jones, R.] (2020). "Lithic technology in the Old Stone Age." *Journal of Archaeology*, 25(3), 112-145.
[Jones, R. and Smith, J.] (2018). "Traditional medicine practices among Indigenous peoples." *World Journal of Ethnopharmacology*, 52, 234-248.
[Smithsonian Institution]. (2021). "Stone Age Tools." *Smithsonian Open Access*.
```

### 5.2 Inline Citations

```
The development of choppers occurred between 300,000 and 200,000 BCE [Smith, 2020].
```

### 5.3 Web Sources

```
[Smithson, J.] (2020). "Lithic Technology." *Smithsonian Open Access*. Retrieved [Date]. URL: [URL]
```

### 5.4 Book Chapters

```
[Smith, J. and Jones, R.] (2020). "Stone Age Technologies." In *The Stone Age: A New Perspective* (Eds. A. B., C. D.). *University Press*, pp. 45-67.
```

---

## 6. Confidence Levels

| Level | Definition | When to Use |
|-------|-----------|-------------|
| **High** | Material evidence, multiple independent sources | Well-documented technologies |
| **Medium** | Single source, or ethnohistoric record | Some evidence but not extensive |
| **Low** | Inferred from related technologies, limited evidence | Limited direct evidence |
| **Speculative** | Hypothesis without direct evidence | Theoretical/reconstructed |

---

## 7. Handling Uncertainty

### 7.1 Notation

```markdown
**Confidence:** Low

### Uncertainties
- The exact origin of [technology] remains debated
  - [Smith, 2020] argues it originated in the Andes
  - [Jones, 2018] proposes a Mediterranean origin
```

### 7.2 Research Question Tags

```markdown
## Open Research Questions
- [[Open Questions]/[Technology-Name-Open-Questions]]
```

### 7.3 Comparison Tables

Use tables to compare regional/cultural variants:

```markdown
## Regional Variations

| Region | Key Features | Confidence |
|--------|-------------|-----------|
| Andean | Terracing technology, quinoa domestication | High |
| Mesoamerican | Maize domestication, chinampas | High |
| North American | Wild rice cultivation, Iroquoian agriculture | Medium |
```

---

## 8. Cross-Linking

### 8.1 Internal Links

```markdown
- [[Category]/[Related1]]
- [[Category]/[Related2]]
```

### 8.2 External Links

```markdown
- [Smithsonian](https://www.si.edu) - Smithsonian Institution
- [JSTOR](https://www.jstor.org) - Academic journal database
- [Project MUSE](https://projectmuse.org) - Academic journal database
```

### 8.3 Link Validation

Every internal link must:
1. Point to an existing page
2. Use the correct `[Category]/[Technology]` format
3. Be verified before each release

---

## 9. Writing Standards

### 9.1 Tone

- **Academic but accessible**
- **Objective and neutral**
- **Evidence-based**
- **Clear and concise**

### 9.2 Language

- **Use present tense for descriptions** ("This tool was used for..." not "This tool was used to be used...")
- **Use past tense for events** ("This technology developed..." not "This technology developed to be developed...")
- **Avoid first person** ("We believe" → "Evidence suggests")
- **Avoid absolute claims** ("This is definitely" → "Current evidence indicates")

### 9.3 Structure

- **Headings:** Use H2 for major sections, H3 for subsections
- **Lists:** Use bullet points for features, numbered lists for sequences
- **Tables:** Use for comparisons and data
- **Images:** Reference with [Figure X](path/to/image) (if using a wiki engine that supports images)

---

## 10. Maintenance

### 10.1 Regular Tasks

- **Weekly:** Add new research notes, update sources
- **Monthly:** Review cross-links, verify citations
- **Quarterly:** Update confidence levels, add uncertainties
- **Annually:** Full review and cleanup

### 10.2 Version Control

- **Branches:** `main`, `feature/category-1`, `feature/category-2`
- **Commits:** `feat: Add page for [Category]/[Technology]`
- **Tags:** `v1.0.0`, `v1.1.0` for releases
- **Wiki directory:** Keep as read-only in main branch

### 10.3 Collaboration

- **Intercom:** Use for session-to-session coordination
- **Todo:** Track multi-step tasks
- **Agent:** Use for research assistance
