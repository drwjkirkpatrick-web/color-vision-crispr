# Dossier 30: Blue Cone Monochromacy (BCM) — CRISPR Design Target Brief

> Project: color-vision-crispr — in-silico literature/design only; no wet-lab protocols.
> Compiled: 2026-10-22. All claims sourced; URLs inline.

---

## 1. Disease overview

**Blue cone monochromacy (BCM, OMIM #303700; also called S-cone monochromatism / X-linked incomplete achromatopsia)** is a congenital X-linked recessive cone dysfunction syndrome in which long-wavelength- (L, "red") and middle-wavelength- (M, "green") cone function is completely absent or severely reduced, leaving photopic vision dependent on S- ("blue") cones (2–7% of all cones, mostly peripheral) and rods.

- **Prevalence:** ~1 in 100,000 worldwide (Orphanet: 1–9/100,000; https://www.orpha.net/en/disease/detail/16 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC4717370/)
- **Inheritance:** X-linked recessive (Xq28); almost exclusively affects males. Female carriers are typically unaffected (skewed/random X-inactivation gives each cone either a WT or mutant allele). (https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/)
- **Symptoms from birth/early infancy:** severely reduced visual acuity (logMAR 0.6–1.0), impaired color discrimination (residual tritan discrimination only), infantile nystagmus, photophobia, and often myopia. Fundus usually normal early; macular RPE atrophy may appear in older patients. (https://pmc.ncbi.nlm.nih.gov/articles/PMC4717370/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)
- **ERG:** normal-to-mildly-subnormal rod ERG; normal S-cone ERG; 30-Hz flicker (L/M-cone mediated) responses undetectable in typical BCM. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)
- **Progressive structural degeneration:** OCT shows foveolar outer nuclear layer (ONL) ~60% of normal in patients aged 5–20, with slow progressive thinning and age; foveal cone outer segments (COS) are shortened or absent. Critically, remaining cones retain intact inner segments (biosynthetic machinery intact) → viable targets for gene therapy even into adulthood in a subset (adaptive-optics evidence that some L/M cones remain viable in adults). (Cideciyan 2012 via https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/)

**BCM vs ordinary red-green color vision deficiency (CVD):** common red-green CVD (protan/deutan anomalies, OMIM 303800/303900) arises from the *same* gene cluster but is a **functional/spectral-tuning** condition — hybrid genes or copy-number changes shift opsin spectral sensitivity while cones remain healthy; patients have normal acuity and a normal fundus. BCM is a **degenerative** disease: the causal mutations abolish opsin production/folding, L/M cones lose function **and progressively degenerate**, causing low vision and nystagmus — far more debilitating than simple color blindness. (https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)

---

## 2. Molecular genetics

### 2.1 The OPN1LW/OPN1MW array
- L- and M-opsin are encoded by **OPN1LW** (OMIM *300822) and **OPN1MW** (OMIM *300821), arranged head-to-tail in a tandem array on **Xq28** — typically one OPN1LW followed by one or more OPN1MW copies; units are 37–38 kb, 96% sequence-homologous. An upstream **locus control region (LCR)** drives expression of (at least) the first two genes only; each cone expresses one opsin. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC9271157/)
- The extreme homology and tandem arrangement make **unequal homologous recombination / NAHR** frequent → deletions, duplications, and L/M **hybrid genes**. (https://pmc.ncbi.nlm.nih.gov/articles/PMC9271157/)

### 2.2 Three causal mechanisms
1. **LCR deletions (~40% of cases):** large deletions of the LCR ± parts/all of the opsin array abolish expression of both genes. (https://pmc.ncbi.nlm.nih.gov/articles/PMC4717370/ ; https://www.nature.com/articles/hgv201611)
2. **Single remaining opsin gene inactivated by a point mutation (~60% of cases):** NAHR first reduces the array to a single OPN1LW or OPN1LW/OPN1MW hybrid gene; a second hit (missense, nonsense, or deletion) inactivates it. (https://pmc.ncbi.nlm.nih.gov/articles/PMC4717370/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)
3. **Exon-3 interchange haplotypes (milder spectrum):** recombinant SNP combinations at exon-3 codons 151/153/155/171/174/178/180 — chiefly **LIAVA, LVAVA, MIAVA, LIAVS** (e.g., LIAVA = p.[L153; I171; A174; V178; A180]) — disrupt exon-3 splicing (exon skipping) rather than protein function. LIAVA causes complete exon-3 skipping (no functional pigment); LVAVA/LIVVA partial skipping (mosaic). These cause a spectrum from mild/typical BCM to high myopia and cone dystrophy. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ ; https://www.nature.com/articles/srep28253 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/)

### 2.3 C203R (Cys203Arg) — the flagship missense mutation
- **Nomenclature:** c.607T>C (older numbering: nucleotide 648) → p.Cys203Arg; ClinVar rs104894914 (RCV000011257). (https://www.orpha.net/en/disease/detail/16 ; http://ncbi.nlm.nih.gov/omim/300821)
- **Codon analysis (derived from standard genetic code, consistent with sources):** codon 203 in WT is **TGC** (Cys); the c.607T>C mutation makes it **CGC** (Arg). So Cys codons are TG× (TGT/TGC) and the pathogenic allele is specifically **TGC→CGC at c.607** (first base of codon 203, exon 4).
- **Why C203 is critical:** C203 is one of two highly conserved cysteines (with C126 in cone opsins; rhodopsin equivalents C110–C187) forming the **disulfide bond** between the third transmembrane helix and the second extracellular loop that is essential for proper folding. C203R disrupts the bond → misfolded opsin retained in the ER, unstable, unable to reach the outer segment or activate transducin. Analogous rhodopsin C187Y causes early severe autosomal-dominant RP. (http://www.molvis.org/molvis/v3/a16/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)
- **Frequency:** the most frequently reported inactivating point mutation in BCM. In the Cideciyan/U Penn cohort of 36 molecularly confirmed BCM patients, 21 had large deletions and **15 (42%) carried p.C203R** in single or multiple opsin genes (https://openaccess.city.ac.uk/id/eprint/29916/1/i2164-2591-12-1-25_1674547467.12385.pdf). Nathans/Ostrer: C203R found in 15 BCM males with a single hybrid gene plus both genes of one individual (http://www.molvis.org/molvis/v3/a16/). In a UK series, 2 of 3 families carried C203R (http://www.molvis.org/molvis/v15/a91/). Notably, C203R also occurs at ~2% allele frequency in normal-vision males (incomplete penetrance; can cause deuteranomaly/protanomaly) (http://ncbi.nlm.nih.gov/omim/300821). In the 213-family BCM SV study, ~1/3 of families carried structural variants, the rest point mutations/hybrids (https://pmc.ncbi.nlm.nih.gov/articles/PMC9271157/).
- **Two-step mechanism:** NAHR creates the single/hybrid gene → point mutation introduces C203R (typically in exon 4 of a 5′-L–M-3′ hybrid gene or a downstream M gene). (https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)

### 2.4 Other inactivating variants
- **Nonsense/truncation:** A247X (http://www.molvis.org/molvis/v3/a16/); R247X reported alongside C203R and P307L as the three classic inactivating opsin mutations (https://pmc.ncbi.nlm.nih.gov/articles/PMC4717370/ ; http://www.molvis.org/molvis/v15/a91/); partial/whole-exon deletions (e.g., exons 2 and 4 deletions in Japanese families) (https://www.nature.com/articles/hgv201611).
- **Other missense mutants (in vivo characterized, Zhu 2021 FASEB J):** N94K, W177R, P307L, R330Q, G338E — distinct mechanisms (ER-retained misfolding for N94K/W177R; outer-segment trafficking but defective signaling for P307L/R330Q/G338E); all appear to exert **dominant phenotypes**; W177R and P307L significantly reduce cone viability (https://pmc.ncbi.nlm.nih.gov/articles/PMC8462070/). K82E, P187S, M273K also characterized (K82E possibly dominant-negative via co-transport interference) (https://www.frontiersin.org/journals/neuroscience/articles/10.3389/fnins.2024.1368089/full).

### 2.5 Genotype–phenotype
- **LCR-deletion genotype:** abolished L/M-opsin expression; foveal IS/OS defects develop faster; ONL thinning begins early.
- **C203R genotype:** slower development of IS/OS defects and decades-longer persistence of foveal ONL thickness vs deletions — consistent with lower toxic burden — but comparably severe foveal loss at late ages. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)
- **Exon-3 haplotypes:** milder — measurable cone flicker ERG in 92% (22/24) of haplotype patients vs only 10% (2/21) of typical-BCM patients. (http://www.molvis.org/molvis/v28/21/)

---

## 3. State of the art

### 3.1 Why CNGA3/CNGB3-style augmentation is not directly applicable
Achromatopsia gene therapy (CNGA3/CNGB3 AAV trials) delivers a **functional channel** into otherwise intact cones. BCM cones lack the **opsin itself**, which is both (i) the light sensor initiating phototransduction and (ii) an essential structural scaffold for cone outer segment maintenance; no downstream component can substitute. The correct paradigm for BCM is opsin **gene supplementation** (expression of a WT OPN1LW or OPN1MW cDNA), which also drives regeneration of outer segment structure. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)

### 3.2 Proof-of-concept AAV opsin supplementation
- **Deletion (DKO) model:** AAV5-PR2.1-OPN1LW/OPN1MW subretinal injection rescued photopic ERG (~60% of WT b-wave at 1 month post-treatment when treated <2 months of age), restored outer segment morphogenesis, and re-localized PDE6α′ and cone transducin α to outer segments. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/)
- **C203R (C198R) model (PMC10906232):** *Opn1mw^C198R/Opn1sw^−/−* mice (mutant equivalent of human C203R; mutant opsin undetectable at any age) phenocopy patients (shortened/absent COS, no photopic function). AAV5 cone-targeted augmentation at early ages robustly rescued cone function, elaborated outer segments, and replenished phototransduction proteins — first proof of concept for the C203R genotype. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/)
- **All-cone (TKO) model (PMC13182793):** *Opn1mw^−/−/Opn1sw^−/−/Nrl^−/−* mice (all-cone retina mimicking foveal cone density) treated with AAV8-Y733F-PR2.1-hOPN1LW at 1 AND 5 months → restored cone function, replenished phototransduction proteins, partially regenerated COS membrane; rescue persisted ≥5 months in both age groups — opsin-deficient densely packed cones remain viable targets even after degeneration begins. (https://pmc.ncbi.nlm.nih.gov/articles/PMC13182793/ ; companion PLOS ONE: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0332684)

### 3.3 Treatment window
- **Mouse:** robust rescue when treated <3 months of age; efficacy significantly reduced at ≥5 months in both DKO and C198R models — comparable therapeutic windows; molecular limits include cone degeneration and reduced transgene expression in aged cones. AAV8^Y733F outperforms AAV5 for cone transduction. (https://www.nature.com/articles/s42003-025-09045-0 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC12644701/)
- **Human:** foveolar ONL already ~60% of normal by age 5–20 with slow progressive loss → earlier treatment likely better, but C203R patients' slower degeneration and evidence of viable adult cones (adaptive optics; adult squirrel monkeys gained trichromacy from adult AAV opsin addition — Mancuso 2009) suggest a window extends into adulthood for at least a subset. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC2782927/)
- **Delivery consideration:** subretinal injection is established but invasive; intravitreal would be safer if capsid/promoter penetrance improves. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)

---

## 4. CRISPR strategy options

### (a) Base/prime editing of C203R — precision correction of c.607
- **Target chemistry:** mutant codon = **CGC** (Arg) vs WT **TGC** (Cys). Correction is a **C→T transition at c.607** on the coding strand (CGC→TGC). Cytosine base editors (CBEs) natively perform C·G→T·A — exactly this change; **no transversion needed**. ABEs cannot do it (would require G→A on the opposite strand, and ABEs edit A→G, not G→A). A **CBE or a prime editor** is required; PE can also make the edit cleanly.
- **Pros:** repairs the endogenous gene under native LCR/promoter control (correct physiological expression level and cone specificity); X-linked → only one allele to correct in affected males; the edit is mutation-specific by design; single-base change avoids any exogenous DNA.
- **Cons:** helps only the C203R genotype (a large minority: ~42% of one well-characterized cohort, but far fewer of all BCM when LCR-deletion genotypes are included); CBEs edit every C in the activity window → bystander edits in neighboring codons must be screened (PE avoids this at the cost of larger delivery cargo); requires in vivo editing of terminally differentiated cones; dual-AAV delivery needed for PE (PE machinery exceeds single-AAV capacity); editing efficiency in cones is unproven for CBE and must outpace the degeneration window.
- **Retinal precedent:** in vivo dual-AAV prime editing rescued PDE6B Y347X in rd1 mice (26.5% ± 13.4% editing, minimal off-targets, restored function) (https://www.nature.com/articles/s41467-025-57628-6 ; https://pubmed.ncbi.nlm.nih.gov/40064881/); engineered CBE + PE rescued Pde6a D670G mice (23.8% editing) (https://www.cell.com/molecular-therapy-family/nucleic-acids/fulltext/S2162-2531(25)00176-3); Prime Medicine's dual-AAV platform achieved up to ~70% precise correction of RHO P23H and ~95% of USH2A c.2299delG in photoreceptors of humanized mice, durable to 6 months (https://primemedicine.com/wp-content/uploads/2025/10/ESGCT-Prime-Editing-in-Retinitis-Pigmentosa-Poster-1.pdf).

### (b) Knock-in of an intact opsin cDNA
- **Concept:** CRISPR-mediated HDR insertion of a WT OPN1LW/OPN1MW cDNA into the array (e.g., at the mutant hybrid locus) under endogenous or internal promoter control.
- **Pros:** genotype-agnostic in principle (could address deletion genotypes); single permanent insertion.
- **Cons:** HDR is inefficient in postmitotic cones; the 37–38 kb repeat structure and 96% homology make locus-specific cutting and HDR template design extremely challenging (gRNAs will multi-match the array); an endogenous-promoter knock-in will not express in **LCR-deletion** patients (the LCR is gone) → needs an exogenous promoter anyway, at which point augmentation (d) is simpler; cargo/sizing and integration-safety issues. **Not recommended as lead strategy.**

### (c) AAV gene augmentation (not CRISPR, but the comparator standard)
- **Concept:** AAV-PR2.1-OPN1LW (or OPN1MW) cDNA supplementation — the OPN1LW cDNA (~1.1 kb) fits AAV packaging easily with a cone-specific promoter.
- **Pros:** proven in three mouse models (DKO, C198R, all-cone TKO) with structural and functional rescue; genotype-agnostic for both major BCM classes (works even with a mutant opsin present); nearest clinical path given the achromatopsia-trial ecosystem; adult rescue demonstrated in NHP for opsin addition (Mancuso 2009).
- **Cons:** not curative of the underlying mutant allele; if the patient's mutant opsin is toxic/dominant-negative (plausible for several missense mutants per Zhu 2021; ER-retained misfolded protein may cause UPR/ER stress), augmentation may not halt degeneration; lifelong transgene expression required; subretinal delivery risk.

### (d) Combined knockdown + replacement (for toxic/dominant-negative mutant opsins)
- **Concept:** AAV delivers (i) an RNAi trigger (siRNA/shRNA/miRNA — e.g., miRNA target sites in the transgene 3′UTR) against the endogenous mutant opsin transcript and (ii) an RNAi-resistant (silent-mutation) WT OPN1LW/MW cDNA — the established "knock-down and replace" paradigm from dominant rhodopsin RP.
- **Pros:** removes potentially toxic ER-retained mutant protein (N94K/W177R/P307L class; possibly C203R if human cones show ER stress) while supplying WT opsin; mutation-class agnostic; keeps AAV packaging.
- **Cons:** more complex vector design; needs mutant-transcript-selective or pan-opsin knockdown with efficient replacement stoichiometry; C203R mutant protein is rapidly degraded (undetectable in the C198R mouse), so the knockdown arm may be unnecessary for that genotype — but is a prudent safeguard for human translation given unresolved dominant-negative behavior. (https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC8462070/)

**LIAVA/haplotype note (secondary CRISPR option):** the LIAVA-class causal variants are defined SNPs in exon 3 (e.g., c.532A>G, c.538T>G within the LIAVA haplotype). Editing the splice-disrupting SNP(s) back to the common (splicing-neutral) sequence is feasible with ABE/CBE/PE and would be genotype-specific — but the target population overlaps partly with mild high-myopia phenotypes, and multi-SP haplotypes complicate editing. Lower priority than C203R.

---

## 5. Recommended CRISPR target region(s) in BCM

**Primary point-mutation target: c.607 (codon 203, exon 4) of the remaining OPN1LW/OPN1LW-MW hybrid gene — the C203R codon (CGC→TGC correction; CBE or prime editing).**

Reasoning:
1. **Highest-yield point mutation in all inherited color-vision disease:** C203R is the single most common inactivating missense mutation of cone opsins; it causes BCM (severe) and also segregates in deuteranomaly/protanomaly. For ordinary red-green CVD there is *no* point mutation to correct (causation is copy-number/spectral-tuning, not sequence error), so **C203R is effectively the only point-mutation target of broad consequence across the color-vision spectrum**.
2. **Identical across genes/hybrids:** codon 203 and its c.607 context are conserved across OPN1LW, OPN1MW, and L/M hybrid genes — one guide/pegRNA design can serve all C203R genotypes (single hybrid gene, or multiple genes carrying C203R). Caveat: the array's high homology means any guide must be screened for off-target binding at other array copies; in the typical single-hybrid-gene patient this burden is minimal, and PE adds specificity.
3. **Editor-friendly chemistry:** the required correction is a C→T transition (CGC→TGC) — the native CBE product; ABEs are excluded; PE offers a bystander-free alternative with strong retinal precedents (rd1 PDE6B; RHO/USH2A humanized mice).
4. **Single-allele, single-cell-type context:** X-linked (one allele in males), expressed only in cones, under native LCR control once corrected — no promoter/transgene sizing problems.

**Caveats on "single best target":** C203R correction addresses only the point-mutation subgroup (~40% in the deepest phenotyped cohort; LCR deletions are ~40%+ and cannot be fixed by editing — they need augmentation). And it does nothing for exon-3 haplotype patients (splicing SNPs — separately editable). So: **C203R = best CRISPR point-mutation target in BCM (and across color-vision disease); AAV-PR2.1-OPN1LW augmentation remains the genotype-agnostic standard with which any CRISPR strategy must compete.**

**Suggested design priority:**
1. PE correction of c.607C>T (mutation-specific, bystander-free) — evaluate pegRNA designs around exon 4, dual-AAV delivery, cone-specific (PR2.1 or endogenous-driving) editor expression, treatment-window modeling.
2. CBE correction of c.607 as a simpler single-AAV-deliverable alternative if bystander profiling of the local sequence window is clean.
3. Augmentation (± knockdown-and-replace for missense genotypes) as the translational benchmark, not CRISPR.

---

## 6. Key papers

| Topic | Reference | URL |
|---|---|---|
| BCM gene therapy review (genetics, models, AAV, outcome measures) | Sechrest, Chmelik, Tan, Deng. Vision Res 2023;208:108221 | https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ |
| C203R mouse model + AAV rescue | Sechrest et al. JCI Insight 2024;9(2):e172834 | https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/ |
| Treatment-window molecular mechanisms (DKO vs C198R; AAV8-Y733F) | Nat Commun 2025 (PMC12644701) | https://www.nature.com/articles/s42003-025-09045-0 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC12644701/ |
| All-cone TKO model, 1- vs 5-month treatment | PMC13182793 (2025) | https://pmc.ncbi.nlm.nih.gov/articles/PMC13182793/ ; https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0332684 |
| DKO rescue (deletion genotype) | PMC9347391 | https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/ |
| SV landscape in 213 BCM families | PMC9271157 | https://pmc.ncbi.nlm.nih.gov/articles/PMC9271157/ |
| C203R structure/function (disulfide, ER retention) | Ostrer, Mol Vis 1997;3:16 | http://www.molvis.org/molvis/v3/a16/ |
| UK BCM families; C203R/R247X/P307L | Michaelides et al., Mol Vis 2009;15:1712 | http://www.molvis.org/molvis/v15/a91/ |
| OMIM 300821 (OPN1MW; C203R, c.648T>C old numbering, 2% population frequency) | OMIM | http://ncbi.nlm.nih.gov/omim/300821 |
| Orphanet BCM entry (c.607T>C) | Orphanet 16 | https://www.orpha.net/en/disease/detail/16 |
| Cone dysfunction syndromes (prevalence, acuity, genotype split 40/60) | PMC4717370 | https://pmc.ncbi.nlm.nih.gov/articles/PMC4717370/ |
| Missense-mutant disease mechanisms in vivo (dominant phenotypes) | Zhu et al., FASEB J 2021;35:e21927 | https://pmc.ncbi.nlm.nih.gov/articles/PMC8462070/ |
| K82E/P187S/M273K mechanisms | Front Neurosci 2024 | https://www.frontiersin.org/journals/neuroscience/articles/10.3389/fnins.2024.1368089/full |
| LIAVA splicing mechanism | Buena-Atienza et al., Sci Rep 2016 (srep28253) | https://www.nature.com/articles/srep28253 |
| Exon-3 haplotypes / high myopia | PMC10148663 | https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/ |
| Mild haplotype phenotype vs typical BCM | Mol Vis 2022;28:301 | http://www.molvis.org/molvis/v28/21/ |
| BCM vs CVD; adult primate trichromacy | Mancuso et al., Nature 2009;461:784 (PMC2782927); review PMC4208712 | https://pmc.ncbi.nlm.nih.gov/articles/PMC2782927/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/ |
| C203R in 15/36 cohort (outcome measure paper) | Mascio et al., TVST 2023;12:25 | https://openaccess.city.ac.uk/id/eprint/29916/1/i2164-2591-12-1-25_1674547467.12385.pdf |
| Prime editing in retina (rd1 rescue) | Nat Commun 2025;16:2394 | https://www.nature.com/articles/s41467-025-57628-6 |
| CBE/PE rescue of Pde6a mice | Adv Sci 2024 (review table) | https://www.cell.com/molecular-therapy-family/nucleic-acids/fulltext/S2162-2531(25)00176-3 |
| Prime Medicine dual-AAV retinal PE platform | ESGCT 2025 poster | https://primemedicine.com/wp-content/uploads/2025/10/ESGCT-Prime-Editing-in-Retinitis-Pigmentosa-Poster-1.pdf |
| Japanese BCM deletion families | Hum Genome Var 2016;2:16011 | https://www.nature.com/articles/hgv201611 |
| Cone opsin haplotypes review | PMC13297016 | https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/ |

---

## 7. Open questions

1. **Is C203R opsin toxic in human cones?** The C198R mouse degrades the mutant protein (undetectable), and augmentation alone sufficed in mice — but the ER-retained-misfolded-protein/UPR hypothesis is unresolved in humans, and several other opsin missense mutants show dominant toxicity (Zhu 2021). Determines whether augmentation alone is enough or knockdown+replace is required.
2. **Exact C203R genotype share of all BCM** varies by population (UK series: no LCR deletions; other cohorts ~40% deletions). Better population-level genotype frequency data would size the addressable population for c.607 editing.
3. **Editing efficiency achievable in human foveal cones** with CBE/PE via dual-AAV in vivo — no published cone-opsin editing data; all retinal PE precedents are rod photoreceptors (rd1, RHO, USH2A). Does the ~26–70% range seen in rods translate to cones, and within the degeneration window?
4. **Bystander-edit profile** around c.607 in the actual local sequence context of each patient's hybrid gene (sequence differs slightly between L, M, and hybrid backgrounds) — must be profiled per haplotype before CBE commitment.
5. **Guide specificity across the homologous opsin array** — patients with multiple opsin genes (some carrying C203R, others WT) risk on-target editing of WT copies; quantify mismatch discrimination.
6. **Human treatment window:** mice lose treatability by ~5 months; C203R humans retain foveal structure decades longer — where is the real cutoff, and does adult correction/augmentation regenerate outer segments in humans as it does in mice?
7. **Could exon-3 splice-SNP editing (LIAVA class) be a second CRISPR indication?** Which single SNP is the minimal splice-disrupting edit, and does correcting it restore full-length transcript in vivo?
8. **Off-target risk of editing within Xq28** segmental-duplication-rich region — genome-wide and on-array off-target mapping needed for any proposed guide.
9. **Spectral outcome after correction:** corrected hybrid genes yield one opsin class — is restored (dichromatic→trichromatic) discrimination the realistic endpoint, and which outcome measures (Mascio 2023 color-vision, Semenov 2020 reading performance) should gate success?
