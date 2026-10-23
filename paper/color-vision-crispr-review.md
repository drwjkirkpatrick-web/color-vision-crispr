# CRISPR Target Selection Across the Color-Vision Disease Spectrum: A Computational Review of Opsin Genetics, Editing Feasibility, and Translational Reality

**Walker, ND — with Hermes Agent (computational research assistant)**

*Computational research review accompanying the `color-vision-crispr` repository. This work is explicitly in-silico: it is a literature synthesis and design-space analysis only. It is not medical advice, no clinical application is proposed, no wet-lab protocols are described, and clinical decisions remain with the treating clinician.*

---

## Abstract

Red–green color vision deficiency (CVD) is the most common inherited vision condition, affecting approximately 1 in 12 males,[128] yet it remains entirely untreated in humans. This review synthesizes the molecular genetics of the five major color-vision disease classes — deutan, protan, blue cone monochromacy (BCM), tritanopia, and achromatopsia — and maps them against the current CRISPR engineering constraints for retinal genome editing.[unverified] The central finding is that "correct the mutation" resolves into three structurally different problems: most red–green CVD is caused by large rearrangements (5′ hybrid genes and deletions) in the >96%-identical `OPN1LW`/`OPN1MW` tandem array on Xq28, not by point mutations;[194][120] a narrow but well-defined set of point lesions is nonetheless precisely editable, led by the C203R (c.607T>C) missense mutation that is the most common inactivating missense change in human cone opsins.[97] We rank candidate targets: first, cytosine-base-editor correction of C203R in BCM; second, prime-editing conversion of hybrid-gene exon 5 spectral codons for protan/deutan CVD; third, splice rescue of the LIAVA exon-3 haplotype; with CRISPRa reactivation and AAV opsin augmentation as comparators. Achromatopsia, in contrast, is classified as "augmentation-watched" rather than a CRISPR target.[unverified] The only in-vivo human retinal CRISPR experience to date (EDIT-101 for CEP290-LCA10) demonstrated safety but limited efficacy and suspended enrollment,[93] and no human trial of any kind exists for red–green CVD. All recommendations herein are computational design hypotheses requiring extensive validation.[unverified]

## 1. Introduction

Human trichromatic color vision depends on three cone photopigments: the long-wavelength (L, "red") opsin encoded by `OPN1LW`, the middle-wavelength (M, "green") opsin encoded by `OPN1MW`, and the short-wavelength (S, "blue") opsin encoded by `OPN1SW` on chromosome 7.[82] The L and M genes occupy a head-to-tail tandem array at Xq28, sharing greater than 96% nucleotide sequence identity over their entire ~40 kb length.[120] An upstream locus control region (LCR) drives expression such that only the first two genes in the array are expressed, and each cone expresses only one opsin type.[1]

Red–green CVD — loss or dysfunction of the L or M pigment — affects approximately 1 in 12 males and 1 in 200 females with otherwise normal visual acuity and normal cone electroretinogram.[128] Deutan defects, mediated by S and L cones, are the most common form at about 6% of males.[120] Although traditionally framed as a benign condition, congenital color blindness carries measurable occupational, educational, and quality-of-life burden, and the 2009 demonstration that a single added opsin class can produce trichromatic color vision in adult red–green color-deficient primates established that the deficit is correctable in principle even in adulthood.[177]

The disease spectrum spans two very different biological situations.[unverified] Simple red–green CVD (deutan/protan) is a *functional spectral-tuning* defect in a structurally healthy cone mosaic. Blue cone monochromacy (BCM) is a *degenerative* cone disease in which L- and M-cone function is absent from birth and the affected cones slowly degenerate, causing low vision and nystagmus rather than a pure color-perception deficit.[1] Achromatopsia removes all cone function and is the subject of five active or completed gene-therapy trials.[11] Tritanopia, the rare S-cone defect, is autosomal dominant and comparatively neglected translationally.[82] Any CRISPR strategy must therefore be selected per disease class, because the causal mutation classes — and hence the editability calculus — differ fundamentally between them.

## 2. Molecular mechanisms by disease class

### 2.1 Deutan (deuteranopia and deuteranomaly)

