# Primitive Tech Wiki Project State

## Project Overview
This is a Jekyll-based GitHub Pages wiki documenting prehistoric and early historical technologies. The wiki is deployed to GitHub Pages at `https://<username>.github.io/prehistoric_wiki/`.

## Current Structure

### Wiki Categories (10 main directories)
1. **AGRICULTURE** - 6 pages (index, Early-Agriculture, Crop-Domestication, Maize, Quinoa, Tuber)
2. **Americas** - 3 pages (index, Mesoamerican-Tech, Oceania_Technology)
3. **CLOTHING** - 5 pages (index, Dyeing-Techniques, Fursuits, Woven-Textiles, Bark-Cloth)
4. **INDEX** - 4 pages (INDEX, NAVIGATION, OPEN-QUESTIONS-INDEX, Timeline)
5. **Lithic_Technologies** - 10 pages (index, Stone-Tools, Paleolithic_Stone_Tools, Neolithic_Pottery, Pottery-Techniques, Hammerstone, Spearhead, Axe, Choppers, Choppers-Regional)
6. **MEDICINE** - 7 pages (index, Traditional-Medicine, Traditional-Medicine-Prehistoric, Archaeosurgery, Herbal-Medicine, research-findings-traditional-medicine-full, research-findings-traditional-medicine-prehistoric)
7. **Metallurgy** - 6 pages (index, Bronze_Age_Metallurgy, Copper-Smelting-Sites-and-Techniques, Lost-Wax-Casting, Copper-Trade, Bronze-Age-Archaeology)
8. **Oceania** - 2 pages (index, Polynesian-Navigation)
9. **REGIONAL-MESOAMERICAN** - 5 pages (index, Mesoamerican-Tech, Olmec-Technology, Maya-Technology, Aztec-Technology)
10. **tags** - 1 page (TAGS-MAP.md)

**Total: ~49 markdown pages**

### Configuration & Infrastructure
- **Jekyll** with `kramdown` markdown processor and `rouge` highlighter
- **GitHub Actions** workflow (`.github/workflows/jekyll-gh-pages.yml`) for auto-deploy on push to master
- **Base URL**: `/prehistoric_wiki`
- **Collections** enabled for wiki pages with pretty permalinks
- **Ruby 3.2** with Bundler for dependency management

### Research Progress (from docs/research-progress.md)
**Completed Research Areas:**
- ✅ Paleolithic Stone Tools (Oldowan, Acheulean, Mousterian, Magdalenian)
- ✅ Bronze Age Metallurgy (copper smelting, lost-wax casting, trade networks)
- ✅ Americas & Oceania Technologies (Andean, Melanesian)
- ✅ **Mesoamerican Civilizations** - Resolved → REGIONAL-MESOAMERICAN/
- ✅ **Polynesian Navigation** - Resolved → Oceania/Polynesian-Navigation.md
- ✅ **Traditional Medicine** - Resolved → MEDICINE/
- ✅ **Copper Smelting Sites** - Resolved → Metallurgy/Copper-Smelting-Sites-and-Techniques.md
- ✅ **Pottery Techniques** - Resolved → Lithic_Technologies/
- ✅ **Early Agriculture** - Resolved → AGRICULTURE/

### Task Status (from docs/comprehensive-todo-list.md)

#### Phase 1: Research (6 tasks) - **COMPLETED**
All 6 research tasks completed:
- R1: Mesoamerican Civilizations ✅
- R2: Polynesian Navigation ✅
- R3: Traditional Medicine ✅
- R4: Copper Smelting Sites ✅
- R5: Pottery Techniques ✅
- R6: Early Agriculture ✅

