# 60 — CRISPR Engineering Constraints for Retinal In-Vivo Editing

Shared engineering reference for the color-vision-crispr subprojects (computational CRISPR
research; in-silico literature and design only). Every factual claim carries an inline source
URL from a session retrieval. Load-bearing facts cross-confirmed in ≥2 independent sources
where available; gaps are marked `[unverified]` and collected in Limitations.

---

## 1. Editor choice for retinal therapy

### 1.1 Sizes (the hard numbers)

| Component | CDS size | Single-AAV compatible? | Sources |
|---|---|---|---|
| SpCas9 | 4,098 bp (~4.1 kb) | No — leaves no room for promoter + gRNA in the ~4.7 kb AAV genome | https://pmc.ncbi.nlm.nih.gov/articles/PMC9589773/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/ |
| SaCas9 | 3.2 kb | Yes (fits with 1–2 sgRNA cassettes) | https://pmc.ncbi.nlm.nih.gov/articles/PMC9589773/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/ |
| CjCas9 (Campylobacter jejuni) | hypercompact; delivered in single AAV subretinally (VEGF-A knockout in AMD mouse, ~20% indels in retina/RPE) | Yes | https://www.nature.com/articles/s41434-025-00573-2 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/ |
| CasMINI (engineered Cas12f, 529 aa / ~1.55 kb) | ~1.55 kb | Yes — even with a tethered deaminase: ABE8e-CasMINI fits AAV packaging (Xu et al.) | https://pmc.ncbi.nlm.nih.gov/articles/PMC9589773/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC9569511/ |
| Base editors (CBE/ABE) | CBE/ABE + gRNA ≈ 6 kb (5.2–6.3 kb class) | No as full-length; single-AAV only via compact orthologs (SaCas9/Nme2/CjCas9) or split-intein dual-AAV | https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC13412194/ |
| Prime editors | >7 kb (some sources >6.3 kb) | No — exceed AAV even with dual-AAV split systems showing limited photoreceptor efficiency | https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/ |
| Compact single-AAV ABEs (Davis et al., Liu lab) | SaABE8e 3.9 kb; whole genome incl. ITRs ≤ ~5.0 kb | Yes — editor + gRNA + promoters in one AAV, packaged in AAV8 and AAV9 | https://www.nature.com/articles/s41551-022-00911-4 |

Other compact architectures: sABE (SpCas9 ΔREC2/ΔHNH, 4.15 kb, single-AAV with mini-promoters,
4.83 kb cassette — slightly over the 4.7 kb limit, moderate in-vivo activity)
https://pmc.ncbi.nlm.nih.gov/articles/PMC10337206/ ; Nme2-ABE8e (with Acr/miRNA-MRE specificity
switch, single AAV) https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/ ; CasMINI-based
repressors/activators far below 4.7 kb https://pmc.ncbi.nlm.nih.gov/articles/PMC9589773/.

### 1.2 PAM requirements and implications for guide density in opsin loci

| Nuclease | PAM (3′ unless noted) | Guide length | Sources |
|---|---|---|---|
| SpCas9 | NGG (canonical); engineered NG / SpG / SpRY near-PAM-less | 20 nt | https://pmc.ncbi.nlm.nih.gov/articles/PMC12204363/ ; https://www.nature.com/articles/s41592-020-0861-5 ; https://www.nature.com/articles/s41467-026-71626-2 |
| SaCas9 | NNGRRT | 21 nt | https://pmc.ncbi.nlm.nih.gov/articles/PMC12204363/ ; https://www.nature.com/articles/s41467-026-71626-2 |
| SaCas9-KKH | NNNRRT | — | https://www.nature.com/articles/s41592-020-0861-5 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC13109818/ |
| eSaCas9-NNG (engineered) | NNG | 21 nt | https://www.nature.com/articles/s41467-026-71626-2 |
| CjCas9 | NG (broad; per ortholog paper) | 22 nt | https://www.cell.com/molecular-therapy-family/molecular-therapy/fulltext/S1525-0016(23)00061-8 ; https://www.nature.com/articles/s41467-026-71626-2 |
| Cas12a (FnCpf1) | TTTN (5′) | — | https://pmc.ncbi.nlm.nih.gov/articles/PMC12204363/ |
| CasMINI (Cas12f) | TTTR | — | https://pmc.ncbi.nlm.nih.gov/articles/PMC9569511/ |
| Cas12j-8 | TTN | — | https://bits.fudan.edu.cn/static/publication_pdf/2023_SciAdv_Cas12j.pdf |