Deutan CVD arises when the M-cone position of the array encodes an L-like pigment or no functional M pigment at all.[120] The dominant mechanism is structural, established in the classic genotype–phenotype study of 41 deutan subjects, in which the great majority of defects were associated with either green-pigment gene deletion or the formation of 5′ green–red hybrid genes;[194] within that cohort, roughly 61% of arrays carried 5′ hybrid genes and about 32% carried complete M-gene deletions.[194] Point mutations are a small minority of deutan causation. The mechanism is unequal crossing-over during male meiosis between the >96%-identical array copies.[120] A subset of deutan cases arises from an `OPN1MW` gene carrying the LIAVA exon-3 haplotype, in which the LIAVA, LVAVA, MIAVA, and LIAVS haplotypes are associated with different degrees of exon 3 skipping, leaving the cone pigment-less but structurally viable.[120]

### 2.2 Protan (protanopia and protanomaly)

Protan defects mirror deutan mechanisms in the opposite direction: the first (L-position) gene is deleted, or — dominantly — replaced by a 5′L–3′M hybrid gene whose exon 5 encodes M-class spectral determinants, yielding a pigment with green-like sensitivity in the "red" cone position.[120] The LIAVA splice haplotype of `OPN1LW` also causes protanopia through complete exon-3 skipping; in vitro, pathogenic haplotypes including LIAVA and LVAVA produced absent or minute amounts of correctly spliced transcripts.[191] Critically for therapy design, simple protanopia shows a structurally intact cone mosaic — the "red" cones are present but empty or mis-specified — whereas the LIAVA splice phenotype is associated with cone dysfunction and high myopia.[unverified]

### 2.3 Blue cone monochromacy

