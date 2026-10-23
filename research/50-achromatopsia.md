# Achromatopsia — Research Dossier (CRISPR Design Project #50)

Scope: in-silico literature and design assessment only. No wet-lab protocols.
Compiled: 2026-10-22. Sources verified via web search/extract; URLs inline.

---

## 1. Disease Overview

**Definition.** Achromatopsia (ACHM; rod monochromatism; total color blindness) is an autosomal-recessive retinal disorder defined by absent or severely impaired function of all three cone photoreceptor classes from birth/early infancy. Classic presentation: reduced visual acuity (commonly ≤20/200 in the complete form), total or near-total color blindness, photophobia, and nystagmus (often improving slightly with age). Full-field ERG shows significantly reduced/absent cone responses with normal or sub-normal rod responses. Sources:
- https://pmc.ncbi.nlm.nih.gov/articles/PMC8766373/ (Springer review, *Achromatopsia: Genetics and Gene Therapy*)
- https://journals.lww.com/co-ophthalmology/fulltext/2015/09000/achromatopsia__a_review.2.aspx
- https://gene.vision/knowledge-base/achromatopsia-for-doctors/

**Prevalence.** ~1:30,000 live births (range up to 1:50,000 in some estimates); one of the more common causes of childhood visual impairment. Sources: PMC8766373; PMC11298110 (https://pmc.ncbi.nlm.nih.gov/articles/PMC11298110/).

**Complete vs incomplete.**
- *Complete ACHM:* no color discrimination; VA typically 6/60 (logMAR 1.0) or worse.
- *Incomplete (atypical) ACHM:* uncommon, milder phenotype with residual cone function — residual color discrimination and VA roughly 6/24–6/60. Initially linked to *CNGA3* missense variants retaining partial channel function, but residual cone function has also been documented in *CNGB3* and *GNAT2* patients; the term "oligocone trichromacy" has been proposed. Genotype alone does not strictly predict complete vs incomplete phenotype. Sources:
  - https://pmc.ncbi.nlm.nih.gov/articles/PMC1771989/ (The cone dysfunction syndromes)
  - https://journals.lww.com/co-ophthalmology/fulltext/2015/09000/achromatopsia__a_review.2.aspx
  - https://onlinelibrary.wiley.com/doi/10.1002/humu.20790 (CNGA3 trafficking/function, complete vs incomplete ACHR)

**Cone loss / progression.** Historically considered stationary, but long-term structural data revise this:
- Visual acuity is generally stable long-term, yet OCT shows slowly progressive structural change (ellipsoid-zone [EZ] disruption, expanding optically empty/hyporeflective zone) — function/structure dissociation. Hyperreflective foci may precede EZ disruption by >3 years.
- A longitudinal OCT study (n=63, ~3.1 y) found 95% had stable EZ grades; only 3/63 progressed and cone density (AOSLO) was stable over up to 9 years — i.e., foveal cone structure is largely preserved over trial-relevant timeframes, which is the critical fact for any rescue therapy: cones are mostly **present but dormant**, not absent.
- Split-detector AOSLO reveals residual cone inner segments even where confocal images are hyporeflective — these are the candidate target cells for rescue.
- Genotype nuance: *GNAT2* mosaics relatively preserved; *PDE6C* and *ATF6* retinas have very few (if any) remaining foveal cones; cGMP accumulation (PDE6 defects) is thought to drive degeneration, potentially faster in S-cone-rich regions.
Sources:
- https://pmc.ncbi.nlm.nih.gov/articles/PMC11005076/ (Longitudinal OCT in ACHM)
- https://pmc.ncbi.nlm.nih.gov/articles/PMC4786023/ (Adaptive optics ophthalmoscopy; rescue rationale)
- https://gene.vision/knowledge-base/achromatopsia-for-doctors/
- https://lumic-eye.jp/en/retina/achromatopsia/ (10-y follow-up; summary of OCT stages)

---

## 2. Molecular Genetics

**Inheritance:** autosomal recessive; only homozygous/compound-heterozygous individuals are affected; carriers have normal vision (https://pmc.ncbi.nlm.nih.gov/articles/PMC8766373/).

**Six known genes** (five phototransduction cascade components + one UPR regulator). Together they explain ~90% of cases; CNGA3+CNGB3 alone explain ~70–90%. Prevalence varies strongly by population.

| Gene | Approx. share of ACHM | Notes |
|---|---|---|
| *CNGB3* | ~40–50% | Dominant in Europe/USA (≥50%); only 8% in Israeli/Palestinian cohorts; ~80% CNGA3-dominated in China/Middle East. Encodes β-subunit of cone CNG channel. |
| *CNGA3* | ~25% (up to 30–40% by some counts) | Encodes α-subunit of cone CNG channel. Most common in Middle East, China (≈80% of cases), Israel (92.3% in one cohort). Predominantly missense, clustered in TM S1/S2, S4 hotspot and cGMP-binding domain. |
| *GNAT2* | <2% | Cone transducin α-subunit. |
| *PDE6C* | <2% (up to ~5% combined with PDE6H in some cohorts; 38.1% in a Korean cohort) | Cone PDE6 catalytic α′ subunit; cGMP hydrolysis. |
| *PDE6H* | ~0.3% (<1%) | Cone PDE6 inhibitory γ subunit. |
| *ATF6* | ~1–2% | ER transmembrane transcription factor, unfolded protein response; only ACHM gene outside phototransduction; associated with foveal hypoplasia. |

Sources:
- https://pmc.ncbi.nlm.nih.gov/articles/PMC8766373/
- https://journals.lww.com/co-ophthalmology/fulltext/2015/09000/achromatopsia__a_review.2.aspx
- https://pmc.ncbi.nlm.nih.gov/articles/PMC11396370/ (Gene Therapy for Achromatopsia)
- https://pmc.ncbi.nlm.nih.gov/articles/PMC10298554/ (Table 2, mutation landscape)
- https://pmc.ncbi.nlm.nih.gov/articles/PMC12000072/ (CNGA3 achromatopsia cohort; Korean/US/UK comparisons)
- https://gene.vision/knowledge-base/achromatopsia-for-doctors/

**Mutation-type distribution per gene.**
- *CNGA3:* predominantly **missense** (e.g., of 46 mutations in Wissinger 2001: 39 missense, 4 nonsense, 2 single-bp insertions, 1 in-frame deletion); clusters at cytoplasmic face of TM S1/S2, TM S4, cGMP-binding domain. https://pubmed.ncbi.nlm.nih.gov/11536077/ ; https://omim.org/entry/600053
- *CNGB3:* predominantly **truncating** — nonsense, frameshift, splice (Kohl 2000: 28 mutations incl. 12 nonsense, 8 indels, 5 splice, 3 missense); plus heterozygous copy-number variants (deletions of 1–10 exons) in ~3% of CNGB3 patients. https://www.nature.com/articles/5201269 ; https://onlinelibrary.wiley.com/doi/10.1002/humu.23311 (552 patients, 98 variants, 58 novel; 9 CNVs in 16 patients)
- *GNAT2/PDE6C/PDE6H/ATF6:* individually rare genes; a mix of missense and truncating variants reported; no single variant dominates at the population level given their low shares.

**Recurrent / founder variants — the key question for single-target editing.**

Yes — achromatopsia has several genuinely recurrent variants, concentrated in *CNGB3* (truncating, founder effects) and a small set of *CNGA3* missense hotspots:

1. **CNGB3 c.1148delC (p.Thr383fs)** — the single most important ACHM variant. A 1-bp deletion accounting for **>70% (up to ~75–80%) of all mutant CNGB3 alleles** in large European cohorts; pan-ethnic founder mutation with shared haplotype; prevalent in European-descent patients. Reported first in 2000; founder effect confirmed by Wiszniewski 2007 (p.T383fs). Sources:
   - https://www.nature.com/articles/5201269 (c.1148delC >70% of CNGB3 mutant alleles)
   - https://www.omim.org/entry/262300 (75%, 18/24 alleles; founder haplotype)
   - https://pmc.ncbi.nlm.nih.gov/articles/PMC8477987/ ("~66% of all CNGB3 mutant alleles"; "panethnic founder mutation")
   - https://gene.vision/knowledge-base/cngb3/
   ⚠️ **Correction to the project brief:** the brief lists "CNGA3 c.1148delC" — this is wrong. c.1148delC is a ***CNGB3*** variant.
   ⚠️ **Unverified:** "CNGB3 c.1572_1573insT / S70" — I could not confirm this variant in any primary source. A similar-looking variant, c.1572_1575del (p.Phe525AsnfsTer13), appears on a patient-advocacy gene page (https://araceagainstblindness.org/education/genes/CNGB3) of uncertain authority. Treat c.1572_1573insT as unverified until checked against ClinVar/HGMD/LOVD.

2. **CNGB3 deep-intronic variants** — c.1663-1205G>A (IVS14-1205G>A), the most common cause among Jewish patients (more frequent than c.1148delC in that cohort; causes pseudoexon activation); plus other pseudoexon-activating deep-intronic variants (Weisschuh 2020). Splice-targeted editing or splice modulation could address these mechanistically. Sources:
   - https://pubmed.ncbi.nlm.nih.gov/34703197/ (Mol Vis 2021;17 patients, 12 families)
   - https://pubmed.ncbi.nlm.nih.gov/?from_uid=54714&linkname=gene_pubmed_rif (Weisschuh, Hum Mutat 2020, 41:255–264)

3. **CNGB3 missense founder variants** — CNGB3 p.Ser435F in the Pingelapese islanders of Micronesia (5–10% population incidence from a ~1775 typhoon bottleneck); CNGB3 p.T383fs founder effect (Wiszniewski 2007). Sources: https://medlineplus.gov/genetics/gene/cngb3/ ; https://pubmed.ncbi.nlm.nih.gov/10888875/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC1771989/

4. **CNGA3 recurrent missense quartet** — Arg277Cys, Arg283Trp, Arg436Trp, Phe547Leu together account for **~40–42% of all mutant CNGA3 alleles** in large European cohorts. Haplotype analysis: R436W and F547L have multiple origins (mutational hotspots), while R283W is a true founder (common in Scandinavia and northern Italy). These are G:C→A:T or C:G→T:A transitions (e.g., R277C = c.829C>T, R436W = c.1306C>T, F547L = c.1639C>A/G) — i.e., *within the canonical reach of cytosine/adenine base editors*. Sources:
   - https://pubmed.ncbi.nlm.nih.gov/11536077/ (Wissinger 2001)
   - https://omim.org/entry/600053 (41.8% of detected mutations)
   - https://pmc.ncbi.nlm.nih.gov/articles/PMC1771989/ (~40%)
   - https://vision.psychol.cam.ac.uk/jdmollon/papers/achromatopsia.pdf

5. **Geographic/population specificity caveat.** In an Israeli cohort CNGA3 was 92.3% of cases with only 1 CNGB3 patient; in the Netherlands CNGB3 is ~87%; Russian cohort: c.1148delC is the most frequent CNGB3 allele (~75% of CNGB3 mutant alleles). Any "single-target editing" program is therefore strongly population-stratified. Sources: https://pmc.ncbi.nlm.nih.gov/articles/PMC12000072/ ; the Russian summary at https://scispace.com/pdf/osobennosti-epidemiologii-kliniki-i-patogeneza-akhromatopsii-4lzn6oiueg.pdf

---

## 3. State of the Art — AAV Augmentation Clinical Trials

All five phase I/II trials use **subretinal AAV gene augmentation** (single monocular subretinal injection; cone-specific promoter PR1.7/hG1.7/hCARp). All genes fit comfortably in AAV (CNGA3 ~1.6 kb, CNGB3 ~2.4 kb, GNAT2 ~1.1 kb coding — no dual-vector requirement), which is the core reason augmentation is the field default.

| NCT | Gene | Vector | Sponsor | Status | Key reported results |
|---|---|---|---|---|---|
| NCT03001310 | CNGB3 | AAV8-hCARp.hCNGB3 | MeiraGTx (UK II) + Janssen | Completed (23 participants: 11 adults, 12 children) | Safe/tolerable; **no consistent pattern** of change week-24 vs baseline across cohort; favorable changes in individual participants: color vision (lvvCCT) 6/23, photo-aversion 11/20, VRQoL 21/23. No significant full-field or pattern-ERG change. 3 participants had severe inflammation (resolved with steroids beyond 6 weeks). Program **stalled after Janssen acquisition of MeiraGTx assets (2023)**. |
| NCT02599922 | CNGB3 | rAAV2tYF-PR1.7-hCNGB3 (AGTC-401) | AGTC → Beacon Therapeutics | Active, not recruiting | Safe/well-tolerated incl. after early SUSARs; robust visual-sensitivity improvements in some adults and pediatric patients at 1.1×10^12 vg/mL dose; retinal-sensitivity improvements 4/11 and light-discomfort improvements 6/11 in high-dose/pediatric groups; no consistent sustained BCVA improvements cohort-wide. |
| NCT02935517 | CNGA3 | rAAV2tYF-PR1.7-hCNGA3 (AGTC-402) | AGTC → Beacon Therapeutics | Active, not recruiting | Preliminary: improvements in photosensitivity and two-color dark-adapted perimetry in 3/16 (CNGA3 study) and 7/16 (CNGB3 companion) in higher-dose groups; no treatment-related SAEs; pediatric enrollment (4–8 y) ongoing as of interim reports. |
| NCT02610582 | CNGA3 | AAV8.CNGA3 (rAAV8.hG1.7p.coCNGA3) | STZ eyetrial (Tübingen; LMU collaboration) | Active, not recruiting | Fischer 2020 JAMA Ophthalmol: 9 adults, 3 dose groups, 12-mo follow-up, no substantial safety problems; **all 9 treated eyes improved**: BCVA +2.9 letters (p=.006), log contrast sensitivity +0.33 (p=.003); modest color-vision gains. |
| NCT03758404 | CNGA3 | AAV8-hG1.7p.coCNGA3 | MeiraGTx UK II (pediatric, 4–17 y) | Completed (n=11) | Acceptable safety at all doses; eye inflammation in 3 (high dose); improvements in some visual measures (HRA summary); enabled the landmark "cone function plasticity" study (Brain 2022): 2 of 4 children (10–15 y) showed novel retinotopic cone-mediated cortical signals (fMRI) + ceiling-level monocular cone-contrast gains in the treated eye — first demonstration that augmentation can awaken dormant cone pathways post-deprivation. |

Sources:
- https://meiragtx.com/wp-content/uploads/2023/10/First-in-Human-Gene-Therapy-Trial-of-AAV8-hCARp.h-CNGB3-in-Adults-and-Children-With-CNGB3-associated-Achromatopsia.pdf (Michaelides et al., first-in-human CNGB3; 6/23 color vision figure)
- https://jamanetwork.com/journals/jamaophthalmology/fullarticle/2765029 (Fischer 2020)
- https://academic.oup.com/brain/article-abstract/145/11/3803/6673168 (Brain 2022 plasticity)
- https://www.hra.nhs.uk/planning-and-improving-research/application-summaries/research-summaries/gene-therapy-for-achromatopsia-cngb3/ and .../gene-therapy-of-patients-with-achromatopsia-due-to-cnga3-defects/ (UK HRA trial summaries; inflammation details)
- https://www.cgtlive.com/view/cngb3-achromatopsia-gene-therapy-improves-visual-sensitivity (AGTC-401 pediatric data)
- https://www.ophthalmologytimes.com/view/gene-therapy-offers-first-steps-in-treatment-of-achromatopsia (AGTC-401/402 interim)
- https://www.fightingblindness.org/news/agtc-announces-results-for-achromatopsia-gene-therapy-clinical-trials-802 (mixed efficacy)
- https://pmc.ncbi.nlm.nih.gov/articles/PMC13002551/table/t2/ (trial table: sponsors, vectors, status)
- https://retinatoday.com/articles/2025-july-aug/top-irds-to-watch-achromatopsia (MeiraGTx/Janssen stall; trial summary)
- https://scge.mcw.edu/platform/data/report/clinicalTrials/NCT03758404

**Why augmentation is preferred here.** All six genes are small enough for single-vector AAV packaging (AAV limit ~4.7 kb), so unlike e.g. ABCA4/Stargardt or USH2A there is no size barrier. A single augmentation construct serves **all** mutations in a given gene regardless of type (missense, nonsense, splice, frameshift, CNV). Preclinical mouse/dog/sheep augmentation rescued cone function (Michalakis 2010; GNAT2 proof-of-principle 2007), giving strong translational precedent. Source: https://www.pnas.org/doi/pdf/10.1073/pnas.1902292116 ; https://www.pharmacology.cup.uni-muenchen.de/research/retinal_gene_therapy/index.html

**Mixed efficacy reality.** Every published trial shows: good safety, statistically significant but modest mean functional gains (Fischer: ~3 letters BCVA), **heterogeneous individual responses**, no reliable ERG endpoint change, and cohort-level "no consistent pattern" (MeiraGTx CNGB3, AGTC). Treated-eye-specific improvements (Brain 2022; Fischer) confirm biology works; the limiting factors are debated: (a) residual cone count per patient, (b) adult cortical plasticity limits, (c) immune/inflammation, (d) endpoints mismatched to effect size.

**Pediatric vs adult timing debate.** Cone deprivation from birth may cause central visual-cortex developmental changes that cap adult benefit; younger retinas retain more dormant cones; the Brain 2022 study explicitly argues treatment "within the plastic period" can awaken dormant pathways in children 10–15 y, while adult trials show smaller, variable gains. This pushed all programs toward pediatric enrollment (MeiraGTx CNGA3 trial children 4+; AGTC amended protocols to age 4). Counterpoint: subretinal surgery risk and maturing ocular growth make very-early treatment harder, and pediatric endpoints are less testable. Sources: https://academic.oup.com/brain/article-abstract/145/11/3803/6673168 ; https://www.frontiersin.org/journals/ophthalmology/articles/10.3389/fopht.2023.1188522/full ; https://www.cgtlive.com/view/cngb3-achromatopsia-gene-therapy-improves-visual-sensitivity

Perceptual caveat: even where cone signals return, color perception is qualitatively limited ("Seeing color following gene augmentation therapy in achromatopsia," 2023 — patients detect colored stimuli only in the treated eye, with rod-like lightness judgments and low saliency). https://pubmed.ncbi.nlm.nih.gov/37433300/

---

## 4. CRISPR Strategy Options

### (a) Gene augmentation (current standard) — *not CRISPR, the comparator*
- **Pros:** one construct per gene covers 100% of that gene's patients regardless of mutation type; genes are AAV-sized; 5 phase I/II trials completed/underway with human safety data; works even for truncating variants where repair target isn't a clean point mutation; preclinical rescue established in mouse/dog/sheep.
- **Cons:** efficacy is modest and heterogeneous; no robust ERG endpoint; inflammation at high dose; monocular benefit; industry momentum uncertain (MeiraGTx/Janssen program stalled; AGTC became Beacon Therapeutics); dosing/luminal spread limits treatment area (fovea + parafovea only).
- Sources: as §3.

### (b) Mutation-specific base/prime editing for recurrent variants
- **Precedent that editing photoreceptors in vivo can work:**
  - Dual-AAV prime editing corrected Pde6b Y347X in rd1 mice: ~26% editing, PDE6B protein restored to 39% of WT, photoreceptor survival + ERG rescue (Nat Commun 2025). https://www.nature.com/articles/s41467-025-57628-6
  - Prime Medicine RHO P23H/V345L/P347L: up to ~65–70% precise correction in photoreceptors via dual-AAV, <0.5% unintended edits (RD2023). https://investors.primemedicine.com/news-releases/news-release-details/prime-medicine-presents-first-vivo-proof-concept-prime-editing
  - CRISPR-HDR/base editing proposed for PDE6-mutant NHPs. https://www.pnas.org/doi/pdf/10.1073/pnas.1902292116
  - Threshold relevance: mouse knock-in data show **~20% of normal CNGA3 protein suffices for near-normal cone phototransduction** — a permissive therapeutic bar for editing efficiency. https://pmc.ncbi.nlm.nih.gov/articles/PMC8347118/
- **Target fit analysis:**
  - *CNGB3 c.1148delC* (a 1-bp deletion): a **prime editing** (or bridging/PE-lite) target — restore the reading frame. Addressable patient pool ≈ 0.5 × 0.45 ≈ **20–25% of all ACHM patients of European descent carry ≥1 c.1148delC allele** (CNGB3 ~45% of ACHM; allele ~70%+), but most are compound heterozygotes: editing one allele in a compound heterozygote does **not** restore the other allele → truly eligible population is biallelic c.1148delC homozygotes (a minority) unless combined with augmentation for the second allele. Heterozygous carriers unaffected — no somatic harm from imperfect editing.
  - *CNGA3 recurrent missense quartet (R277C, R283W, R436W, F547L):* canonical C→T / G→A transitions within **cytosine/adenine base-editor reach**; each is a single clean edit. Covers ~40% of CNGA3 mutant alleles (CNGA3 ≈ 25% of ACHM → roughly 10% of total ACHM allele coverage, again split between hetero/homozygous states). These also dominate in *incomplete* ACHM, where residual cone function implies retinal cells are healthy — arguably the best-case editing population.
  - *CNGB3 deep intronic c.1663-1205G>A* (Jewish population): single A>G transition, adenine-base-editable in principle, or the pseudoexon could be targeted by splice-editing; small population (~0.3–1% of ACHM globally) but founder-concentrated, simplifying trial logistics.
- **Cons:** PE systems need dual-AAV (cargo ~6.3 kb vs 4.8 kb AAV cap) — two-vector subretinal delivery with reconstitution; editing efficiency (tens of %) may fall short if needed in a larger fraction of cells; permanent edit = no dose titration, and subretinal coverage is inherently focal; indel byproducts of Cas9 nickase activity in a surviving-cone population; each variant needs its own gRNA/editor optimization and regulatory path (n-of-1-drug economics for a 1:30,000 disease); competitive landscape: augmentation already in trials with a cleaner path.
- **Pros:** no lifelong transgene overexpression; restores the *native* channel with native regulation; precisely addressable patients identifiable by cheap genotyping; unaffected-carrier biology means off-target partial editing is not a toxicity catastrophe (cells stay functional).

### (c) Conclusion: editing is not the practical entry point here
The diverse, population-stratified, largely truncating mutation landscape means mutation-specific editing fragments the patient pool (per-variant programs of a few hundred to low-thousands of patients globally) into programs that are individually too small and too expensive for a disease where a one-size-fits-all augmentation already exists, is AAV-encodable, and has been de-risked in five human trials. The one arguable exception — biallelic CNGB3 c.1148delC — is better served by the standard augmentation route unless augmentation fails clinically.

---

## 5. Recommendation

**Do NOT start a CRISPR design subproject on achromatopsia at this time. Classify it as an "augmentation-watched" category.**

Reasoning:
1. **Therapeutic ceiling already claimed:** six genes all AAV-sized; augmentation covers every mutation class; five phase I/II trials have established the safety envelope and human dosing. A CRISPR program would compete head-on with an incumbent modality whose main open problems (efficacy heterogeneity, endpoints, timing) are not problems CRISPR specifically solves.
2. **Fragmented mutation landscape:** even the best single target (CNGB3 c.1148delC, ~70% of CNGB3 mutant alleles) reaches a small truly-eligible (biallelic) pool, and patients are heavily population-stratified (CNGB3-dominant Europe/USA vs CNGA3-dominant Middle East/China vs PDE6C-heavy Korea).
3. **Editing feasibility is unproven for this tissue modality at needed scale:** dual-AAV prime editing in cones is at mouse-POC stage (2023–2025), and while the 20%-protein-threshold finding (Cnga3 knock-in) is encouraging, no CNGA3/CNGB3 editing study in a disease model exists to date (as of this search).
4. **When to revisit (watch triggers):** (a) augmentation phase III results disappoint or a program halts, leaving a mutation-specific niche open; (b) dual-AAV prime editing demonstrates cone rescue in a CNGA3/CNGB3 disease model; (c) a well-powered longitudinal study shows late cone degeneration (Sundaram/Dubis-style split-detector data) that augmentation can no longer address but in-situ correction of the c.1148delC allele in still-viable cones could; (d) incomplete-ACHM CNGA3 missense quartet is prioritized as a base-editing showcase (clean single-base C→T transitions, healthy target tissue, measurable residual function as a sensitive endpoint).

---

## 6. Key Papers & URLs

**Reviews / genetics**
- Achromatopsia: Genetics and Gene Therapy (Genes/PMC 2022): https://pmc.ncbi.nlm.nih.gov/articles/PMC8766373/
- Achromatopsia: a review (Curr Opin Ophthalmol 2015): https://journals.lww.com/co-ophthalmology/fulltext/2015/09000/achromatopsia__a_review.2.aspx
- The cone dysfunction syndromes (Surv Ophthalmol/PMC): https://pmc.ncbi.nlm.nih.gov/articles/PMC1771989/
- Gene Therapy for Achromatopsia (2024/PMC): https://pmc.ncbi.nlm.nih.gov/articles/PMC11396370/
- Gene Vision professional page: https://gene.vision/knowledge-base/achromatopsia-for-doctors/

**Mutation landscape**
- Kohl 2000, CNGB3 accounts for ~50% (EJHG): https://www.nature.com/articles/5201269
- Reuter/Jägle CNGB3 spectrum, 552 patients (Hum Mutat 2020): https://onlinelibrary.wiley.com/doi/10.1002/humu.23311
- Wissinger 2001, CNGA3 mutations (Hum Mutat/Am J Hum Genet abstract): https://pubmed.ncbi.nlm.nih.gov/11536077/
- OMIM CNGB3 #262300: https://www.omim.org/entry/262300 ; OMIM CNGA3 #600053: https://omim.org/entry/600053
- Aweidah 2021, CNGB3 deep intronic c.1663-1205G>A in Jewish patients: https://pubmed.ncbi.nlm.nih.gov/34703197/
- Wiszniewski 2007, p.T383fs founder (via citations): https://medlineplus.gov/genetics/gene/cngb3/
- Pingelapese founder (Sundin 2000): https://pubmed.ncbi.nlm.nih.gov/10888875/

**Clinical trials & outcomes**
- Michaelides et al., first-in-human AAV8-hCARp.hCNGB3 (NCT03001310): https://meiragtx.com/wp-content/uploads/2023/10/First-in-Human-Gene-Therapy-Trial-of-AAV8-hCARp.h-CNGB3-in-Adults-and-Children-With-CNGB3-associated-Achromatopsia.pdf
- Fischer 2020, AAV8.CNGA3 (NCT02610582), JAMA Ophthalmol: https://jamanetwork.com/journals/jamaophthalmology/fullarticle/2765029
- Brain 2022, cone function plasticity after gene therapy (children, NCT03758404/NCT03001310): https://academic.oup.com/brain/article-abstract/145/11/3803/6673168
- AGTC trials interim/outcomes: https://www.ophthalmologytimes.com/view/gene-therapy-offers-first-steps-in-treatment-of-achromatopsia ; https://www.cgtlive.com/view/cngb3-achromatopsia-gene-therapy-improves-visual-sensitivity ; https://www.fightingblindness.org/news/agtc-announces-results-for-achromatopsia-gene-therapy-clinical-trials-802
- Trial summary table (sponsors/status): https://pmc.ncbi.nlm.nih.gov/articles/PMC13002551/table/t2/
- UK HRA trial-result summaries: https://www.hra.nhs.uk/planning-and-improving-research/application-summaries/research-summaries/gene-therapy-for-achromatopsia-cngb3/ ; https://www.hra.nhs.uk/planning-and-improving-research/application-summaries/research-summaries/gene-therapy-of-patients-with-achromatopsia-due-to-cnga3-defects/
- Retina Today 2025 program overview (MeiraGTx/Janssen stall): https://retinatoday.com/articles/2025-july-aug/top-irds-to-watch-achromatopsia
- Seeing color following gene augmentation therapy (2023): https://pubmed.ncbi.nlm.nih.gov/37433300/
- Frontiers in pediatric ophthalmology gene therapy review: https://www.frontiersin.org/journals/ophthalmology/articles/10.3389/fopht.2023.1188522/full

**Natural history / cone structure**
- Longitudinal OCT foveal cone structure (2024): https://pmc.ncbi.nlm.nih.gov/articles/PMC11005076/
- Adaptive optics ophthalmoscopy review (rescue rationale): https://pmc.ncbi.nlm.nih.gov/articles/PMC4786023/
- Achromatopsia clinical overview (Japanese ophthalmology summary): https://lumic-eye.jp/en/retina/achromatopsia/

**Editing feasibility / thresholds**
- In vivo prime editing rescues Pde6b rd1 photoreceptors (Nat Commun 2025): https://www.nature.com/articles/s41467-025-57628-6
- Prime Medicine RHO dual-AAV prime editing POC: https://investors.primemedicine.com/news-releases/news-release-details/prime-medicine-presents-first-vivo-proof-concept-prime-editing
- Mouse models / 20% CNGA3 protein threshold (PMC 2021): https://pmc.ncbi.nlm.nih.gov/articles/PMC8347118/
- CRISPR options in NHP retinal models (PNAS): https://www.pnas.org/doi/pdf/10.1073/pnas.1902292116

---

## 7. Open Questions

1. **c.1572_1573insT in CNGB3 (from the project brief): unverified.** No primary source found; closest hit is c.1572_1575del (p.Phe525AsnfsTer13) on a low-authority advocacy page. Needs ClinVar/HGMD/LOVD check before any design work.
2. **True biallelic fraction for c.1148delC** — what fraction of c.1148delC carriers are homozygous (vs compound heterozygous)? This determines the actual addressable population for mutation-specific editing and is not cleanly stated in the sources found.
3. **Efficacy ceiling of augmentation:** is the mixed trial outcome a cone-count problem, a cortical-plasticity problem, or an endpoint/dose problem? The answer decides whether a mutation-specific approach would even outperform augmentation in the same patients.
4. **Long-term cone survival by genotype:** PDE6C/ATF6 retinas appear cone-depleted while CNGA3/CNGB3/GNAT2 retinas retain dormant cones — how durable is this over decades, and does any patient subgroup lose the "editable target tissue"?
5. **Editing efficiency requirement in human cones:** the 20%-protein mouse threshold is for protein level, not per-cell editing fraction; how many cone cells per unit area need in-situ correction, given AAV subretinal blebs cover only part of the retina?
6. **Splice-targeted strategies for deep-intronic CNGB3 variants** (c.1663-1205G>A and pseudoexon-activating variants): base-editable splice-site or antisense approaches untested; population concentration makes a founder-population trial feasible but tiny.
7. **Where is the field heading post-2024:** Beacon's CNGA3/CNGB3 programs status after AGTC's restructuring, and any prime-editor company (Prime Medicine etc.) announcing an ACHM target — should be re-checked before closing the "augmentation-watched" file.