GenomePAM mammalian-genome measurements confirm the canonical PAMs and quantify context
dependence: for SaCas9, adding successive PAM bases (G → GR → GRR → GRRT at PAM positions
3–6) raises the fraction of edited targets from 44.6% to 96.7–98.0%, i.e. the full NNGRRT is
essentially mandatory for reliable activity
(https://pmc.ncbi.nlm.nih.gov/articles/PMC12204363/ ; corroborated
https://pmc.ncbi.nlm.nih.gov/articles/PMC12812445/).

**Density arithmetic** (random-sequence expectation, computed this session): NGG occurs 1 per
16 bp; NNGRRT 1 per 256 bp (16× sparser); NNNRRT 1 per 64 bp; TTTR and TTN 1 per 16 bp.
Recognized footprint: SpCas9 = 23 nt (20 nt spacer + 3 nt PAM); SaCas9 = 27 nt (21 + 6). Real
genomes deviate with GC content (SpCas9 sites need G; opsin genes are ~60–70% GC), so NNGG
counts must be computed on actual OPN1LW/OPN1MW sequence in the design phase. Practical
consequence for opsin loci: SaCas9's 6-nt PAM plus 21-nt spacer demands a 27-nt perfectly
positioned site — roughly an order of magnitude fewer candidate sites than SpCas9 — while
Cas12j-8's TTN and SpCas9's NGG give high site density but a 4.1–4.2 kb editor that does not
fit AAV. The Cas12j-8 paper explicitly notes its "simple TTN PAM that provides for high target
site density" (https://bits.fudan.edu.cn/static/publication_pdf/2023_SciAdv_Cas12j.pdf).
CasMINI's TTTR is dense but its editing window lies only 3–4 bp downstream of the PAM, a
constraint "that render[s] it inapplicable to USH2A and many other pathogenic mutations"
(https://pmc.ncbi.nlm.nih.gov/articles/PMC9569511/) — the same window-position constraint will
apply to any specific opsin codon target.

### 1.3 DSB risks in post-mitotic photoreceptors — why base/prime editing is preferred

- Nucleases create double-strand breaks; in post-mitotic photoreceptors the repair outcome is
  NHEJ-dominated. DSBs produce "highly heterogeneous mixtures of potentially toxic indel
  outcomes, adeno-associated virus (AAV) integration into the genome, chromosomal
  abnormalities, and other undesired cellular consequences"
  (https://www.pnas.org/doi/10.1073/pnas.2416827121).
- HDR is cell-cycle restricted (S/G2); "repair efficiency is low for postmitotic retinal
  cells" (https://pmc.ncbi.nlm.nih.gov/articles/PMC10768554/). CRISPR-HDR can work in
  post-mitotic retina but at very low efficiency (<3% in newborn mice; RPE-only in rd12)
  (https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2021.698521/full ;
  https://onlinelibrary.wiley.com/doi/full/10.1002/smtd.202000309).
- Base and prime editors edit "without causing DSBs" (https://pmc.ncbi.nlm.nih.gov/articles/PMC10768554/),
  making them the mechanistically preferred class for correcting point mutations (e.g. a
  missense opsin variant) in post-mitotic cones — provided delivery constraints (§2) can be met.

---

## 2. Delivery

### 2.1 AAV packaging and dual-AAV split-intein strategies

- AAV packaging limit ~4.7 kb (excluding ITRs) — the central constraint; "large CRISPR
  platforms such as BEs and PEs still exceed the packaging capacity of rAAV vectors,
  precluding their delivery as full-length molecules"
  (https://www.nature.com/articles/s41434-025-00573-2).
- Dual-AAV split-intein: the editor is split into N- and C-terminal halves, each fused to a
  trans-splicing intein; full-length editor is reconstituted after co-transduction of both
  particles (https://pmc.ncbi.nlm.nih.gov/articles/PMC9604474/ ;
  https://pmc.ncbi.nlm.nih.gov/articles/PMC13412194/ — "the most widely adopted solution").
- **Efficiency penalty:** the target cell must be co-transduced by both particles. Retinal
  split-ABE data: ~20–25% A-to-G editing at the NR2E3 splice donor in adult mouse retina
  (https://onlinelibrary.wiley.com/doi/full/10.1002/smtd.202000309); dual-AAV CBE/ABE via
  PHP.B/Anc80 capsids: 19–26% rod editing
  (https://www.cell.com/molecular-therapy-family/molecular-therapy/fulltext/S1525-0016(21)00457-3);
  rd10 Pde6b correction with dual-AAV8 ABE: up to 20.8% at DNA level, 55% at cDNA level
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC9996133/); rhodopsin-E150K correction up to 44%,
  but functional rescue only when injected at postnatal day 15, not later
  (https://www.pnas.org/doi/10.1073/pnas.2416827121). Compare single-vector CasMINI nuclease
  in the same organ: >70% editing in transduced retinal cells
  (https://onlinelibrary.wiley.com/doi/10.1002/advs.202308095) — the split-vs-single gap is
  the practical cost of a >4.7 kb payload.
- Single-AAV alternatives that avoid the co-transduction penalty: CasMINI-based editors
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC9569511/), Davis et al. compact ABEs
  (https://www.nature.com/articles/s41551-022-00911-4), sABE
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC10337206/). Caveats from Davis et al.: single-AAV
  ABEs are limited to A·T→G·C edits and have wide editing windows that increase bystander
  editing; their genomes sit at the packaging limit and package truncated species.

### 2.2 Retinal capsids

| Capsid | Route | Tropism notes | Sources |
|---|---|---|---|
| AAV2 (native) | subretinal | Photoreceptors + RPE; weaker than variants; used in clinical trials (RP, achromatopsia, LCA) | https://pmc.ncbi.nlm.nih.gov/articles/PMC10722277/ |
| AAV5 | subretinal | Efficient subretinal PR transduction; used in NHPs and in EDIT-101 | https://pmc.ncbi.nlm.nih.gov/articles/PMC10722277/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/ |
| AAV8 | subretinal | Greater PR tropism than AAV2; efficiently targets rod PRs in NHP subretinal | https://pmc.ncbi.nlm.nih.gov/articles/PMC4993104/ |
| AAV9 | subretinal | "superior for cone PRs and retains tropism for rod PRs" in NHP | https://pmc.ncbi.nlm.nih.gov/articles/PMC4993104/ |
| AAV2tYF (quad Y-F) | IVT or subretinal | Well tolerated in cynomolgus IVT (GCL/INL transduction); subretinal PR1.7 study had severe ocular inflammation in 1/6 animals | https://pmc.ncbi.nlm.nih.gov/articles/PMC12662786/ |
| AAV2.7m8 | IVT or subretinal | "most efficient retinal capsid"; transduces all retinal layers after IVT; cones best transduced among capsids in human explants | https://pmc.ncbi.nlm.nih.gov/articles/PMC10722277/ ; https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746594/ ; https://discovery.ucl.ac.uk/id/eprint/10183864/1/s41598-023-49112-2.pdf |

- AAV2(7m8) "transduced the largest area of retina and resulted in the highest level of GFP
  expression, followed by AAV2/2(quad Y-F) and AAV2/8(Y733F)"; the same pattern held whether
  injected intravitreally or subretinally, and **cones were the most frequently transduced
  cell type in macaque retina explants** (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746594/).
- In primary human retina organoids/explants, AAV-7m8 "transduced cones as well as many other
  cell types," and achieved the highest expression in sorted cones
  (https://discovery.ucl.ac.uk/id/eprint/10183864/1/s41598-023-49112-2.pdf).
- 7m8 caution: intravitreal AAV2(7m8) "has also resulted in intraocular inflammation and other
  retinal immune responses in clinical trials," and 7m8 did not transduce cone photoreceptors
  in retinal organoids (https://www.nature.com/articles/s41434-025-00527-8).
- Cone tropism lever: AAV9 for cones via subretinal in NHP (above); high-dose AAV8 subretinal
  transduces cones efficiently (≥1e11 vg) while low dose yields mostly rods
  (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746594/).

### 2.3 Subretinal vs intravitreal

- Subretinal: vector delivered between photoreceptors and RPE; creates a localized retinal
  detachment (bleb); the subretinal space is immune privileged; typically requires pars plana
  vitrectomy; transduces PRs and RPE efficiently (https://onlinelibrary.wiley.com/doi/full/10.1111/ceo.14593 ;
  https://pmc.ncbi.nlm.nih.gov/articles/PMC4993104/).
- Intravitreal: non-surgical, broader spread, but most capsids fail to cross the inner
  limiting membrane (ILM); 7m8 and tYF variants are the exceptions
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC4993104/ ;
  https://www.nature.com/articles/s41434-025-00527-8).
- For cone opsin targets, EDIT-101 precedent used subretinal delivery to reach photoreceptors
  (https://ir.editasmedicine.com/node/10671/pdf).

### 2.4 Promoters

| Promoter | Size | Specificity | Sources |
|---|---|---|---|
| PR2.1 (human red/green opsin promoter) | 2.1 kb | Strong in L/M cones; in mouse leaky to rods and weak; NHP L/M-cone expression weak; intravitreal leak into INL/GCL | https://pmc.ncbi.nlm.nih.gov/articles/PMC4741229/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC5821199/ ; https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5656413/ |
| PR1.7 (shortened human red/green opsin promoter) | 1.7 kb | "More efficient than the PR2.1 promoter, driving strong and specific GFP expression in primate cone photoreceptors"; maintained cone specificity even after IVT; robust in NHP L/M and S cones | https://pmc.ncbi.nlm.nih.gov/articles/PMC4741229/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC5821199/ |
| hCAR (human cone arrestin) | ~500 bp | Not cone-specific — off-target in rods; ~58% of foveolar hCAR+ cells expressed GFP with 7m8 IVT | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4450355/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC5821199/ |
| mCAR (mouse cone arrestin) | ~500 bp | Leaky to rods, INL, GCL — unsuitable when inner-retinal expression is harmful | https://pmc.ncbi.nlm.nih.gov/articles/PMC5821199/ |
| IRBPe/GNAT2 chimera | <500 bp | Strong and specific in all cone subclasses; an improvement over PR2.1 for cone targeting | https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4450355/ |
| hG1.7 (GRK1-derived) | 1.7 kb class | Rod+cone PR promoter used in optogenetic constructs (GenSight-style); patent-cited | https://patents.google.com/patent/JP2025528188A/en [unverified scope — patent source] |
| PR1.1 / PR1.5 | 1.1 / 1.5 kb | PR1.1 strong but RPE off-target; PR1.5 weaker | https://data.epo.org/publication-server/rest/v1.2/publication-dates/2025-11-19/patents/EP3517135NWB1/document.pdf [patent source] |

Cone LCR context: the OPN1LW/OPN1MW locus control region (LCR) upstream of the array is
required for opsin expression; deletion mapping refined its minimal functional extent to
~358 bp (https://affinage.wi.mit.edu/api/gene/OPN1LW [unverified — secondary API source]).
The LCR-related locus control region concept for cone-specific expression derives from the red
opsin LCR promoter series (PR1.7/PR2.1) (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5656413/).

**Packaging interplay:** PR2.1 (2.1 kb) + SaCas9 (3.2 kb) + gRNA + regulatory elements already
exceeds 4.7 kb — PR1.7 (1.7 kb) or a <500 bp promoter is effectively mandatory for single-AAV
Cas9 constructs; for base editors only the smallest promoters (e.g. miniCMV, IRBPe/GNAT2) fit
even with compact orthologs (https://www.nature.com/articles/s41551-022-00911-4 ;
https://pmc.ncbi.nlm.nih.gov/articles/PMC10337206/).

---

## 3. Allele-specificity challenge for X-linked opsin edits

The locus: "a single OPN1LW and up to five OPN1MW genes located head-to-tail in tandem" on
Xq28, sharing ">96% nucleotide sequence identity over their entire ~40 kilobase pair length";
unequal recombination/gene conversion generates hybrid opsin genes; "only the first two genes
in the array are expressed" (first gene + first M copy, ordered by distance to the LCR)
(https://pmc.ncbi.nlm.nih.gov/articles/PMC9646815/ ;
https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/ ;
https://medlineplus.gov/genetics/gene/opn1mw/ ;
https://www.sciencedirect.com/topics/neuroscience/opn1lw).

This makes allele-/copy-specific editing harder than the autosomal-dominant setting the
existing literature addresses: the guide must discriminate near-identical tandem copies, not
just two alleles. Approaches demonstrated for allele-specific retinal editing, in increasing
specificity:

1. **Mutation-in-spacer ("near the PAM"):** the discriminating base sits in the guide seed.
   Demonstrated for Rho-P23H (Bakondi et al.; Li et al.) and for c.1039C>T RHO-P347S with
   SpCas9-VQR and the variant as the 20th spacer nucleotide
   (https://www.mdpi.com/1422-0067/21/7/2329 ;
   https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2021.698521/full ;
   https://iris.unimore.it/bitstream/11380/1236862/2/1-s2.0-S0002929721000069-main.pdf).
   Caveat: "single–base pair mismatches between the mutant and WT alleles may not be enough to
   always prevent cleavage of the WT allele" (https://www.jci.org/articles/view/158287), and
   5′-end mismatches are well tolerated — position in the seed is decisive
   (https://www.jci.org/articles/view/158287).
2. **Mutation-creates-PAM ("in the PAM"):** the variant base generates a PAM absent from the
   other allele, so Cas9 binds exclusively
   (https://www.frontiersin.org/journals/genetics/articles/10.3389/fgene.2020.00851/full).
3. **SNP-derived PAM in cis (mutation-independent):** use a natural SNP-in-PAM on the target
   copy, "removing the constraints of a mutation-dependent approach" — complete allele
   discrimination demonstrated for TGFBI
   (https://www.cell.com/molecular-therapy-family/molecular-therapy/fulltext/S1525-0016(20)30236-7 ;
   CriPam analysis tool: https://www.frontiersin.org/journals/genetics/articles/10.3389/fgene.2020.00851/full).
   For the opsin array this maps to: find copy-specific SNPs (junction/L-and-M-characteristic
   bases) that create a PAM or sit in the seed only on the hybrid/target copy.
4. **Truncated guides + Cas9 variant combos:** sgRNA truncation plus SpCas9-VQR in Rho-P23H
   mice — ~45% of the mutant allele edited at DNA level, no detectable WT cleavage in
   homozygous-WT controls; WT:mutant expression ratio ~2.8
   (https://pmc.ncbi.nlm.nih.gov/articles/PMC6319323/).
5. **Paired guides flanking SNPs → targeted deletion** of the mutant copy
   (https://www.jci.org/articles/view/158287) — a candidate strategy for knocking out a
   specific array copy, at the cost of a nuclease DSB (§1.3).
6. **Mismatch-sensitive nucleases:** Cas12j-8 is PAM-proximal-mismatch-sensitive and
   allele-specifically disrupts SNP loci with a TTN PAM, with in-silico allele-specific
   coverage of 25,931 ClinVar variants
   (https://bits.fudan.edu.cn/static/publication_pdf/2023_SciAdv_Cas12j.pdf).

Constraints this imposes on the design phase: for any X-linked opsin edit, candidate guides
must be screened against **every copy in the patient's array** (long-read/MLPA haplotype
determination first — https://pmc.ncbi.nlm.nih.gov/articles/PMC9646815/), exploiting the
<4% of bases that differ between copies; expression confinement to the first two genes
(partly) limits the blast radius of off-copy editing of distal copies, since unexpressed
array copies would not contribute protein even if cut [unverified — inferred].

---

## 4. Guide design tooling

- **CRISPOR** (http://crispor.tefor.net/): off-target enumeration (BWA-based) + multi-algorithm
  efficiency scoring, 100+ genomes, custom genome upload, 30+ Cas variants, specificity
  scores, cloning/primer output. Most versatile per recent reviews
  (https://link.springer.com/article/10.1007/s00294-026-01339-y ;
  https://pmc.ncbi.nlm.nih.gov/articles/PMC12109910/ ;
  https://pmc.ncbi.nlm.nih.gov/articles/PMC12319022/).
- **CHOPCHOP** (https://chopchop.cbu.uib.no/): guide design for Cas9, Cas12a and base editors;
  supports most sequenced vertebrates + custom genomes; enumerates off-targets to 3 mismatches;
  published scoring penalties (MM0 off-target +1000, MM1 +800, MM2 +600, bad GC +500)
  (https://link.springer.com/article/10.1007/s00294-026-01339-y ; https://chopchop.cbu.uib.no/scoring).
- **ML scoring:** DeepSpCas9 / Azimuth-style on-target models; DeepCRISPR adds CNN +
  epigenomic features (DNase I, histone marks, chromatin accessibility) for cell-type-aware
  on/off-target prediction, at the cost of a dependency on cell-type-specific epigenomic data
  (https://link.springer.com/article/10.1007/s00294-026-01339-y). For photoreceptors such
  epigenomic data exist for mouse retina but are scarcer for human cones [unverified].
- **Benchmark:** a PLoS Comp Biol head-to-head of guide-design methods (off-target mapping via
  Bowtie/Bowtie2/BWA) found CRISPOR (reporting the Azimuth score) at 77.4% precision and SSC
  at 85.1% (https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1007274&type=printable).
- **Off-target assessment options for the later in-silico phase:** (a) whole-genome exhaustive
  enumeration with mismatch/bulge tolerances (CRISPOR/CHOPCHOP/GuideScan class) — appropriate
  for final candidate guides; (b) panel-based targeted checks — faster but incomplete;
  (c) empirical GUIDE-seq-style data, useful for validating PAM-relaxed variants since SpG/SpRY
  edit additional off-target sites (https://www.nature.com/articles/s41592-020-0861-5).
  Two categories are recognized: "exhaustive genomic search tools" vs "predictive scoring
  models" (https://link.springer.com/article/10.1007/s00294-026-01339-y).
- For opsin-locus work specifically: any tool run must score guides against the full tandem
  array, not the reference single-copy haplotype (§3), and PAM-variant nucleases (SaCas9-KKH,
  VQR, Cas12j-8) change which sites exist — the tool must support the chosen PAM.

---

## 5. Safety / immunology

- **Cas9 immunity prevalence (varies by assay):** anti-SaCas9 serum antibodies 10%–79%;
  anti-SpCas9 2.5%–65% across cohorts (Simhadri et al. 10%/2.5%; Charlesworth et al. 58%/78%;
  Wagner et al. 85% for SpCas9). Cas9-reactive CD4+/CD8+ T cells also widespread (SaCas9
  CD4+ reactivity 9.5–53%)
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC6070699/ ;
  https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7264432/ ;
  https://pmc.ncbi.nlm.nih.gov/articles/PMC12848201/).
- **Ocular-specific good news:** in human donor tissue, "high prevalence of preexisting
  Cas9-reactive antibodies in serum but not in the eye" — preexisting Cas9 immunity "may
  represent a lower risk in human eyes than systemically"
  (https://www.nature.com/articles/s41467-022-28674-1).
- **But immunity can negate editing:** in mice, pre-existing anti-Cas9 immunity negated
  AAV-CRISPR editing — possible mechanisms include blocking delivery, acute inflammation, or
  immune destruction of edited cells
  (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7264438/). Subretinal delivery into the
  immune-privileged space is the mitigating factor for retinal CRISPR
  (https://onlinelibrary.wiley.com/doi/full/10.1111/ceo.14593).
- **Germline vs somatic:** ocular subretinal dosing is somatic; NHP biodistribution of
  dual-AAV8.MYO7A found no vector in gonads ("negligible risk of germline transmission"),
  transient shedding in tears up to ~31–91 days and possible spread to the untreated eye by
  eye rubbing (https://pmc.ncbi.nlm.nih.gov/articles/PMC9996380/). Regulatory practice:
  biodistribution to gonads must be assessed for in-vivo vector use; contraceptive measures
  are conventionally recommended for ~one spermatogenesis cycle (64–74 days)
  (https://www.ncbi.nlm.nih.gov/books/NBK447271/ ; EMA germline-transmission guidance:
  https://www.ema.europa.eu/en/documents/scientific-guideline/draft-note-guidance-quality-preclinical-and-clinical-aspects-gene-transfer-medicinal-products-annex-non-clinical-testing-inadvertent-germline-transmission-gene-transfer-vectors_en.pdf).
- **Subretinal injection risks:** procedure-related AEs dominate. Pooled ocular AAV trials:
  cumulative ≥1 SAE ~8%; SAEs mostly surgical rather than vector-related
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC10668613/). Route meta-analysis: subretinal
  serious events — severe inflammation 2.3%, retinal injuries 1.4%, retinal degeneration 1.1%,
  RD 1.1%, severe unexplained vision loss 5.5% (n = 438 eyes)
  (https://onlinelibrary.wiley.com/doi/full/10.1111/ceo.14593). Foveal detachment is part of
  the standard procedure; central retinal thinning post-LCA gene therapy (~19 μm at 2–3 y) is
  attributed to the temporary detachment
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC8259781/). Voretigene-neparvovec post-marketing:
  progressive perifoveal chorioretinal atrophy in up to 50% of treated eyes; at least one case
  of presumed AAV immune response causing foveal photoreceptor loss in the second treated eye
  (https://link.springer.com/content/pdf/10.1007/s13353-025-00973-5.pdf). EDIT-101 itself:
  inflammation and retinal deposits in some patients, resolving over time or with steroids,
  without functional impact (https://crisprmedicinenews.com/news/gene-editing-highlights-from-retina-international-world-congress-2024/).

---

## 6. What's clinically real

- **EDIT-101 (Editas Medicine), BRILLIANCE trial (NCT03872479)** — the first in-vivo CRISPR
  therapy in humans: CEP290-LCA10 IVS26 deep-intronic mutation (c.2991+1655A>G); single AAV5
  vector encoding SaCas9 + two gRNAs to excise the aberrant splice donor; subretinal injection.
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC12932096/ ;
  https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/)
- Status: 14 participants (12 adults 17–63 y, 2 pediatric 9 and 14 y). No dose-limiting
  toxicities, no treatment-related SAEs; no adverse effects attributable to Cas9 activity
  (surgery-related only). Efficacy: 6/14 meaningful improvement in cone-mediated vision (FST);
  6/14 meaningful improvement in vision-related quality of life; 4/14 significant BCVA
  improvement; BCVA improvement ≥0.3 logMAR in 3/14. Phase 1/2 published in NEJM
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC12838982/ ;
  https://crisprmedicinenews.com/news/gene-editing-highlights-from-retina-international-world-congress-2024/ ;
  https://ir.editasmedicine.com/node/10671/pdf).
- **Trial discontinued/suspended:** enrollment stopped after 14 patients; limited efficacy in
  a small population led Editas to discontinue further enrollment and seek a development
  partner; as of mid-2024 further development unclear
  (https://pmc.ncbi.nlm.nih.gov/articles/PMC12932096/ ;
  https://crisprmedicinenews.com/news/gene-editing-highlights-from-retina-international-world-congress-2024/).
- **Other in-vivo retinal CRISPR:** no approved product. Preclinical in-vivo nuclease editing
  of photoreceptors exists (CEP290 IVS26 knock-in mice and NHPs, 27.9±20.7% editing at 1e12
  vg/mL — https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/ ; CasMINI Nr2e3 in RP mice —
  https://onlinelibrary.wiley.com/doi/10.1002/advs.202308095). Base-editing retinal trials:
  none dosed [unverified as of this search]. Adjacent ocular CRISPR: CjCas9-VEGF-A AMD
  preclinical (https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/).

---

## 7. Key papers

1. rAAV CRISPR delivery review (2025) — https://www.nature.com/articles/s41434-025-00573-2
2. Genome-editing strategies for retinal disease (CEP290 NHP, sizes) — https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/
3. Base & prime editing in the retina review — https://pmc.ncbi.nlm.nih.gov/articles/PMC9604474/ ; updated https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/
4. Rho-E150K in-vivo photoreceptor base editing (PNAS) — https://www.pnas.org/doi/10.1073/pnas.2416827121
5. rd10 Pde6b ABE rescue — https://pmc.ncbi.nlm.nih.gov/articles/PMC9996133/
6. Split-ABE dual-AAV development — https://onlinelibrary.wiley.com/doi/full/10.1002/smtd.202000309
7. CasMINI hypercompact in-vivo retina editing — https://onlinelibrary.wiley.com/doi/10.1002/advs.202308095
8. Single-AAV compact ABEs (Davis et al.) — https://www.nature.com/articles/s41551-022-00911-4
9. 7m8/tYF tropism in rd1 mouse + primate/human explants — https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746594/
10. PR1.7 vs PR2.1 promoters (NHP cones) — https://pmc.ncbi.nlm.nih.gov/articles/PMC4741229/
11. Noninvasive foveal cone delivery (7m8 + PR1.7) — https://pmc.ncbi.nlm.nih.gov/articles/PMC5821199/
12. OPN1LW/OPN1MW cluster structure/diagnostics — https://pmc.ncbi.nlm.nih.gov/articles/PMC9646815/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/
13. Allele-specific editing reviews & RHO-P347S — https://www.jci.org/articles/view/158287 ; https://iris.unimore.it/bitstream/11380/1236862/2/1-s2.0-S0002929721000069-main.pdf
14. Tru-gRNA + Cas9-variant allele discrimination — https://pmc.ncbi.nlm.nih.gov/articles/PMC6319323/
15. CriPam SNP-derived PAM tool — https://www.frontiersin.org/journals/genetics/articles/10.3389/fgene.2020.00851/full
16. Cas12j-8 allele-specific nuclease — https://bits.fudan.edu.cn/static/publication_pdf/2023_SciAdv_Cas12j.pdf
17. Guide-design tool landscape + benchmark — https://link.springer.com/article/10.1007/s00294-026-01339-y ; https://journals.plos.org/ploscompbiol/article/file?id=10.1371/journal.pcbi.1007274&type=printable
18. Cas9 immunity: ocular — https://www.nature.com/articles/s41467-022-28674-1 ; prevalence — https://pmc.ncbi.nlm.nih.gov/articles/PMC6070699/ ; https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7264432/
19. Ocular route-of-administration safety meta-analysis — https://onlinelibrary.wiley.com/doi/full/10.1111/ceo.14593
20. EDIT-101 / BRILLIANCE — https://pmc.ncbi.nlm.nih.gov/articles/PMC12838982/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC12932096/ ; https://ir.editasmedicine.com/node/10671/pdf
21. NHP biodistribution/germline/shedding — https://pmc.ncbi.nlm.nih.gov/articles/PMC9996380/
22. GenomePAM mammalian PAM quantification — https://pmc.ncbi.nlm.nih.gov/articles/PMC12204363/

## 8. Open questions

1. **Cone coverage area:** subretinal blebs transduce only a limited retinal area; what
   fraction of the ~6–7 million cones (or foveal L/M cones specifically) is reachable in a
   single subretinal injection, and can a color-vision effect be achieved with partial
   coverage? (No quantified source found in this pass.)
2. **Editing in adult human cones:** all retinal base-editing functional rescues to date are
   in mice (and mostly young mice — P15/P21 windows, Rho-E150K and rd10); durability and
   efficiency in adult, diseased or normal adult cones are unproven. The PNAS E150K result
   (rescue at P15 but not later) is a direct warning for adult-onset strategies
   (https://www.pnas.org/doi/10.1073/pnas.2416827121).
3. **Allele/copy specificity thresholds:** no study has yet demonstrated copy-specific editing
   within the OPN1LW/OPN1MW array; what off-copy cut rate is acceptable when unexpressed array
   copies are collateral? Needs bespoke in-silico screen + patient haplotypes.
4. **Single-AAV base editor for opsin point edits:** would a compact ABE (SaABE8e class,
   NNGRRT PAM — sparse sites in opsin loci) find usable target sites for a given opsin
   variant? Must be computed per-variant on real sequence.
5. **Bystander edits in opsin coding sequence:** wide ABE windows + degenerate codons mean
   synonymous-but-real protein changes are possible; tolerance unknown.
6. **CasMINI-class editors with PAM-free targeting** (evolved or ML-designed compact effectors)
   could dissolve the size-vs-PAM-density trade-off — monitor literature.
7. **Whether prime editing can ever be delivered to photoreceptors** — current dual-AAV PE
   efficiency is the limiting factor (https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/).

## Limitations

- Sizes and PAM tables are from retrieved literature; CjCas9 exact CDS length was not
  independently confirmed this session, and hG1.7/PR1.1/PR1.5 details rest partly on patent
  documents. LCR minimal-extent (~358 bp) figure comes from a secondary API source.
- Cas9-immunity prevalence figures span conflicting assays (2.5%–79%); treated here as a range,
  not a point estimate.
- EDIT-101 status is time-sensitive (trial suspended mid-2024); re-verify before citing as
  current state.
- Guide-density arithmetic (§1.2) assumes random sequence; real opsin-locus site counts must
  be computed on actual OPN1LW/OPN1MW haplotype sequence in the design phase.
- No source quantifying achievable cone coverage per subretinal bleb in humans was found.