BCM (OMIM #303700) is an X-linked cone dysfunction syndrome in which both L- and M-cone function is absent from birth, leaving photopic vision to S cones and rods; it affects approximately 1 in 100,000 people worldwide [1]. Two mechanisms dominate: large deletions of the LCR (~40% of cases), and a single remaining opsin gene inactivated by a subsequent point mutation (~60% of cases) [106]. The flagship point lesion is C203R: the most common missense mutation in L- and M-opsin genes, substituting the cysteine at position 203 by arginine [97]. In a deeply phenotyped series of 36 molecularly confirmed BCM patients, 21 had large structural variants and 15 carried the p.C203R missense mutation in single or multiple array genes [67]. C203 participates in a crucial disulfide bond required for proper opsin folding;[2] when disrupted, the misfolded pigment is retained and degraded, and the affected cones progressively lose outer-segment structure.[2] By the standard genetic code, the mutant allele carries CGC (Arg) at codon 203 in place of the wild-type TGC (Cys) — a c.607T>C transition on the coding strand [analysis; see also [97]].

### 2.4 Tritanopia and tritanomaly

Tritan defects map to `OPN1SW` (7q32.1), are autosomal dominant, and are caused by a short catalog of missense alleles plus one splice variant.[82] The literature catalog comprises L56P, G79R, T190I, S214P, P264S, and R283Q, plus an intron 3 +5delG splice-site deletion.[97] Mechanistic data are thin: the splice allele produces a frameshifted transcript and a predicted haploinsufficiency mechanism, with heterozygotes carrying roughly half the normal amount of S-opsin protein, and its minor allele frequency is estimated at 0.132% in large population studies.[117] For the missense alleles, dominant-negative misfolding is hypothesized by analogy to L/M-opsin disease but has never been directly demonstrated [unverified].

### 2.5 Achromatopsia

Achromatopsia (ACHM) is an autosomal-recessive, non-progressive-at-presentation cone disorder affecting approximately one in 30,000 people.[122] Up to 90% of patients carry mutations in `CNGA3` or `CNGB3`, the alpha and beta subunits of the cone cyclic nucleotide-gated channel.[122] Within `CNGB3`, the recurrent 1-bp deletion c.1148delC accounts for over 70% of all CNGB3 mutant alleles.[174] The mutation landscape is therefore dominated by truncating variants spread across six genes — mechanistically unfavorable for mutation-specific editing and favorable for gene augmentation.

## 3. The CRISPR design space for the opsin array

Several engineering realities shape every design in this locus.[unverified]

**Editor choice.** The required edits span transition-class base changes (C203R correction; LIAVA c.532 reversion), transversion-class recoding (the exon-5 Y277F/A285T conversions that define M→L spectral identity [analysis based on the L/M codon identities]), and a 1-bp re-insertion (tritan splice allele). Cytosine and adenine base editors convert one nucleotide to another without generating double-strand breaks (DSBs) in the target DNA,[74] making them the mechanistically preferred class for the transition-class lesions in post-mitotic cones. Prime editing extends this precision to all small changes but at a steep delivery cost (below).

**AAV delivery limits.** Retinal in-vivo delivery is AAV-bound, and the limited packaging capacity of rAAV vectors (<4.7 kb) remains a significant challenge for in-vivo delivery of CRISPR components.[181] Full-length prime editors exceed this limit and must be split across dual AAV vectors, with the co-transduction requirement imposing a substantial efficiency penalty. Compact single-AAV architectures exist — for example, a size-minimized AAV backbone delivering the SaABE8e adenine base editor (3.9 kb) with guide RNA and all regulatory elements in a single AAV of ≤~5.0 kb including ITRs[187] — but these are restricted to A·T→G·C edits and carry wide bystander-editing windows [unverified].

**DSB avoidance.** In post-mitotic photoreceptors, nuclease-induced DSBs heal by NHEJ, producing heterogeneous indels and creating a risk of AAV genome integration at a locus that is already pathologically recombination-prone.[74] Base and prime editors avoid DSBs entirely[74] — a decisive advantage at Xq28, where a DSB-triggered rearrangement could convert a functional defect into a degenerative one. In-vivo retinal prime editing has been demonstrated in the rd1 mouse: a dual-AAV PE system targeting the PDE6B Y347X mutation achieved an editing efficiency of 26.47 ± 13.35% with negligible off-target effects.[183]

**Allele and copy specificity.** The hardest problem specific to this locus: any guide targeting the expressed proximal gene must be screened against every copy of a tandem array whose members share >96% identity over ~40 kb.[120] Editing a silenced downstream copy is probably phenotypically silent, but editing the *wrong expressed* copy would change the patient's pigment class rather than correct it [inference; unverified]. Per-patient long-read haplotyping of the full array is a prerequisite for any guide design [design principle; unverified].

## 4. Candidate targets, ranked

### 4.1 First — C203R correction in BCM (cytosine base editing)

C203R is the only common, single-base, precisely-editable lesion in the entire color-vision field.[unverified] The correction is a C→T transition on the coding strand (CGC→TGC, restoring Cys-203) [analysis], exactly the native product of a cytosine base editor and outside the scope of adenine base editing;[74] prime editing is the bystander-free alternative. The biology is favorable: the C198R mouse model (the murine equivalent of human C203R) phenocopies the human disease, and AAV opsin augmentation rescued cone structure and function in that model, proving that corrected cones are rescue-competent.[2] The edit repairs the endogenous gene under native LCR regulation, in an X-linked context requiring correction of only one allele in affected males.[1] The addressable population is narrow — the point-mutation subgroup of a 1-in-100,000 disease, roughly 42% of one deeply phenotyped cohort[67] — but this remains the strongest precision-to-biology fit of any candidate.

### 4.2 Second — hybrid-gene exon 5 conversion by prime editing (protan/deutan)

Codons 277 and 285 in exon 5 encode amino acids that determine whether the specified pigment is L or M.[46] Converting a 5′ hybrid gene's exon 5 back to M identity (Y277F, T285A) in the second array position would restore a normal L-first/M-second configuration for most deutan cases; the reverse conversion addresses protan hybrids. Because the Y277F change requires an A→T transversion [analysis], it lies outside base-editor scope and mandates prime editing — hence dual-AAV delivery with the efficiency penalty described above, and a hard requirement for per-patient hybrid-breakpoint mapping.[unverified] This is the largest-population target (it addresses the causal lesion in the majority of deutan and protan patients[194]) but carries the hardest delivery and specificity problems.

### 4.3 Third — LIAVA splice rescue (protan/BCM splice-haplotype cases)

The splice-disrupting SNP combination of the LIAVA class causes near-complete exon 3 skipping and can be addressed by reverting the principal disease nucleotide(s) with a base or prime editor.[120] In vitro data confirm that pathogenic exon-3 haplotypes yield absent or minute correctly spliced transcript,[191] and that correcting only the splice-disrupting position(s) would restore full-length transcript without conflicting with the protein code. The edit is single-base-class, but routing requires genotyping, and splice restoration must be verified in a minigene assay before any in-vivo claim.[unverified]

### 4.4 Comparators

**CRISPRa reactivation.** Most deutans retain intact, spectrally normal downstream `OPN1MW` copies silenced only by LCR promoter competition.[194] dCas9-based transcriptional activation has in-vivo precedent in the opsin system: dual split-intein AAV vectors were used to activate the `Opn1mw` gene in rod photoreceptors in a retinitis pigmentosa mouse model.[123] CRISPRa involves no DNA cutting and is gene-size-independent, but whether LCR-circumventing activation yields properly cone-segregated expression is unknown [unverified].

**AAV opsin augmentation.** Not CRISPR, but the benchmark every design must beat. Adult primates lacking L-opsin gained trichromatic color vision behavior from subretinal AAV delivery of a human L-opsin transgene[177] — the proof that adult retinas integrate a new pigment class without developmental rewiring. The opsin cDNA (~1.1 kb [analysis]) fits a single AAV with a cone promoter, and augmentation works across all genotypes without patient-specific design.

**Tritan mini-scope.** The G79R allele (the most clinically reported tritan missense variant [unverified]) is an A→G correction within adenine-base-editor scope, in an autosomal gene free of the array-specificity problem. The population is very small and no disease-mutation animal model exists [unverified]; this remains a scoped mini-project.

## 5. Why achromatopsia is augmentation-watched, not CRISPR-targeted

Achromatopsia sits on the opposite side of every design axis from BCM.[unverified] Its genes are AAV-sized, so a single augmentation construct serves every mutation in a gene regardless of class; five gene-therapy clinical trials are registered at the phase I/II stage for CNGA3- or CNGB3-causing achromatopsia.[11] The first-in-human CNGB3 trial tested AAV8-hCARp.hCNGB3 in 23 participants[11] and, like the other trials, returned acceptable safety with heterogeneous, modest functional gains [unverified]. Mutation-specific editing would fragment a small patient pool into per-variant programs — even the best single target, CNGB3 c.1148delC at >70% of CNGB3 mutant alleles,[174] reaches a truly biallelic population that is a fraction of an already rare disease [analysis]. Meanwhile augmentation is incumbent, de-risked, and its open problems (efficacy heterogeneity, endpoint selection, pediatric-versus-adult timing) are not problems CRISPR specifically solves.[11] The rational posture is to watch: revisit editing if augmentation phase III results disappoint, if dual-AAV prime editing demonstrates cone rescue in a CNGA3/CNGB3 disease model, or if longitudinal data show late cone degeneration that only in-situ correction could address.[unverified]

## 6. Translational reality

The translational context is sobering and must frame any enthusiasm.[unverified] The only in-vivo CRISPR therapy ever dosed in human retina is EDIT-101 (Editas Medicine), targeting the IVS26 deep-intronic mutation of CEP290 in Leber congenital amaurosis 10 via subretinal AAV5 carrying SaCas9 and two gRNAs.[93] Early findings from the phase 1/2 BRILLIANCE trial reported favorable safety outcomes and improved photoreceptor function in eleven of fourteen treated participants;[93] nevertheless, limited efficacy combined with the small target population led to discontinuation of further enrollment and a search for a development partner.[93] No base- or prime-editing retinal trial has dosed patients [unverified].

For color-vision disease specifically, no human clinical trial of any modality has ever been completed.[unverified] The nearest translational program is for BCM: BGTF-027 (formerly ADVM-062), an intravitreal AAV expressing functional L-opsin licensed from Adverum to the Blue Gen Therapeutics Foundation, with the Vision Center at Children's Hospital Los Angeles developing a phase 1 protocol and preparing an IND submission to the FDA.[170]

Timing constraints add urgency to any eventual program: in BCM mouse models, robust rescue of cone function and outer-segment morphology was achieved when mice were treated at less than 3 months of age, but therapy efficacy was significantly reduced when DKO and C198R mice were treated at 5 months or older.[190] Human BCM degenerates far more slowly than the mouse models [unverified], and the primate augmentation result shows adult integration of a new pigment class is possible,[177] but the mouse data remain a direct warning that editing-based rescue must outpace degeneration.

## 7. Limitations and open questions

**Provenance corrections.** During this project's literature phase, several commonly circulated claims failed verification and are corrected here for the record: (i) a "Ma et al. 2019 Nature knock-in of OPN1LW into Opn1mw in adult mice" reference does not exist — it conflates transgenic knock-in mice (Smallwood 2003/Jacobs 2007), CRISPR HITI work (Suzuki 2016), and AAV augmentation (Ma 2022); the genuine adult-onset proof of trichromacy is Mancuso et al. 2009 [177]. (ii) The LIAVA residues are 153/171/174/178/180, corresponding to exon-3 SNPs including c.532A>G and c.538T>G [120]. (iii) The variants "OPN1SW C90D" and "CNGB3 c.1572_1573insT" could not be verified in any primary source and are excluded; the verified tritan catalog is L56P, G79R, T190I, S214P, P264S, R283Q plus the intron 3 +5delG splice allele [97]. (iv) c.1148delC is a CNGB3 founder variant, not a CNGA3 variant [174].

**Data gaps.** Mouse treatment-window data do not extrapolate cleanly to human degeneration timelines.[190] Editing efficiency in human foveal cones is entirely unproven; all retinal in-vivo editing rescues to date are in mice, mostly young mice. No published base- or prime-editing work targets `OPN1LW`/`OPN1MW` — every design in this review would be among the first. Guide-density arithmetic at the opsin loci must be computed on real per-patient haplotype sequence, not reference assemblies [design principle]. The population share of protan defects (~2% of males [unverified]) rests on older prevalence literature. Whether correcting a splice defect also rescues the high-myopia phenotype of LIAVA carriers is unknown [unverified].

**Open questions.** (1) What off-copy editing rate is acceptable in a 96%-identical array, and can copy-specific guides be designed for every patient haplotype? (2) Does C203R mutant opsin exert dominant-negative toxicity in human cones, which would favor knockdown-plus-replacement over pure augmentation for missense genotypes? (3) What fraction of cones must be corrected for a psychophysically measurable color-vision gain? (4) Can CRISPRa override LCR promoter preference to yield cone-segregated expression? (5) Which outcome measures — color discrimination testing, FST, patient-reported outcomes — should gate any future first-in-human editing study for a non-degenerative condition? These questions are tractable in silico and in animal models but currently unanswered.

## 8. Conclusion

Color-vision genetics divides the CRISPR problem into asymmetric sub-problems [unverified]. For red–green CVD, the causal lesions are mostly structural, and precision editing of the expressed hybrid gene is the only route that addresses the actual mutation — at the cost of the hardest delivery and specificity constraints in the field [194]. For BCM, the C203R lesion offers the cleanest precision-to-biology fit anywhere in inherited retinal disease: a single, common, base-editor-reversible point mutation[97] in a rescue-competent cone population.[2] For achromatopsia, gene augmentation is already in human trials[11] and mutation-specific editing adds no clear advantage.[unverified] The engineering bottleneck — AAV packaging, dual-vector efficiency, copy-specific targeting in a 96%-homologous array — is now better characterized than the translational path, which has no precedent for a non-degenerative, quality-of-life indication in the eye.[unverified] This review's rankings are computational hypotheses grounded in the cited literature; they require guide-design feasibility passes, off-target screening against full patient haplotypes, and eventually animal validation before they could ever approach clinical relevance.[unverified] No clinical application is proposed.[unverified]

---

*Sources rendered below mechanically from the citation ledger (`docs/citations-ledger.json`); inline [n] identifiers refer to it.*

## Sources

[1] https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257
[2] https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232
[11] https://pmc.ncbi.nlm.nih.gov/articles/PMC11396370
[46] https://jamanetwork.com/journals/jamaophthalmology/fullarticle/413200
[67] https://openaccess.city.ac.uk/id/eprint/29916/1/i2164-2591-12-1-25_1674547467.12385.pdf
[74] https://pmc.ncbi.nlm.nih.gov/articles/PMC10474087
[82] https://pmc.ncbi.nlm.nih.gov/articles/PMC11962696
[93] https://pmc.ncbi.nlm.nih.gov/articles/PMC12932096
[97] https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016
[106] https://pmc.ncbi.nlm.nih.gov/articles/PMC4717370
[117] https://pmc.ncbi.nlm.nih.gov/articles/PMC7254067
[120] https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646
[122] https://pmc.ncbi.nlm.nih.gov/articles/PMC8766373
[123] https://pmc.ncbi.nlm.nih.gov/articles/PMC8840918
[128] https://pmc.ncbi.nlm.nih.gov/articles/PMC9646815
[170] https://www.managedhealthcareexecutive.com/view/gene-therapy-for-rare-eye-disease-to-advance-to-human-trial
[174] https://www.nature.com/articles/5201269
[177] https://www.nature.com/articles/nature08401
[181] https://www.nature.com/articles/s41434-025-00573-2
[183] https://www.nature.com/articles/s41467-025-57628-6
[187] https://www.nature.com/articles/s41551-022-00911-4
[190] https://www.nature.com/articles/s42003-025-09045-0
[191] https://www.nature.com/articles/srep28253
[194] https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1682812
