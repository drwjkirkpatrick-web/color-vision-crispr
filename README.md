# color-vision-crispr

Computational research project: design CRISPR-based strategies to correct the genetic defects
behind each major type of color blindness, per disease class. **In-silico literature and design
only** — no wet-lab protocols, no clinical claims. Clinical decisions remain with Dr. Walker.

## Why "replace the mutated gene" is harder than it sounds

The initial literature sweep (2026-10-22) established the core framing:

1. **Red-green color blindness is usually NOT a point mutation.** `OPN1LW` (red opsin) and
   `OPN1MW` (green opsin) sit head-to-tail in a tandem array on Xq28 and are ~96% identical.
   Unequal crossing-over between them produces **hybrid genes** and **deletions** — this causes
   the majority of deutan/protan defects (MedlinePlus; City University review; U. Arizona DCB).
   So the CRISPR design problem is not "fix one wrong base" but one of:
   - (a) **knock-in** of a functional opsin cDNA (the Ma et al. 2019 approach restored
     trichromatic vision in adult dichromatic mice),
   - (b) **exon conversion** — prime-editing the hybrid gene's spectral-tuning codons
     (exons 3–5; positions ~180, 230, 233, 277, 285) back to full L or M sequence,
   - (c) **point correction** where a clean missense exists — most notably **Cys203Arg (C203R)**,
     which kills folding/trafficking of L/M opsins and is the most common inactivating missense
     in blue cone monochromacy and in some hybrids,
   - (d) **CRISPRa reactivation** of intact downstream `OPN1MW` copies (Becirovic-style
     epigenome editing proved the concept in rods).

2. **The LIAVA haplotype** in `OPN1LW` (exon 3 splice-disrupting variants) causes complete loss
   of functional red pigment — a splice-editing target, not a coding edit.

3. **Delivery is the hard constraint.** AAV packages ~4.7 kb; opsin cDNA (~1.1 kb) fits easily
   (hence gene augmentation works preclinically), but prime editors (>6.3 kb) need dual-AAV
   split-intein systems with efficiency penalties. DSB-generating Cas9 is disfavored in
   post-mitotic cones → base/prime editing preferred.

4. **Achromatopsia (CNGA3/CNGB3 etc.) is already in phase I/II AAV augmentation trials** —
   five registered (MeiraGTx/Janssen, AGTC/Beacon, STZ eyetrial). Watching category, not a
   primary CRISPR design target, pending the dossier's verdict.

## Subprojects

| Dossier | Disease class | Gene(s) | Key question |
|---|---|---|---|
| `research/10-deutan.md` | Deuteranopia/anomaly | OPN1MW/OPN1LW array | Hybrid-gene exon conversion vs knock-in vs CRISPRa |
| `research/20-protan.md` | Protanopia/anomaly | OPN1LW | Hybrid conversion, LIAVA splice fix, C203R |
| `research/30-bcm.md` | Blue cone monochromacy | OPN1LW+OPN1MW loss | C203R correction — likely best point-mutation target overall |
| `research/40-tritan.md` | Tritanopia/anomaly | OPN1SW (chr 7) | Rare; catalog mutations, editing feasibility |
| `research/50-achromatopsia.md` | Achromatopsia | CNGA3, CNGB3, GNAT2, PDE6C, PDE6H, ATF6 | Augmentation trials underway; does editing add value? |
| `research/60-crispr-engineering.md` | Shared engineering ref | — | Editor choice, AAV delivery, allele specificity, guide tools |

## State

See `Project_state.md`. Current phase: research (6 dossiers in flight).
Next milestone: `docs/synthesis.md` — pick the best target per subproject and the single
most promising CRISPR strategy overall for a full in-silico guide-design pass.
