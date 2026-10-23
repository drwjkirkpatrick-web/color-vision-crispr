# Research Dossier: Deuteranopia / Deuteranomaly (Deutan Red-Green Color Blindness)

**Project:** color-vision-crispr — computational CRISPR research, in-silico literature and design only.
**Compiled:** October 22, 2026. All claims sourced; URLs in-line and in §6.

---

## 1. Disease Overview & Prevalence

Red-green color vision deficiency (CVD) is the most common single-locus genetic disorder [Mancuso 2009, Nature 461:784 — https://www.nature.com/articles/nature08401]. It is X-linked recessive, arising from loss or dysfunction of the L- or M-wavelength cone opsins encoded at Xq28.

- Overall red-green CVD affects ~8% of males and ~0.4–0.5% of females in the US (https://disorders.eyes.arizona.edu/category/clinical-features/anomalous-color-vision).
- **Deutan** CVD (S + L cones functional; loss of M-pigment function) is the most common form, ~6% of males (https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/); other estimates put deutan defects at ~1 in 12 males overall for red-green defects combined (https://pmc.ncbi.nlm.nih.gov/articles/PMC9646815/).
- Deutan has two severities:
  - **Deuteranomaly** (anomalous trichromacy): M cones present but pigments spectrally shifted/dysfunctional — ~5% of Caucasian males; the single most common CVD subtype (https://disorders.eyes.arizona.edu/category/clinical-features/anomalous-color-vision).
  - **Deuteranopia** (dichromacy): no functional M cone — ~1% of Caucasian males (same source).
- Red-green CVD with normal acuity and cone ERG affects ~1 in 12 males and ~1 in 200 females (long-read clinical study, https://www.nature.com/articles/s41525-022-00334-9). Females are rarely affected because two X chromosomes must both carry the defect.
- Vision is otherwise normal: visual acuity and cone ERG are intact; the deficit is purely spectral (https://pmc.ncbi.nlm.nih.gov/articles/PMC9646815/). This makes deutan a uniquely attractive editing target — the cone cells are healthy and abundant; only the pigment is wrong or absent.

## 2. Molecular Genetics

### 2.1 Array structure at Xq28

- OPN1LW (L/"red" opsin, λmax ≈ 560 nm) and OPN1MW (M/"green" opsin, λmax ≈ 532 nm) sit in a **head-to-tail tandem array on Xq28**, sharing >96% nucleotide identity over ~40 kb (https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/).
- Normal trichromats have a **single OPN1LW gene in the most upstream position followed by one or more OPN1MW genes** (https://en.wikipedia.org/wiki/OPN1LW; https://omim.org/entry/300821).
- The **locus control region (LCR)** sits 3.1–3.7 kb 5′ of the array and is a master switch: it is essential for cone-specific expression of the genes and for their **segregated expression in separate cones** (https://omim.org/entry/300821). In an array of 3–4 genes, **only the two most proximal (first and second) genes are expressed**; downstream copies are silenced by promoter competition for the LCR (https://disorders.eyes.arizona.edu/category/clinical-features/anomalous-color-vision; https://www.blueconemonochromacy.org/wp-content/uploads/2011/08/Deeb_2004.pdf).

### 2.2 Pathogenic mechanism: unequal crossover

- The head-to-tail arrangement and ~96% identity make the array prone to mispairing during male meiosis, producing **unequal crossing-over** (https://openaccess.city.ac.uk/id/eprint/23584/1/Photoreceptors%20Color%20Vision_submitted%20to%20CRO.pdf).
- A crossover **between genes** deletes a gene from one chromosome and duplicates it on the other; a crossover **within a gene** creates a **hybrid gene** splicing L and M segments into a single 3′-or-5′ chimeric opsin (https://openaccess.city.ac.uk/id/eprint/23584/1/Photoreceptors%20Color%20Vision_submitted%20to%20CRO.pdf; MedlinePlus: https://medlineplus.gov/genetics/gene/opn1mw/).
- Phenotype logic (https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/):
  - **Deuteranopia**: first and second genes specify L pigments with identical λmax, or the array encodes only an L pigment (complete M-gene deletion); also OPN1LW + an M gene carrying the nonfunctional **LIAVA exon-3 haplotype** (M cones devoid of pigment).
  - **Deuteranomaly**: first and second genes encode L-like pigments differing in λmax (a 5′ hybrid in position 1 or 2 plus a distinct second pigment). If a 5′ hybrid occupies the **second** array position, the result is deutan; if it occupies the third or more distal position (silenced), color vision is normal (https://www.blueconemonochromacy.org/wp-content/uploads/2011/08/Deeb_2004.pdf).

### 2.3 Fraction of deutan cases: hybrid vs deletion vs point mutation

- Deeb et al. 1992 (AJHG 51:687 — https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1682812/), 41 deutan subjects:
  - **13/41 (~32%)** complete green-pigment gene deletion (array = single L gene).
  - **25/41 (~61%)** arrays carrying **5′ green–red hybrid genes** (7 without any normal M gene — usually deuteranopia; 18 with one or more normal M genes downstream — usually deuteranomaly).
  - Remainder: rare 5′ green–red–green hybrids; **point mutations are a small minority** (the study's "great majority" summary: deletions or 5′ hybrids).
- Japanese cohort (Jpn J Ophthalmol 44:596 — https://www.nichigan.or.jp/Portals/0/JJO_PDF/044060596.pdf): of 34 deutan subjects, 16 (47%) had complete M-gene deletion (13 deuteranopia, 3 deuteranomaly), 27/43 total subjects carried hybrid genes.
- Conclusion for design: **the overwhelming majority of deutan cases are structural — hybrid genes or deletions — not point mutations** (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1682812/). Any CRISPR strategy dominated by point-mutation correction will miss most patients.

### 2.4 The five spectral-tuning codons (L vs M)

| Codon | Exon | Amino acid change | λmax effect |
|---|---|---|---|
| 180 | 3 | Ser ↔ Ala (S180A) | −5 to −7 nm; ~30% frequency in populations, common polymorphism (https://sites.socsci.uci.edu/~kjameson/VerrelliEtAl2008.pdf) |
| 230 | 4 | Ile ↔ Thr | ~−5 nm, smaller shift (http://www.molvis.org/molvis/v26/158/mv-v26-158.pdf) |
| 233 | 4 | Ala ↔ Ser | ~−5 nm, smaller shift (same) |
| 277 | 5 | Tyr ↔ Phe (Y277F) | ~−7 to −10 nm (https://sites.socsci.uci.edu/~kjameson/VerrelliEtAl2008.pdf) |
| 285 | 5 | Thr ↔ Ala (T285A) | ~−14 to −17 nm (same) |

- L pigment = S180/Y277/T285 (λmax 560 nm); M pigment = A180/F277/A285 (λmax 532 nm) (Neitz & Neitz 2011, cited in https://trepo.tuni.fi/bitstream/handle/10024/159755/LiljaOlivia.pdf?sequence=2&isAllowed=y).
- **Codons 277 and 285 (exon 5) determine L vs M class**; together they produce a 16–24 nm shift separating the two pigment classes (https://jamanetwork.com/journals/jamaophthalmology/fullarticle/413200). Exon 3 (codon 180) and exon 4 (230, 233) make smaller shifts; hybrid genes in which exons 3, 4, or 5 were exchanged produce pigments with intermediate peaks, confirming exon 5 dominance (Merbs & Nathans, cited in https://www.ncbi.nlm.nih.gov/pmc/articles/PMC44379/pdf/pnas01137-0556.pdf).
- Design implication: **converting a hybrid gene's exons 3–5 spectral residues back to the M set (A180, T230, S233, F277, A285) or the L set requires only a handful of base changes**, several of which are A↔G / T↔C / G↔A transitions potentially addressable by base editing.

## 3. State of the Art: Restoring Trichromacy in Adults

### 3.1 "Ma et al. 2019 Nature" — could not be verified as described

The task brief referenced a "Ma et al. 2019 Nature knock-in of OPN1LW into the Opn1mw locus in adult mice restoring trichromatic vision." **After extensive searching (PubMed eutils queries across 2019 opsin/color-vision/knock-in terms, and multiple web searches), no such Nature paper exists.** The premise appears to conflate several real works:

- **Smallwood et al. 2003 / Jacobs et al. 2007** — transgenic (not CRISPR) knock-in mice in which the endogenous mouse M-opsin gene was replaced with human L opsin; heterozygous females (X-inactivation mosaic) showed weak but real red-green color discrimination (https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/; https://www.nature.com/articles/nrg2106).
- **Ma X. et al. 2022, Human Gene Therapy 33:708–718** — AAV gene *augmentation* (not knock-in editing) of human L-opsin in Opn1mw−/−/Opn1sw−/− mice (https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/).
- **Suzuki et al. 2016, Nature 539:114** — CRISPR-Cas9 **homology-independent targeted integration (HITI)**, the likely source of the "homology-independent targeting" phrasing; demonstrated in retinal cells (rat RP model), not color vision (https://www.nature.com/articles/nature20565).

This dossier treats the closest genuine analogues (below) as the state of the art.

### 3.2 Mancuso et al. 2009, Nature 461:784–787 — adult monkeys (verified)

- Adult squirrel monkeys (*Saimiri sciureus*) red-green color-blind since birth (missing L-opsin; a protan model) received **rAAV2/5 carrying a human L-opsin gene under the L/M-opsin enhancer + promoter (pR2.1)** by subretinal injection (PDF: http://www.neitzvision.com/research/publications/publications/2009-Mancuso-Gene_therapy_for_red-green_colour_blindness-Nature.pdf).
- The transgene was expressed in **~15–30% of endogenous M cones**, shifting their spectral sensitivity to long wavelengths and creating two distinct M/L populations — the receptoral basis for trichromacy (https://www.nationalgeographic.com/science/article/gene-therapy-gives-full-colour-vision-to-colour-blind-monkeys).
- **~20 weeks post-injection**, behavioral thresholds for blue-green and red-violet stimuli dropped to trichromatic levels (~0.08 units in u′v′ space). Key conclusion: **trichromacy can arise in adulthood from a single added cone class — no early developmental critical period is required** (https://www.nature.com/articles/nature08401).
- Adult mouse analogy: knock-in female mice carrying human L opsin at the M locus also gained (weak) red-green discrimination, confirming adult brain plasticity in mice (https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/).

### 3.3 AAV augmentation data relevant to deutan

No registered human clinical trial for deutan CVD was found in this search. The strongest preclinical data are in opsin-deficient mouse models (functionally analogous, since deutan cones are healthy but M-pigment-less):

- **Ting/? — Deng et al. 2017, Sci Rep 7:6976** (https://www.nature.com/articles/s41598-017-06982-7): Opn1mw−/− mice (only S-opsin, a BCM model); AAV5-delivered recombinant M-opsin rescued M-cone ERG function; cones without opsin remained viable; treatment effective in adults up to ~3 months of age; expression persisted >7 months. Explicitly notes the primate result as independent support.
- **Deng et al. 2018, Mol Vis 24:17–28**: AAV5 human OPN1LW or OPN1MW restored outer-segment morphogenesis and M-cone function in Opn1mw−/− mice (cited in https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/).
- **Deng et al. 2019, IOVS 60:3644–3651** (https://pmc.ncbi.nlm.nih.gov/articles/PMC6716949/): AAV5 human L-opsin rescued M-cone function and outer segments even in **aged (15-month) Opn1mw−/− mice** — separating outer-segment loss from cone death and showing gene augmentation can work in old, structurally degraded cones (PMID 31469404).
- **Ma X. et al. 2022, Hum Gene Ther 33:708–718** (https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/): AAV5 PR2.1-hOPN1LW rescued cone function in DKO mice when treated ≤2 months; rescue markedly reduced at older ages.
- **Treatment-window limit**: efficacy declines when treatment starts at ≥5 months in BCM mouse models (https://www.nature.com/articles/s42003-025-09045-0; https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/). Notably, this aging effect is documented in BCM (cones degenerating); in deutan-phenotype mice (healthy cones, wrong pigment) the Mancuso primate result shows adult treatment works — timing constraints are likely milder for deutan.
- **Böhm et al.** — dCas9-VPR CRISPRa with dual split-intein AAV reactivated *Opn1mw* in rod photoreceptors in an RP mouse model, improving retinal function — proof that CRISPRa of opsin genes works in vivo via dual-AAV delivery (https://pmc.ncbi.nlm.nih.gov/articles/PMC8840918/).

## 4. CRISPR Strategy Options for Deutan

### (a) Knock-in of functional M-opsin cDNA at the array locus

- **Pros**: Directly replaces a defective first/second gene; endogenous LCR/promoter regulation retained; cDNA is small (~1.1 kb coding sequence — 364 aa — comfortably within AAV's ~4.7 kb capacity, so a CRISPR knock-in could even be packaged with a promoter). Knock-in mice with a human opsin replacing the M locus demonstrated the concept (§3.1). HITI (https://www.nature.com/articles/nature20565) enables knock-in in non-dividing photoreceptors without homology arms.
- **Cons**: Requires DSB + integration — inefficient in postmitotic cones; risk of array disruption at a hyper-recombinogenic locus (the array already recombines pathologically); dual-AAV cargo split needed if using larger payloads; indel/NHEJ byproducts at Xq28 hard to characterize; most advanced knock-in methods (~40–45% in dividing cells — https://www.nature.com/articles/s41467-025-67239-w) have not been demonstrated in retina.

### (b) Prime editing of hybrid-gene exons 3–5 back to an M (or L) spectral sequence

- **Pros**: Targets the *actual expressed* hybrid gene in position 1 or 2 — the causal lesion in ~61% of deutan cases (§2.3). DSB-free and donor-free; installs all 12 base substitutions plus small indels; no bystander edits (https://www.pnas.org/doi/10.1073/pnas.2210104119). Restoring the M identity of the second gene converts deuteranomaly → normal-like trichromacy; restoring L identity on the first gene with a distinct second pigment achieves anomalous-trichromacy → normal correction. Prime editing has already been demonstrated in mouse retina (Pde6b^rd10, dual-AAV PESpRY, ~41% retinal / ~76% transduced-cell editing: https://pmc.ncbi.nlm.nih.gov/articles/PMC10035435/).
- **Cons**: A hybrid-to-ortholog conversion can involve multiple dispersed edits across exons 3–5 (one pegRNA per edit region — multiplexing raises complexity and delivery load); PE cargo (editor + pegRNA) needs dual AAV; long-read sequencing (https://www.nature.com/articles/s41525-022-00334-9) is required to map each patient's hybrid breakpoint for personalized guide design; editing efficacy of multi-nucleotide rewrites in retina unproven.

### (c) Base / prime editing of the spectral codons only

- **Pros**: If only codon-level changes are needed (e.g., a 5′ hybrid that differs from M at just positions 180/230/233/277/285), base editors handle transitions (C→T, G→A, A→G, T→C — https://pmc.ncbi.nlm.nih.gov/articles/PMC9456398/) at very high efficiency with low off-target rates; single-AAV feasible for compact editors (ABE8e, or enCas12a/Cas12f systems); Smaller pegRNA burden than (b) when the hybrid retains M-like sequence except a few codons.
- **Cons**: Only transitions addressable (A→C, C→G etc. need prime editing); bystander deamination within the activity window (https://www.pnas.org/doi/10.1073/pnas.2210104119); note that the key L→M codon rewrites are not single transitions — Y277F requires A→T (transversion) and S180A requires two base changes per codon — so a full five-codon L→M conversion generally exceeds base-editing scope and needs prime editing; base editing is best reserved for hybrid haplotypes needing only one or two transition-compatible changes; must deliver to the *expressed* proximal gene only, requiring guide specificity against a >96%-identical array — but this also applies to (b).
- Note: guide-discrimination challenge is real but tractable — sequence differences between L and M genes concentrate in exons 3–5 and introns at recombination breakpoints (https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/).

### (d) CRISPRa reactivation of downstream intact OPN1MW copies

- **Pros**: No DNA cutting at all — safest mechanistically. Most deutans retain one or more **intact, spectrally normal OPN1MW genes downstream** (18/25 hybrid-case subjects in Deeb 1992 had normal M genes — §2.3), silenced only by LCR promoter competition for the first two positions. dCas9-VPR activation has precedent in opsin genes in vivo (Böhm et al. — §3.3), via dual split-intein AAV (https://pmc.ncbi.nlm.nih.gov/articles/PMC8840918/). CRISPRa is gene-size-independent (https://pmc.ncbi.nlm.nih.gov/articles/PMC8840918/).
- **Cons**: Reactivating a downstream gene requires overriding the LCR's promoter-preference mechanism — the LCR naturally contacts only the proximal promoters; sgRNAs would need to target the downstream gene's promoter with an activator, and whether that yields cone-segregated expression (rather than co-expression with L in the same cone) is unknown; sustained dCas9-VPR expression raises immunogenicity/durability questions; single-vector AAV can't fit dCas9-VPR (dual-AAV required — https://pmc.ncbi.nlm.nih.gov/articles/PMC8840918/).

### (e) Gene augmentation via AAV (add functional M-opsin cDNA)

- **Pros**: The only approach with primate proof-of-concept (Mancuso 2009 — added a third pigment class to adult dichromats, restoring trichromatic behavior — §3.2); strong mouse data with human L/M-opsin cDNA (Deng 2017/2018/2019; Ma 2022 — §3.3); M-opsin cDNA (~1.1 kb) plus a cone promoter (PR2.1) fits a **single AAV5** easily (https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/); works on *every* deutan genotype (hybrid, deletion, or point mutation) without patient-specific genotyping; adult treatment demonstrated in primates.
- **Cons**: Not CRISPR (no permanent genomic edit — episomal AAV expression, though retinal AAV expression is durable); transgene driven by a heterologous promoter (PR2.1), not the endogenous LCR → expression in a random subset of cones rather than a properly segregated M-cone population (in Mancuso 2009, 15–30% of M cones became L-like — a non-native mosaic); subretinal injection is focal; immune response to AAV capsid/transgene possible.

## 5. Recommended Best Target Region(s) for CRISPR in Deutan

**Primary recommendation — the expressed (proximal) hybrid gene, exons 3–5, edited back to an M or L spectral identity via prime/base editing (options b + c):**

Reasoning:
1. **It hits the actual lesion in the majority of patients.** ~61% of deutan cases carry 5′ green–red hybrids and ~32% carry M-gene deletions (§2.3); among hybrid cases, most deuteranomaly results from the expressed hybrid gene in position 1 or 2 plus a second differing pigment (§2.2). Restoring the second gene to a clean M sequence (A180/T230/S233/F277/A285) converts the array back to a normal L-first/M-second configuration — the physiological arrangement.
2. **The edit is small and well-defined.** The L↔M distinction reduces to five codons, with exon 5 (277, 285) decisive (§2.4); several required changes are transitions amenable to base editing, and all are within prime-editing scope. This is a far smaller rewrite than delivering or integrating a whole cDNA.
3. **Targeting specificity is manageable.** Only the first two array genes are expressed (§2.1), so guides can be designed against the expressed proximal genes; L/M sequence divergence at exons 3–5 and hybrid breakpoints provides discriminator sites (§2.2, §4c).
4. **Precedent in the target tissue.** Prime editing works in mouse retina (PESpRY dual-AAV, rd10 — §4b); CRISPRa of opsin genes works in vivo (§3.3).

**Secondary recommendation — CRISPRa of downstream intact OPN1MW copies (option d)** as the safest follow-on strategy for patients confirmed (by long-read sequencing, https://www.nature.com/articles/s41525-022-00334-9) to carry downstream intact M genes. No DSB risk; needs validation that LCR-circumventing activation yields cone-segregated expression.

**Fallback / benchmarking comparator — AAV gene augmentation (option e)**, which is not CRISPR but is the only approach with primate efficacy data (Mancuso 2009) and works across all deutan genotypes; any CRISPR design should be benchmarked against it.

**Deletion cases (deuteranopia, single-gene arrays)** are poorly served by all editing strategies and are the natural use case for augmentation (e) or knock-in (a) — note that knock-in at the recombination-prone array is mechanistically risky (§4a).

## 6. Key Papers

| Topic | Reference | URL |
|---|---|---|
| Primate gene augmentation (landmark) | Mancuso et al. 2009, *Nature* 461:784–787 | https://www.nature.com/articles/nature08401 |
| — full PDF | Neitz Vision mirror | http://www.neitzvision.com/research/publications/publications/2009-Mancuso-Gene_therapy_for_red-green_colour_blindness-Nature.pdf |
| Genotype–phenotype (hybrid/deletion fractions) | Deeb et al. 1992, *AJHG* 51:687–700 | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1682812/ |
| Array structure, recombination, deutan logic | Intermixing review (2021) | https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/ |
| LCR position/function | OMIM 300821 (OPN1MW) | https://omim.org/entry/300821 |
| Hybrid position → phenotype | Deeb 2004 review | https://www.blueconemonochromacy.org/wp-content/uploads/2011/08/Deeb_2004.pdf |
| Spectral-tuning codons (180/230/233/277/285) | JAMA Ophthalmol review | https://jamanetwork.com/journals/jamaophthalmology/fullarticle/413200 |
| — codon shift magnitudes | Molecular Vision 2020, v26:158 | http://www.molvis.org/molvis/v26/158/mv-v26-158.pdf |
| — Neitz three-site rule values | Neitz & Neitz 2011 (via Tuni thesis) | https://trepo.tuni.fi/bitstream/handle/10024/159755/LiljaOlivia.pdf |
| AAV M-opsin rescue in Opn1mw−/− mice | Deng et al. 2017, *Sci Rep* 7:6976 | https://www.nature.com/articles/s41598-017-06982-7 |
| Aged-mouse AAV rescue | Deng et al. 2019, *IOVS* 60:3644 | https://pmc.ncbi.nlm.nih.gov/articles/PMC6716949/ |
| AAV DKO model (Ma X.) | Ma et al. 2022, *Hum Gene Ther* 33:708 | https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/ |
| Treatment-window limit | 2025, *Commun Biol* | https://www.nature.com/articles/s42003-025-09045-0 |
| BCM gene therapy review | 2023 review | https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/ |
| HITI (homology-independent knock-in) | Suzuki et al. 2016, *Nature* 539:114 | https://www.nature.com/articles/nature20565 |
| Prime editing in retina (PESpRY, rd10) | Qin et al. 2023 (review: PMC10035435) | https://pmc.ncbi.nlm.nih.gov/articles/PMC10035435/ |
| CRISPRa of Opn1mw in vivo | Böhm et al. (review PMC8840918) | https://pmc.ncbi.nlm.nih.gov/articles/PMC8840918/ |
| Long-read diagnostics of the array | 2022, *HGADO* | https://www.nature.com/articles/s41525-022-00334-9 |
| Knock-in mice (human L at M locus) | Smallwood 2003 / Jacobs 2007 (review) | https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/ |
| Prevalence / clinical features | Univ. Arizona Hereditary Ocular Diseases | https://disorders.eyes.arizona.edu/category/clinical-features/anomalous-color-vision |
| MedlinePlus OPN1MW (patient-level) | — | https://medlineplus.gov/genetics/gene/opn1mw/ |

## 7. Open Questions

1. **Exact hybrid-breakpoint distribution in the general deutan population** — Deeb 1992 (n=41) and a Japanese cohort (n=34) are small; modern long-read sequencing of large cohorts (cf. https://www.nature.com/articles/s41525-022-00334-9) is needed to size each strategy's addressable population.
2. **Prime-editing multiplex feasibility in cones** — can a single dual-AAV PE system carry 2–3 pegRNAs to rewrite multiple spectral codons (exons 3 + 5) in one treatment, at what efficiency?
3. **LCR dynamics under CRISPRa** — does activating a downstream OPN1MW promoter produce a properly segregated M-cone population, or co-expression with L (which would not create a new color channel)? Requires in-vivo testing in a deutan mouse model.
4. **Base-editor transition coverage** — for each patient's hybrid haplotype, what fraction of the required codon changes are base-editor-accessible transitions vs. requiring prime editing? (Case-by-case; needs the five-codon allele inventory.)
5. **Off-target discrimination in a 96%-identical array** — guide specificity across the tandem repeat and risk of editing the silenced OPN1LW; needs targeted off-target screening at Xq28.
6. **Durability and immunogenicity** of dCas9-VPR or PE expression in retina over years (AAV data span months in mice; primate behavioral rescue stable over years post-Mancuso but not formally published as long-term).
7. **Does the "Ma et al. 2019 Nature" reference in the project brief correspond to a paper not indexed in PubMed?** Multiple database searches (PubMed eutils; web search) found no such knock-in paper; closest matches are Jacobs 2007 (transgenic), Ma X. 2022 (AAV), Suzuki 2016 (HITI). Project should re-verify the citation before internal documents propagate it.
