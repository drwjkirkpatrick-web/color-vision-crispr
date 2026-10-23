# 40 — Tritanopia / Tritanomaly (S-cone, OPN1SW)

Subproject dossier for the color-vision CRISPR project. In-silico literature/design only — no wet-lab protocols.
Compiled 2026-10-22. **Honesty note up front:** this is by far the smallest and thinnest subproject. OPN1SW disease literature spans ~30 years but consists of a handful of family reports; there is no gene-therapy, editing, or disease-mutation animal-model work on tritanopia specifically, and ClinVar carries only 3 pathogenic variants. Much of what follows leans on the closest analog (M/L opsin disease, blue cone monochromacy) rather than on tritanopia data itself.

---

## 1. Disease overview

- **Tritanopia** = complete loss of S-cone (short-wavelength, "blue") function → can't distinguish blue/green, yellow from violet/pink; **tritanomaly** = partial S-cone dysfunction, sometimes described as a phenotypic variation of tritanopia. Both map to the same gene ([MedlinePlus OPN1SW](https://medlineplus.gov/genetics/gene/opn1sw/); [Cone Contrast Test review, PMC12072747](https://pmc.ncbi.nlm.nih.gov/articles/PMC12072747/)).
- **Inheritance: autosomal dominant, 7q32.1 (OPN1SW), MIM 190900**, with *incomplete penetrance* and *progression* — tritan defects can take decades to progress from mild to moderate, and normal trichromatic childhood vision gradually succumbs as S cones slowly die ([OMIM 190900](https://omim.org/entry/190900); [Cells 2026 review, PMC13297016](https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/)).
- **Chromosome 7 gene:** OPN1SW ("opsin 1, short-wave-sensitive", blue cone pigment) is the only cone opsin on an autosome; L/M opsins are on Xq28 ([OMIM 613522](https://omim.org/entry/613522); [Clin Exp Ophthalmol 2025, PMC11962696](https://pmc.ncbi.nlm.nih.gov/articles/PMC11962696/)).
- **Extreme rarity — estimates conflict:** older estimate 1 in 13,000–1 in 65,000; a newer estimate puts combined tritanopia+tritanomaly at up to 1 in 500 in European populations; congenital tritan defects specifically estimated at ~0.008% (most "tritan" defects clinically are acquired, e.g. from optic-nerve disease) ([Eye 2009 review, Simunovic & Moore](https://www.nature.com/articles/eye2009251); [PMC12072747](https://pmc.ncbi.nlm.nih.gov/articles/PMC12072747/)). MedGen/OMIM emphasize it affects males and females equally ([MedGen C0155017](https://www.ncbi.nlm.nih.gov/medgen/C0155017/)). **Best working prevalence: ~1 in 500 (all tritan defects, possibly progressive/acquired-mixed) down to 1 in 13,000–65,000 for frank congenital tritanopia** — flag as unresolved.
- Visual acuity is typically **normal**, because the foveal center contains no S cones even in healthy people — a key therapeutic point (see §3) ([PMC11962696](https://pmc.ncbi.nlm.nih.gov/articles/PMC11962696/); [PMC11538286](https://pmc.ncbi.nlm.nih.gov/articles/PMC11538286/)).
- Adaptive-optics imaging of a tritan family (R283Q) showed **actual S-cone dystrophy** — reduced S-cone density and disrupted mosaic, i.e. the disease is degenerative, not purely functional ([Baraas et al. 2007, J Opt Soc Am A; ref list in PMC3516400](https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/); [PMC13297016](https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/)).

## 2. Molecular genetics — the documented OPN1SW catalog

### 2.1 Pathogenic variants (the real list)

Literature consensus (Baraas et al. 2019: "there are six known mutations"): **six missense variants + one splice variant**.

| Variant | cDNA (ClinVar / OMIM) | Codon (verified against NM_001708 / NP_001699) | Domain | Type | First report |
|---|---|---|---|---|---|
| **L56P** | c.167T>C | WT CTG (L) → CCG (P) | — | missense | Gunther, Neitz & Neitz 2006 (via [PMC3516400](https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/)) |
| **G79R** | c.235G>A (ClinVar, rs104894031) | WT GGA (G) → AGA (R) | TM2 | missense | Weitz et al. 1992a ([OMIM 190900](https://omim.org/entry/190900)) |
| **T190I** | c.568G>A | WT ACC (T) → ATC (I) | extracellular loop II | missense | [Baraas et al. 2012, Vision Res, PMC3516400](https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/) |
| **S214P** | c.640T>C (ClinVar, rs104894032) | WT TCC (S) → CCC (P) | TM5 | missense | Weitz et al. 1992a ([OMIM 190900](https://omim.org/entry/190900)) |
| **P264S** | c.790C>T (ClinVar, rs104894033) | WT CCC (P) → TCC (S) | conserved Pro of GPCR family (NPxxY vicinity) — "may perturb folding, stability, or transport" | missense | Weitz et al. 1992b ([OMIM 190900](https://omim.org/entry/190900)) |
| **R283Q** | c.848G>A | WT CGG (R) → CAG (Q) | cytoplasmic | missense | [Baraas et al. 2007 (S-cone dystrophy family)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/) |
| **Exon 3 +5G del** | intron 3 +5delG | — | 5′ splice site of intron 3 → exon 2+3 skipping → frameshift fs119_X133, **truncation-equivalent (nonfunctional mRNA)** | splice/truncation | [Baraas et al. 2019, IOVS, PMC7254067](https://pmc.ncbi.nlm.nih.gov/articles/PMC7254067/) |

\* Codons and reference bases verified computationally against NM_001708.2 / NP_001699.1 (NCBI EFetch, 2026-10-22): G79=GGA, S214=TCC, P264=CCC, L56=CTG, T190=ACC, R283=CGG; ClinVar cDNA notations c.235G>A, c.640T>C, c.790C>T are consistent with this transcript.

- **ClinVar coverage is thin:** only **3 pathogenic missense variants** (G79R, S214P, P264S) are in ClinVar for tritanopia, plus a benign Gly119= (rs1799922) and a VUS Arg58His ([Malacards tritanopia, mirroring ClinVar](https://www.malacards.org/card/tritanopia)). L56P, T190I, R283Q and the splice variant are literature-only. The splice-site deletion allele has an estimated population minor-allele frequency of 0.132% ([PMC7254067](https://pmc.ncbi.nlm.nih.gov/articles/PMC7254067/)) — an order of magnitude commoner than any other tritan allele, and the best candidate for the "1 in 500" end of the prevalence range.
- **Mutation hints checked and rejected:** the parent task's hints "C90D" and "Pro79" are **not found** in OMIM, ClinVar, or PubMed literature as OPN1SW pathogenic variants (searched 2026-10-22); the closest real variants are G79R (Gly79→Arg) and P264S. Treat "C90D" as nonexistent for design purposes.
- Incomplete penetrance is documented (Weitz 1992; OMIM), and genotype–phenotype severity varies: T190I = "mild tritanopia"; splice variant = mild (haploinsufficiency); P264S = more severe ([PMC3516400](https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/); [PMC7254067](https://pmc.ncbi.nlm.nih.gov/articles/PMC7254067/)).

### 2.2 Mechanism

- **Dominant-negative / toxic-misfolding is proposed for missense alleles:** Weitz et al. reasoned that dominant inheritance implies "the aberrant gene products actively interfere with the viability or fidelity of blue-sensitive cone photoreceptors" ([OMIM 190900](https://omim.org/entry/190900)); P264S hits a proline conserved across all GPCRs (folding/stability/transport) ([OMIM 190900](https://omim.org/entry/190900)); G79R in TM2 is argued to disrupt "folding, processing, or stability" ([RP+EYS case report, PMC7057104](https://pmc.ncbi.nlm.nih.gov/articles/PMC7057104/)).
- **Direct evidence for tritan mutants is essentially absent**: I found **no in vitro expression/trafficking study of any human tritan OPN1SW missense mutant** in cells or retina — a genuine data gap (see §7). The mechanistic picture is borrowed by analogy from L/M opsins: the **C203R** M-opsin missense is a folding/trafficking defect that prevents outer-segment localization and kills cone outer segments, rescued by providing normal opsin ([JCI Insight 2023, C203R rescue](https://insight.jci.org/articles/view/172834)); and an engineered S-opsin knock-in mouse (F81Y) shows that misfolded S-opsin reduces outer-segment trafficking ~1.6–2.2-fold while cones stay viable ([Insinna 2012, PMC3381355](https://pmc.ncbi.nlm.nih.gov/articles/PMC3381355/)) — i.e., S-opsin folding/trafficking defects *can* behave this way.
- **The one mechanistically proven tritan allele is haploinsufficiency:** the exon 3 +5delG splice mutant produces an exon-2/3-skipped, PTC-containing transcript; heterozygotes have ~half normal S-opsin and mild tritan defects — "the mechanism … must be haploinsufficiency" ([PMC7254067](https://pmc.ncbi.nlm.nih.gov/articles/PMC7254067/)).
- MedlinePlus concurs that S cones without functional opsin "die prematurely or cannot transmit visual signals" ([MedlinePlus OPN1SW](https://medlineplus.gov/genetics/gene/opn1sw/)).

## 3. State of the art

### 3.1 Direct tritanopia therapy: none

- **No gene therapy, gene editing, or clinical trial targets OPN1SW/tritanopia.** The 2025 Clinical & Experimental Ophthalmology trial table of phototransduction-gene programs (CNGA3, CNGB3, GUCY2D, PDE6A/B, CNGA1…) contains **no OPN1SW entry** ([PMC11962696](https://pmc.ncbi.nlm.nih.gov/articles/PMC11962696/)); targeted searches of the literature for OPN1SW gene therapy/editing returned nothing disease-specific. **This is the documented gap this subproject sits in.**
- **Nearest analog 1 — opsin gene augmentation in opsin-null cone mouse models (works):** AAV5-PR2.1-human-OPN1LW subretinally in Opn1mw⁻/⁻Opn1sw⁻/⁻ mice regenerates cone outer segments and rescues photopic ERG when delivered ≤2 months of age (rescue lasts ≥8 months; efficacy collapses at 5–7 months) ([Ma et al. 2022, Hum Gene Ther, PMC9347391](https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/)); same in an all-cone (Nrl⁻/⁻) background ([PMC13182793](https://pmc.ncbi.nlm.nih.gov/articles/PMC13182793/)); M-opsin AAV rescues M-cone function in Opn1mw⁻/⁻ mice ([Deng et al. 2018, Sci Rep, PMC5532293](https://www.nature.com/articles/s41598-017-06982-7)); augmentation rescues the C203R missense-folding model ([JCI Insight 2023](https://insight.jci.org/articles/view/172834)). Review: [Blue Cone Monochromacy and Gene Therapy, PMC10182257](https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/).
- **Nearest analog 2 — retina base/prime editing (works in animals, not yet opsins):** in vivo base/prime editing has rescued retinal phenotypes in mice (rd10 Pde6b prime editing ~41% retinal editing via dual-AAV split-PE) ([Eye on genome editing, PMC10035435](https://pmc.ncbi.nlm.nih.gov/articles/PMC10035435/); [rd12 prime editing, PMC10474087](https://pmc.ncbi.nlm.nih.gov/articles/PMC10474087/)), and an AAV5 adenosine base editor reached **up to 75% editing in cone cells and 87% in RPE of the macula in NHPs** ([Base and Prime Editing for IRDs, PMC12655462](https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/)). Reviews: [PMC9913839](https://pmc.ncbi.nlm.nih.gov/articles/PMC9913839/), [PubMed 36241547](https://pubmed.ncbi.nlm.nih.gov/36241547/).
- **No animal model of a human tritan mutation exists.** Available Opn1sw mice are knockouts/hypomorphs or spectral/trafficking engineering (F81Y knock-in, abnormal cone physiology; Insinna 2012) ([MGI MGI:99438](https://www.informatics.jax.org/marker/MGI:99438); [PMC3381355](https://pmc.ncbi.nlm.nih.gov/articles/PMC3381355/); [Daniele 2011](https://pubmed.ncbi.nlm.nih.gov/21219924/)). The Opn1sw⁻/⁻ phenotype (dorsal cones okay, ventral cone outer segments absent/short, cones viable ≥1.5 yr) matters for therapy design: S-opsin loss alone is compatible with long-term cone survival in mouse ([Daniele 2011](https://pubmed.ncbi.nlm.nih.gov/21219924/); [PMC4167788](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4167788/)).

### 3.2 S-cone biology relevant to therapy

- S cones are **~5–10% of the human cone mosaic** (peak ~2,000–2,600/mm² at ~0.3–0.7 mm eccentricity; ~7.6% of cones at 9° eccentricity), **absent from the central ~0.35° of the foveola**, peaking on the foveal slope ([Webvision: S-cone pathways](https://www.webvision.pitt.edu/book/part-iii-retinal-circuits/s-cone-pathways/); [Curcio et al. 1991, J Comp Neurol 312:610–624 — summarized in PMC11538286](https://pmc.ncbi.nlm.nih.gov/articles/PMC11538286/) and [J Neurosci 2020, jneurosci.org/content/40/42/8132](https://www.jneurosci.org/content/40/42/8132)).
- Therapeutic implications: (a) **target the perifoveal ring, not the foveola** — subretinal blebs cover foveal/perifoveal retina well; (b) normal acuity is unaffected, so the bar is *color discrimination*, which is psychophysically subtle and demands high edit/transduction fractions of a small S-cone population; (c) S cones die progressively in tritan families — intervention window favors early/young treatment, consistent with the 2- vs 5–7-month therapeutic cliff in opsin-null mouse rescue ([PMC9347391](https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/)).
- Promoter consideration: PR2.1 (2.1-kb human red/green opsin promoter) targets L/M cones — the standard cone vector promoter ([PMC5532293](https://www.nature.com/articles/s41598-017-06982-7)) — so S-cone-restricted expression needs an S-opsin promoter; RORβ-binding elements upstream of Opn1sw are required for S-opsin expression in mouse retina ([Mol Endocrinol 2006](https://academic.oup.com/mend/article/20/8/1728/2738206)) — a lead for promoter design, but a validated human S-cone-specific AAV promoter is not established (open question).

## 4. CRISPR strategy options, per mutation class

OPN1SW is small: CDS 1,044 bp (348 aa), mRNA 1,114 nt (NM_001708.2, verified by EFetch). AAV packaging limit ~4.7 kb; a single AAV easily carries OPN1SW cDNA + promoter + polyA ([AAV cargo limits forcing dual-AAV for editors: PMC9913839](https://pmc.ncbi.nlm.nih.gov/articles/PMC9913839/)).

### 4.1 Adenine base editing (ABE) — corrects the mutant base A→G

| Variant | Mutant base | Correction | In canonical ABE scope? |
|---|---|---|---|
| **G79R** (c.235G>A) | A | A→G | **Yes** |
| **T190I** (c.568G>A) | A | A→G | **Yes** |
| **R283Q** (c.848G>A) | A | A→G | **Yes** |

Pros: ABE is the most mature high-efficiency editor; NHP cone editing of up to 75% demonstrated ([PMC12655462](https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/)); no DSB; single AAV possible with small editors. Bonus for G79R: the WT allele codon GGA contains an A (c.237) whose A→G conversion is silent (GGA→GGG, still Gly) — WT-allele bystander risk at the target codon is benign, though full guide-level bystander analysis (±window) is not yet done (design TODO).
Cons: 3 of 7 known alleles only; bystander A edits in the deamination window must be screened per-guide; requires a PAM near the target (Cas9n/NG/SpRY can relax this).

### 4.2 Cytosine base editing (CBE) — corrects the mutant base C→T

| Variant | Mutant base | Correction | In canonical CBE scope? |
|---|---|---|---|
| **S214P** (c.640T>C) | C | C→T | **Yes** |
| **L56P** (c.167T>C) | C | C→T | **Yes** |

Cons: CBEs have broader bystander and DNA/RNA off-target concerns; S214P WT codon TCC contains two other Cs in-frame (c.641T>C→TTC = Ser→Phe possible; c.642C>T silent) — guide choice must avoid the pathogenic bystander. Still, both alleles are technically correctable without DSBs.

### 4.3 Prime editing (PE) — any small change

| Variant | Needed change | PE needed? |
|---|---|---|
| **P264S** (c.790C>T) | T→C | **Yes** — outside ABE/CBE scope (T-to-C conversion has no canonical editor) |
| **Exon 3 +5delG** (splice) | re-insert 1 bp G | **Yes** — small insertion well within PE capability; can't be done by BE |

Pros: precise, no bystander deamination, handles the only truncation-class allele. Cons: dual-AAV split-PE delivery required (PE too big for one AAV) with substantially lower in vivo editing (~28–41% in retinal models) ([PMC10474087](https://pmc.ncbi.nlm.nih.gov/articles/PMC10474087/); [PMC10035435](https://pmc.ncbi.nlm.nih.gov/articles/PMC10035435/)); pegRNA design/optimization burden.

### 4.4 Gene augmentation (single AAV, S-opsin cDNA)

- Fits trivially: 1.04-kb cDNA + promoter + polyA « 4.7 kb. Proof of concept that opsin-null cones are rescuable by AAV opsin cDNA is strong in mice ([PMC9347391](https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/); [PMC5532293](https://www.nature.com/articles/s41598-017-06982-7)).
- **Critical caveat — the disease is autosomal dominant.** For the missense alleles, if the mutant protein is dominant-negative (folding/trafficking poison), adding WT S-opsin may not rescue S cones that are busy degrading/misrouting mutant opsin — the C203R analog was rescued by augmentation, but in an opsin-null background that removed the mutant protein ([JCI Insight 2023](https://insight.jci.org/articles/view/172834)). The proven-haploinsufficiency splice allele and mild alleles (T190I) are the safest fits for augmentation.
- Mitigation for dominant-negative alleles: allele-specific silencing of the mutant transcript (siRNA/miRNA target sites or CRISPRi) + WT cDNA replacement in one vector, or cutting-mosaic approaches (out of scope here). No published work exists.
- Promoter gap noted in §3.2.

### 4.5 Knock-in / other

- Homology-directed knock-in of a corrected cDNA into the endogenous locus is unnecessary given the small cDNA and AAV-friendliness, and HDR is inefficient in post-mitotic photoreceptors. Recombination-based correction of the splice allele (e.g., editing the splice motif) via PE (§4.3) is more rational. Niche option: PE-based splice-restoration could alternatively edit the cryptic splice consequences (not explored — no literature).

## 5. Recommended target(s), with reasoning

1. **Primary: G79R (c.235G>A) via ABE.** Most clinically reported tritan allele (multiple families, Weitz 1992; also seen comorbid in RP, [PMC7057104](https://pmc.ncbi.nlm.nih.gov/articles/PMC7057104/)); A→G correction in ABE scope; WT-allele bystander at the codon is silent; small-editor single-AAV delivery plausible; NHP cone ABE precedent. Deliver to perifoveal S cones.
2. **Secondary: R283Q and T190I via ABE** — same logic; R283Q additionally has the best-characterized degenerative phenotype (AO imaging, Baraas 2007), useful as a natural-history anchor. T190I is mild — arguably a lower-value target.
3. **Tertiary: PE for P264S and the exon 3 +5G deletion.** P264S is the severe/classic missense but needs T→C (PE-only); the splice deletion is PE-correctable by 1-bp insertion and is likely the most *frequent* allele in the population (MAF 0.132%) — PE's lower efficiency is offset by haploinsufficiency (no dominant-negative to overcome) and mild phenotype; may be better served by augmentation anyway.
4. **Fallback strategy for all alleles: single-AAV OPN1SW augmentation** once an S-cone-specific promoter is sorted — universal, avoids per-variant guide work, but dominant-negative risk for missense alleles is unresolved.
- Do **not** prioritize: L56P (single family, 2006 report, CBE with possible pathogenic bystander risk) except as a completeness exercise.

## 6. Key papers (with URLs)

Genetics / natural history
- Weitz, Miyake, Shinzato, Montag, Zrenner, Went & Nathans 1992a, *Am J Hum Genet* 50:498–507 — G79R, S214P; 1992b, *AJHG* 51:444–446 — P264S (full texts: [OMIM 190900 allelic variants](https://omim.org/entry/190900), [OMIM 613522](https://omim.org/entry/613522))
- Baraas, Carroll, Gunther, Chung, Williams, Foster & Neitz 2007, *J Opt Soc Am A* 24:1438–1447 — R283Q, AO evidence of S-cone dystrophy (referenced in [PMC3516400](https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/) and [MedlinePlus](https://medlineplus.gov/genetics/gene/opn1sw/))
- Gunther, Neitz & Neitz 2006 — L56P (referenced in [PMC3516400](https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/))
- Baraas, Hagen, Dees & Neitz 2012, *Vision Res* 73:1–9 — T190I — https://pmc.ncbi.nlm.nih.gov/articles/PMC3516400/
- Baraas, Foster, Sumness et al. 2019? (IOVS) — OPN1SW intron 3 +5delG splice defect, haploinsufficiency — https://pmc.ncbi.nlm.nih.gov/articles/PMC7254067/
- Review: *Cone Opsins and Inherited Retinal Disease* (Cells 2026) — https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/ and https://www.mdpi.com/2073-4409/15/12/1098
- Simunovic & Moore, *Eye* 2009 — CVD prevalence incl. tritan — https://www.nature.com/articles/eye2009251
- MedlinePlus OPN1SW — https://medlineplus.gov/genetics/gene/opn1sw/ ; MedGen C0155017 — https://www.ncbi.nlm.nih.gov/medgen/C0155017/
- ClinVar mirror (variant list) — https://www.malacards.org/card/tritanopia

S-cone biology
- Curcio, Sloan, Kalina & Hendrickson 1990, *J Comp Neurol* 292:497–523; Curcio et al. 1991 *J Comp Neurol* 312:610–624 (anti-blue-opsin topology) — via [PMC11538286](https://pmc.ncbi.nlm.nih.gov/articles/PMC11538286/), [J Neurosci 2020](https://www.jneurosci.org/content/40/42/8132)
- Webvision, S-cone pathways (Kolb) — https://www.webvision.pitt.edu/book/part-iii-retinal-circuits/s-cone-pathways/
- RORβ activates Opn1sw (promoter biology) — https://academic.oup.com/mend/article/20/8/1728/2738206

Therapy analogs / models
- Ma, Li, Chen et al. 2022, *Hum Gene Ther* — AAV5-OPN1LW rescues Opn1mw⁻/⁻Opn1sw⁻/⁻ cones — https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/
- Deng, Cehajic-Kapetanovic, Kostic, Carroll, Rubin 2018, *Sci Rep* — AAV-M-opsin rescue — https://www.nature.com/articles/s41598-017-06982-7
- C203R missense (folding/trafficking) augmentation rescue, *JCI Insight* 2023 — https://insight.jci.org/articles/view/172834
- BCM gene therapy review — https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/
- Daniele et al. 2011, *Vision Res* 51:447–458 — Opn1sw(Neo/Neo) mouse — https://pubmed.ncbi.nlm.nih.gov/21219924/
- Insinna et al. 2012 — F81Y S-opsin knock-in, trafficking defect — https://pmc.ncbi.nlm.nih.gov/articles/PMC3381355/ ; MGI Opn1sw — https://www.informatics.jax.org/marker/MGI:99438
- *Eye on genome editing* 2023 (rd10 dual-AAV prime editing) — https://pmc.ncbi.nlm.nih.gov/articles/PMC10035435/
- *Base and Prime Editing for Inherited Retinal Diseases* (NHP cone ABE 75%) — https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/
- Prime editing delivery for IRD (dual-AAV split-PE) — https://pmc.ncbi.nlm.nih.gov/articles/PMC9913839/
- Trial landscape (no OPN1SW entry): *Clin Exp Ophthalmol* 2025 — https://pmc.ncbi.nlm.nih.gov/articles/PMC11962696/

## 7. Open questions

1. **Mechanism per missense allele is unproven.** No in vitro expression/trafficking study of any tritan OPN1SW mutant exists (searches returned none). Dominant-negative vs haploinsufficiency vs simple loss-of-function matters enormously for editing-vs-augmentation choice. A cell-culture expression assay (S-opsin folding/trafficking like Insinna's F81Y work) is the obvious first in-silico-adjacent experiment — not designed here.
2. **Prevalence is unsettled** (1 in 500 vs 1 in 13,000–65,000). The splice allele MAF (0.132%) suggests the high end may be real; population-genetics reconciliation would sharpen market/impact estimates.
3. **"C90D" does not exist in OPN1SW** (OMIM/ClinVar/literature searches, 2026-10-22) — parent-task hint should be dropped; verify it wasn't a confusion with a rhodopsin or L/M-opsin variant.
4. **No disease-mutation animal model** — a knock-in (G79R or P264S) mouse would be a prerequisite for any translational step; none exists.
5. **Guide-level design not yet done:** PAM availability, bystander edits in ABE/CBE windows (esp. S214P's c.641 T>C → Ser→Phe risk), and off-target analysis in the OPN1SW/opsin-family context (OPN1SW shares ~40% identity with L/M opsins — low homology risk, but must be checked) are all open TODOs.
6. **S-cone-specific promoter for AAV** — validated human S-cone-restricted promoter is missing; RORβ-responsive Opn1sw upstream elements are a starting point ([Mol Endocrinol 2006](https://academic.oup.com/mend/article/20/8/1728/2738206)).
7. **Penetrance and progression** — incomplete penetrance complicates patient selection and endpoint design; what fraction of genotype-positive carriers progress to S-cone loss?
8. **Dose/endpoint:** with S cones at 5–10% of cones and no acuity benefit, what edit fraction yields psychophysically measurable tritan improvement? No model data exist.
