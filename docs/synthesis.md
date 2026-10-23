# Synthesis: CRISPR Target Selection Across Color Blindness Types

> **Date:** 2026-10-22
> **Inputs:** `research/10-deutan.md` … `research/60-crispr-engineering.md`
> **Scope:** in-silico target selection. No wet-lab protocols. Clinical decisions remain with Dr. Walker.

---

## 1. The one-sentence landscape

Red-green color vision deficiency (CVD) — the vast majority of color blindness — is caused mostly
by **structural rearrangements** (5′ hybrid genes, gene deletions) in the highly homologous
`OPN1LW`/`OPN1MW` tandem array at Xq28, with only a minority of cases caused by clean point
mutations; therefore "CRISPR-replace the mutated gene" splits into three genuinely different
design problems depending on the mutation class.

## 2. Mechanism → strategy map

| Disease class | Population | Dominant mechanism | Best-fit edit |
|---|---|---|---|
| Deutan (deuteranopia/anomaly) | ~6% of males | ~61% 5′-hybrid genes, ~32% M-gene deletion (Deeb 1992, n=41) | Prime editing of expressed hybrid's spectral codons back to M identity; CRISPRa of downstream intact OPN1MW; AAV augmentation comparator |
| Protan (protanopia/anomaly) | ~2% of males | 5′L–3′M hybrid replacement; LIAVA splice haplotype (c.532A>G principally responsible) | PE of exon 5 codons 277 (F→Y) + 285 (A→T) in expressed hybrid; splice rescue (CBE/PE) for LIAVA |
| Blue cone monochromacy | ~1/100,000, X-linked | ~40% LCR deletions; ~60% point/hybrid inactivation; **C203R = c.607T>C (TGC→CGC)** most common missense (~42% of deepest-phenotyped cohort) | **CBE: c.607 C→T reversal (CGC→TGC)** — ABE excluded, PE as bystander-free alternative |
| Tritanopia/anomaly | rare/unresolved prevalence, AD | 7 missense alleles + 1 splice-deletion in OPN1SW | G79R via ABE (commonest allele); augmentation fallback |
| Achromatopsia | ~1:30,000, AR | CNGB3 (~40–50%, mostly truncating; c.1148delC founder >70% of alleles), CNGA3 (~25%, mostly missense) | **No CRISPR subproject** — augmentation-watched; 5 phase I/II AAV trials; genes fit single AAV |

## 3. Best targets, ranked

### 🥇 #1 — C203R correction in BCM (`c.607 T>C`, CBE-reversible)
- The only **common, single-base, precisely-editable** lesion in the entire color-vision field.
- Mechanistically clean: CGC→TGC restores Cys-203, the C126–C203 disulfide bond, opsin folding/trafficking.
- Native CBE edit (C→T); no ABE route; PE possible as bystander-free alternative.
- Patient population is narrow (point-mutation subgroup of a 1/100,000 disease) but the biology
  and precedent (C198R mouse rescue, PMC10906232) are the strongest.
- **Recommended primary subproject for the full in-silico guide-design phase.**

### 🥈 #2 — Hybrid-gene exon 5 conversion (codons 277 F→Y, 285 A→T) for protan/deutan
- Addresses the *causal* lesion for the largest population (hybrid genes across deutan+protan).
- Exon 5 carries the decisive L/M determinants — a small, well-understood edit zone.
- Constraint: Y277F is a transversion → outside base-editor scope; **prime editing required**,
  which means dual-AAV delivery with an efficiency penalty (editor >7 kb vs ~4.7 kb AAV limit).
- Allele/array copy-specificity is the hard engineering problem (≥96% identity across up to 5 copies).

### 🥉 #3 — LIAVA splice rescue (exon 3, c.532A>G) for protan/BCM splice-haplotype cases
- Single-base CBE/PE edit fixing an ESE-disrupted splice site (exon 3 skipping → frameshift → NMD).
- Routed by genotyping; shares the same array-specificity challenge as #2.

