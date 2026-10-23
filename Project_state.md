# Project State: color-vision-crispr

> **Last updated:** 2026-10-22
> **Current phase:** research
> **Overall health:** green

---

## 1. Goal (1–2 sentences)
Computational research project: design CRISPR-based strategies to correct the genetic defects behind each major type of color blindness, targeting the best-correctable locus per disease class. Purely in-silico literature + design work — no wet-lab protocols.

## 2. Current Status
### Done
- [x] Initial literature sweep (types, genes, mechanisms, editor/delivery constraints)
- [x] Scaffold project structure and subprojects
- [x] Six research dossiers complete (`research/10…60*.md`, ~166 KB, all URL-cited)
- [x] `docs/synthesis.md` — targets ranked: #1 C203R CBE (BCM), #2 hybrid exon-5 PE (protan/deutan), #3 LIAVA splice rescue; achromatopsia deferred (augmentation-watched)
- [x] Medical research paper `paper/color-vision-crispr-review.md` (~3,200 words; verify --evidence exit 0; ledger: 219 sources, 24 cited w/ verbatim quotes)

### In Progress
- (none)

### Not Started
- [ ] Guide-design feasibility pass #1: C203R locus (PAM/CBE window survey, off-targets vs full OPN1LW/MW array, bystanders)
- [ ] Guide-design feasibility pass #2: hybrid exon-5 pegRNA design (RTT+PBS)
- [ ] Decision: primary subproject to develop into actual in-silico guide designs

## 3. Architecture & Key Decisions
| Decision | Rationale | Date |
|---|---|---|
| Research-first phase before any design | Mechanisms dictate strategy: most red-green CVD is structural (hybrid/deletion), not point mutation, so "replace the mutated segment" means knock-in or exon conversion, not simple SNP edit | 2026-10-22 |
| One subproject per disease class | Mutation mechanisms and editability differ completely between classes | 2026-10-22 |

## 4. Blockers & Risks
- **Risk:** Key finding so far — red-green CVD is usually large structural rearrangement, not a clean point mutation → CRISPR "correction" may mean (a) knock-in of functional opsin cDNA, (b) prime-editing hybrid exon 3–5 back to L-spectral sequence, or (c) C203R correction in BCM-like cases.
- **Risk:** AAV packaging limit (~4.7 kb) excludes full prime editors from single vector → dual-AAV split or smaller editors.
- **Risk:** Adult intervention efficacy uncertain (cone degeneration timing in BCM; animal data suggests early treatment matters).

## 5. Next Step (only ONE)
> **Next:** Collect the 6 research dossiers from subagents, then synthesize target recommendations.

## 6. Environment & Tooling Notes
- Language: Python (analysis/design scripts later)
- Guide design tools to evaluate: CRISPOR, CHOPCHOP, Benchling conventions
- Scope: literature + computational design only; clinical decisions remain with Dr. Walker

## 7. Recent Session Log
- 2026-10-22: Project created; initial research sweep; 6 research subagents dispatched.

## 8. References
- Research dossiers: `research/`
- Synthesis: `docs/synthesis.md` (pending)