#### Phase 2: Content Creation (21 tasks) - **PARTIALLY COMPLETED**
Pages **already created/existing** (matching the 21 planned):
- Stone Tools (6): Stone-Tools.md, Axe.md, Spearhead.md, Hammerstone.md, Choppers.md, Choppers-Regional.md ✅
- Bronze Age (3): Lost-Wax-Casting.md, Copper-Trade.md, Bronze-Age-Archaeology.md ✅
- Agriculture (4): Crop-Domestication.md, Maize-Agriculture.md, Quinoa-Domestication.md, Tuber-Agriculture.md ✅
- Clothing (4): Fursuits.md, Bark-Cloth.md, Woven-Textiles.md, Dyeing-Techniques.md ✅
- Medicine (4): Traditional-Medicine.md, Archaeosurgery.md, Herbal-Medicine.md, Dental-Care.md ⚠️ (Dental-Care.md missing)
- Regional (4): Americas/Mesoamerican-Tech.md, Oceania/Polynesian-Navigation.md, Europe/Neolithic-Technology.md, Asia/Neolithic-Technology.md ⚠️ (Europe/ and Asia/ directories missing)

**Status**: ~19/21 pages exist. Missing: Dental-Care.md, Europe/Neolithic-Technology.md, Asia/Neolithic-Technology.md

#### Phase 3: Quality Assurance (10 tasks) - **NOT STARTED**
- QA1: Template compliance verification
- QA2: Citation verification
- QA3: Confidence levels
- QA4: Evidence types
- QA5: Tag consistency
- QA6: Internal links
- QA7: Heading hierarchy
- QA8: Review existing pages
- QA9: Tag consistency
- QA10: Final review

#### Phase 4: Organization (8 tasks) - **PARTIALLY COMPLETED**
- Org1: INDEX.md ✅ (exists at wiki/INDEX.md and wiki/index.md)
- Org2: OPEN-QUESTIONS-INDEX.md ✅ (exists at wiki/INDEX/OPEN-QUESTIONS-INDEX.md)
- Org3: Cross-linking review ❌
- Org4: NAVIGATION.md ✅ (exists at wiki/INDEX/NAVIGATION.md)
- Org5: Timeline.md ✅ (exists at wiki/INDEX/Timeline.md)
- Org6: TAGS-MAP.md ✅ (exists at wiki/tags/TAGS-MAP.md)
- Org7: INDEX structure verification ❌
- Org8: Final organization review ❌

### Open Questions (from wiki/OPEN-QUESTIONS.md)
41 open research questions across all categories, organized as links to be resolved.

### Key Files
- **state.md** - This file (project state tracking)
- **docs/comprehensive-todo-list.md** - Full 45-task plan (65-88 hours estimated)
- **docs/research-progress.md** - Research findings log
- **docs/STYLE-GUIDE.md** - Writing/style guidelines
- **docs/TEMPLATE.md** - Page template for new wiki pages
- **_config.yml** - Jekyll configuration
- **.github/workflows/jekyll-gh-pages.yml** - CI/CD pipeline

## Next Steps Priority

### Immediate (High Priority)
1. **Create missing Phase 2 pages**: Dental-Care.md, Europe/Neolithic-Technology.md, Asia/Neolithic-Technology.md
2. **Begin Phase 3 QA**: Verify all pages against TEMPLATE.md structure
3. **Fix cross-linking**: Ensure all `[[Category]/[Technology]]` links resolve correctly

### Medium Priority
4. Complete Phase 4 organization tasks (cross-linking review, final org review)
5. Verify citation format consistency across all pages
6. Apply consistent tags from TAGS-MAP.md taxonomy

### Low Priority
7. Expand research into additional areas (Africa Neolithic, more regional variations)
8. Add academic citations beyond Wikipedia sources

## Git Status
- Current branch: master
- Last commit: 115b2e1 "Fix broken wiki navigation links on GitHub Pages"
- Working directory: Clean (2 modified files per initial status - likely state.md and index.html from local build)

## Deployment
- Auto-deploys to GitHub Pages on push to master
- Uses GitHub Actions with ruby/setup-ruby@v1, bundler-cache
- Build command: `bundle exec jekyll build --no-watch`
- Artifact upload: actions/upload-pages-artifact@v3
- Deploy: actions/deploy-pages@v4