### Secondary options
- **CRISPRa reactivation of downstream intact OPN1MW copies** (deutan) — no DSB, no DSB-cascade
  risk in post-mitotic cones; proof-of-concept exists for opsin gene reactivation (Becirovic lab,
  rhodopsin→cone-opsin switch in rods). Safest modality, less established.
- **G79R ABE for tritanopia** — clean but very small population; keep as a scoped mini-project.
- **AAV opsin augmentation** — not CRISPR, but the benchmark every design must beat; cDNA (~1.1 kb)
  fits a single AAV with room for a cone promoter (PR1.7 preferred in NHP).

## 4. Engineering constraints that shape all designs (dossier 60)

- **Editor delivery:** base editor + gRNA ≈6 kb, prime editor >7 kb → dual-AAV split-intein with
  ~20–25% co-transduction efficiency, or compact single-AAV editors (SaABE8e class ≤5.0 kb, CasMINI
  ~1.55 kb). PAM scarcity: NGG = 1/16 bp random density vs SaCas9 NNGRRT = 1/256 bp (16× sparser)
  — guide availability must be computed per patient haplotype.
- **No DSBs:** HDR is near-absent in post-mitotic retina; nuclease approaches produce indels +
  AAV integration risk. Base/prime editing mechanistically preferred for every point edit here.
- **Allele specificity in the opsin array:** six demonstrated allele-specific strategies
  (mutation-in-spacer, mutation-creates-PAM, SNP-PAM in cis, truncated guides, paired guides,
  mismatch-sensitive Cas12j-8); all require per-patient long-read/MLPA haplotyping first.
- **Clinical reality check:** the only in-vivo human retinal CRISPR (EDIT-101/BRILLIANCE, CEP290
  LCA10) was safe (14/14 dosed, no Cas9-attributable AEs, 6/14 improved FST) but suspended mid-2024.
- **Cones tolerate dormancy:** achromatopsia trials show dormant cones can be awakened years
  later; BCM cone degeneration is slower in humans than mice — a favorable adult-treatment window.

## 5. Corrections to the original brief (kept for the record)

- The "Ma et al. 2019 Nature knock-in of OPN1LW into Opn1mw in adult mice" reference **does not
  exist** — it conflated Smallwood 2003/Jacobs 2007 transgenic knock-ins, Suzuki 2016 HITI, and
  Ma 2022 AAV augmentation. The real adult-onset proof of trichromacy is **Mancuso et al. 2009,
  Nature 461:784** (AAV L-opsin in adult protanopic squirrel monkeys).
- LIAVA residues are **153/171/174/178/180**, not the residues I initially guessed.
- "OPN1SW C90D" and "CNGB3 c.1572_1573insT/S70" could not be verified in any primary source —
  excluded. Verified tritan catalog: L56P, G79R, T190I, S214P, P264S, R283Q + intron 3 +5delG.
- `c.1148delC` is a **CNGB3** founder variant, not CNGA3.
- No human trial for red-green CVD exists yet; nearest clinic is BGTF-027 (ex-ADVM-062,
  intravitreal L-opsin, phase-1 prep, CHLA).

## 6. Decision

**Primary subproject: BCM C203R cytosine-base-editing design** (best precision/biology fit).
**Parallel subproject: protan/deutan hybrid exon-5 prime-editing design** (largest population,
harder delivery). **Deferred:** achromatopsia (augmentation-watched, re-open triggers in
dossier 50). **Mini-scoped:** tritan G79R ABE.

### Next steps
1. Guide-design feasibility pass on C203R locus: PAM survey (CBE windows), on-target scoring,
   off-target screen against the full OPN1LW/MW array + genome, bystander edit inventory.
2. Same pass for hybrid exon-5 PE targets (requires pegRNA design: RTT + PBS).
3. Medical research paper for the repo (grounded-citations, `paper/`).
