# Protanopia / Protanomaly — Research Dossier for CRISPR Design

*In-silico literature dossier only. No wet-lab protocols. Compiled 2026-10-22.*

---

## 1. Disease Overview & Prevalence

**Protan defects** are X-linked recessive red-green color vision deficiencies (CVD) caused by loss or dysfunction of the long-wavelength-sensitive (L) cone photopigment encoded by **OPN1LW** (OMIM 300822; phenotype OMIM 303900), located on Xq28.

- **Protanopia** (dichromacy): L-cone function is completely absent; vision is mediated by S and M cones. Red sensitivity is markedly reduced and reds appear darkened.
- **Protanomaly** (anomalous trichromacy): an L cone with shifted (green-like, ~532 nm) spectral sensitivity remains partially functional; residual red-green discrimination is poor but present.

Prevalence (per Neitz & Neitz 2021 and Carroll-lab reviews):
- All red-green CVD: ~8% of males (1 in 12), ~0.4% of females (1 in 230). ([PMC8391646](https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/), [PMC9646815](https://pmc.ncbi.nlm.nih.gov/articles/PMC9646815/))
- Deutan forms account for ~6% of males; **protan forms for roughly 2%** — approximately **1% protanopia + 1% protanomaly** in European/Caucasian males (Deeb 2005, "Molecular genetics of colour vision deficiencies"; [disorders.eyes.arizona.edu](https://disorders.eyes.arizona.edu/category/alternate-names/protanopia)).
- X-linked recessive inheritance; hemizygous males affected, heterozygous females typically carriers (occasional skewing symptoms).

**Retinal structure matters for therapy design:** unlike the splice-haplotype cone dystrophies, "simple" protanopia from hybrid-gene replacement shows a **cone mosaic of normal density** (AO imaging: Carroll et al. 2004/2009; Wagner-Schuman 2010) — the L cones are either replaced by M-cone pigment or left as "empty cones" that remain structurally viable for years ([PMC10317068](https://pmc.ncbi.nlm.nih.gov/articles/PMC10317068/), [PMC7081934](https://pmc.ncbi.nlm.nih.gov/articles/PMC7081934/)). This makes protanopia a *functional* defect in a healthy cone population — favorable for in-vivo genome editing. By contrast, the LIAVA splice haplotype is associated with cone-mosaic gaps, high myopia (eoHM), and cone dysfunction ([PMC10148663](https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/)).

---

## 2. Molecular Genetics of Protan Defects

### 2.1 Genomic architecture

- The **OPN1LW/OPN1MW array** sits head-to-tail on Xq28: one OPN1LW in the first (most 5′) position followed by 1–5 OPN1MW copies; the genes share **>96–98% nucleotide identity over ~40 kb** ([PMC8391646](https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/)).
- A shared upstream **locus control region (LCR)** drives expression; **only the first two genes in the array are expressed** — the first occupies the L-cone position, the second the M-cone position ([PMC7081934](https://pmc.ncbi.nlm.nih.gov/articles/PMC7081934/), [PMC10317068](https://pmc.ncbi.nlm.nih.gov/articles/PMC10317068/)).
- 15 amino acids differ between L and M opsins; **7 alter spectral tuning** (M→L identities: S116/Y116, A180/S180, T230/I230, S233/A233, F277/Y277, A285/T285, F309/Y309). Residues **277 and 285 (exon 5) are the main L/M determinants (~16–24 nm shift)**; 180 (exon 3) contributes ~4–7 nm; 230 and 233 (exon 4) contribute ~3 nm each ([jamanetwork 413200](https://jamanetwork.com/journals/jamaophthalmology/fullarticle/413200), [PMC10946592 Table 3](https://pmc.ncbi.nlm.nih.gov/articles/PMC10946592/), [Sharpe et al. 1999](https://www.allpsych.uni-giessen.de/karl/colbook/sharpe.pdf)).

### 2.2 Mechanisms causing protan defects (with relative prevalence)

**Mechanism 1 — Replacement: 5′L–3′M hybrid gene or lone M-spectrum gene in first position (the dominant mechanism, majority of protan cases).**
- Unequal homologous recombination (NAHR) between the highly homologous array copies produces a **5′-red–3′-green hybrid gene** in the first (expressed) position, so the "L" position encodes a pigment with green (M) spectral sensitivity, peak ~530 nm ([OMIM 303900](https://www.omim.org/entry/303900), [MedlinePlus OPN1LW](https://medlineplus.gov/genetics/gene/opn1lw/)).
- Genotype–phenotype rule (OMIM 303900, citing Deeb/Nathans work): protan defects are **always associated with 5′ red–green hybrid genes**; a *single* hybrid gene (fusion in introns 1–4) → **protanopia**; hybrid in first/second position *plus* an additional spectrally distinct downstream gene → mostly **protanomaly**.
- The Wang 2023 eoHM cohort confirms the same principle: "L-M hybrid gene with amino acids in exon 5 of OPN1MW, which are important for most spectral sensitivity, leads to no functional red photopigment" ([PMC10148663](https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/)).

**Mechanism 2 — OPN1LW deletion.** Unequal crossing over can delete the first gene entirely, leaving only M genes → protanopia with a single expressed M gene ([MedlinePlus OPN1LW](https://medlineplus.gov/genetics/gene/opn1lw/), [PMC8391646](https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/)).

**Mechanism 3 — LIAVA exon-3 splice haplotype (complete exon-3 skipping → protanopia).**
- The five exon-3 polymorphic residues are at **positions 153, 171, 174, 178, 180** (c.457, c.511/513, c.521, c.532, c.538). The prompt's "p.Leu153_Ile156_Val171_Ala180" is **incorrect** — the correct abbreviation is:
  - **LIAVA = p.Leu153; Ile171; Ala174; Val178; Ala180** (positions 153/171/174/178/180), arising from SNPs c.457C>A (L153M context), c.511G>A + c.513G>T (V171I), c.532A>G (I178V), c.538T>G (S180A). A180 is already the pathogenic state; the "A" at 174 is unchanged relative to some references. Normal splice-competent L exon 3 encodes **LVAIS** (Leu153, Val171, Ala174, Ile178, Ser180). ([srep28253](https://www.nature.com/articles/srep28253), [PMC8391646 Table 1](https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/))
- **Splicing mechanism:** the LIAVA nucleotide combination **destroys exonic splicing enhancers (ESEs) and creates exonic splicing silencers (ESSs)** at positions 171, 178 and 180; the splicing machinery fails to recognize exon 3, which is **skipped essentially completely** — exon 2 splices to exon 4, producing a frameshift **p.Ile138Thrfs\*6** and a predicted PTC → nonsense-mediated decay or truncated, nonfunctional opsin. Cones become "empty cones" (stable for years). The single SNP **c.532A>G (I178V)**, common to all three disease haplotypes (LIAVA, MIAVA, LVAVA), "appears to be principally responsible" for the splicing defect. ([PMC8391646](https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/), [PMC4285181](https://pmc.ncbi.nlm.nih.gov/articles/PMC4285181/), [PMC7081934](https://pmc.ncbi.nlm.nih.gov/articles/PMC7081934/))
- **Haplotype severity ranking** (in-vitro splicing assays, Ueyama / Mizrahi-Meissonnier / McClements; summarized in [PMC6068165](https://pmc.ncbi.nlm.nih.gov/articles/PMC6068165/)):
  - Highly deleterious: **LIAVA, MIAVA, LVAVA**
  - Intermediate: LIAIA, LIAVS, MVAVA
  - Minor: LVAIA, LVAIS, MVAIA, MVVVA; **MVAIS** (the normal M exon-3 pattern) — no defect
- **LVAVA** (partial exon-3 skipping — mixed full-length/skipped transcripts, mosaic cone function) and the novel **LIVVA** also occur in OPN1LW; in hybrids carrying LVAVA they produce a nonfunctional/"green" first gene → complete loss of red pigment ([PMC10148663](https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/), [PMC7081934](https://pmc.ncbi.nlm.nih.gov/articles/PMC7081934/)).

**Mechanism 4 — Truncation variants of OPN1LW.** Rare nonsense/frameshift mutations (e.g., R247X, exon 2/3 frameshifts) inactivate the first gene → protanopia; 5/68 protan+eoHM families in Wang 2023 carried truncations ([PMC10148663](https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/), [PMC10182257](https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)).

**Mechanism 5 — Missense mutants.** Single-residue changes that abolish folding, chromophore binding, or trafficking ([PMC13297016 Table](https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/), [PMC10182257](https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/), [PMC6068165](https://pmc.ncbi.nlm.nih.gov/articles/PMC6068165/)):
- **C203R (c.607T>C)** — the **most common missense mutation in human cone opsin**; destroys the Cys110–Cys203 disulfide bond required for folding; occurs in single hybrid L/M genes and in downstream M genes; causes BCM when both expressed genes are hit, and severe protan/deutan defects + cone dysfunction when in one. Arises via a two-step mechanism: NAHR creates a single hybrid gene, then a point mutation introduces C203R ([PMC10906232](https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/), [PMC10182257](https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)).
- **K82E** — L-gene missense; cone dysfunction with reduced acuity and poor color discrimination ([PMC13297016](https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/)).
- **P187S** — reported in the opsin cluster (M-gene context, deuteranopia); predicted to perturb folding ([PMC13297016](https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/)).
- **M273K (c.818T>A, exon 5)** — recombinant pigment shows **no absorbance** at any wavelength (defective 11-cis-retinal binding); documented in both OPN1LW and OPN1MW of a two-gene array ([PMC6068165](https://pmc.ncbi.nlm.nih.gov/articles/PMC6068165/)).
- Others: W177R, P307L, R247X ([PMC10182257](https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/)).

**Relative prevalence summary:** the large majority of protan defects are structural — hybrid-gene replacement or deletion (Mechanisms 1–2). Splice haplotypes (Mechanism 3) are the second major class: in the largest genotype series (Wang 2023, 68 protan/eoHM families), LIAVA in OPN1LW accounted for 29 families, partial-splice haplotypes (LVAVA/LIVVA) 31, LVAVA in a hybrid 3, truncations 5 — though this cohort is selected for high myopia, so pure-CVD population frequencies skew further toward hybrid replacement ([PMC10148663](https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/)). Missense (Mechanism 5) is rare in simple protan, but **C203R in a hybrid gene is the classic severe-protan/BCM mutation**.

---

## 3. State of the Art: Gene Therapy / Translational Work

### 3.1 Primate — the landmark result
- **Mancuso et al., Nature 2009** (Neitz lab): two adult male squirrel monkeys that lacked L-opsin received subretinal **rAAV2/5 carrying human L-opsin under the human L/M-opsin enhancer/promoter pR2.1**. ~15–30% of M cones were transduced to co-express L-opsin; **~20 weeks post-injection the animals gained trichromatic color vision** (Cambridge Colour Test, mf-ERG), discriminating red-green and blue-green from red-violet. Acquired new color vision persisted ≥2 years with no retinal degeneration or inflammation. ([Nature 461:784](https://www.nature.com/articles/nature08401), [PDF](http://www.neitzvision.com/research/publications/publications/2009-Mancuso-Gene_therapy_for_red-green_colour_blindness-Nature.pdf), [PMC4208712 review](https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/), [PMC3073527](https://pmc.ncbi.nlm.nih.gov/articles/PMC3073527/))
- Key implication: **the adult primate retina can integrate a new cone type into pre-existing circuitry without developmental rewiring** — a strong argument that protan correction is achievable even in adults.

### 3.2 Mouse models
- **Knock-in mice** expressing human L-opsin in place of M-opsin (Smallwood 2003; Jacobs 2007) gained weak trichromatic behavior — showing a new cone submosaic suffices in a dichromat, but with much weaker capacity than primates ([PMC4208712](https://pmc.ncbi.nlm.nih.gov/articles/PMC4208712/)).
- **AAV augmentation of L-opsin** in opsin-deficient mouse models (Opn1mw−/−, Opn1mw−/−/Opn1sw−/− DKO, Nrl−/− all-cone "fovea-like" TKO, and C198R/C203R-equivalent models): subretinal **AAV5 or AAV8-Y733F carrying PR2.1-hOPN1LW** rescued cone structure and photopic ERG; **AAV8-Y733F outperforms AAV5**; treatment window is narrow — robust rescue when injected **< ~2–3 months of age**, reduced at ≥5 months as cones degenerate ([PMC9347391](https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/), [Nature s42003-025-09045-0](https://www.nature.com/articles/s42003-025-09045-0), [PLOS ONE 2025 C198RAC](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0332684), [PMC13182793](https://pmc.ncbi.nlm.nih.gov/articles/PMC13182793/)).
- Important caveat for translation: the narrow treatment window applies to **degenerating** cones (BCM models). Simple protanopia cones are viable long-term, so an adult-window therapy is more plausible (cf. stable empty cones in LIAVA carriers, §1).

### 3.3 Clinical / translational status (as of this writing)
- **No human clinical trial has yet been completed for red-green color vision deficiency.** The Neitz lab and Avalanche Biotechnologies announced a licensing deal in 2015 aiming for trials in 1–2 years; it did not materialize ([KPBS 2015](https://www.kpbs.org/news/national/2015/03/25/university-and-biotech-firm-team-up-on-colorblindness-therapy), [Neitz Vision gene-therapy page](http://www.neitzvision.com/research/gene-therapy/)).
- The nearest translational program in the opsin-cluster space is for **blue cone monochromacy**: **BGTF-027 (formerly ADVM-062)**, an **intravitreal** AAV expressing functional L-opsin, developed by Adverum → Blue Gen Therapeutics Foundation; the Vision Center at Children's Hospital Los Angeles received CIRM funding ($4.7M) to prepare a **phase 1 protocol and IND for BCM boys** ([Managed Healthcare Executive](https://www.managedhealthcareexecutive.com/view/gene-therapy-for-rare-eye-disease-to-advance-to-human-trial), [Adverum ADVM-062 preclinical](https://www.cell.com/molecular-therapy-family/molecular-therapy/fulltext/S1525-0016(23)00132-6)).
- AAV cone gene therapy in humans is already clinically precedent-setting via **achromatopsia trials** (CNGA3/CNGB3, e.g., NCT03001310 — 23 participants, acceptable safety, variable efficacy incl. color-vision gains in 6/23), establishing the retinal-AAV delivery and regulatory playbook ([PMC11396370](https://pmc.ncbi.nlm.nih.gov/articles/PMC11396370/)).

### 3.4 Genome editing in the retina (general precedent)
- **Base editing:** in-vivo ABE correction of rhodopsin **E150K** in mice — up to **44%** editing, restored rhodopsin expression/partial functional rescue; strict age dependence ([PNAS 2024](https://www.broadinstitute.org/publications/broad1357371), [NEI news](https://www.nei.nih.gov/research-and-training/research-news/crispr-gene-editing-promising-blinding-disease-retinitis-pigmentosa)). ABE corrected Rpe65 rd12 (~10–29% depending on delivery) ([Frontiers](https://www.frontiersin.org/journals/genome-editing/articles/10.3389/fgeed.2021.775330/full)).
- **Prime editing:** **PE^SpRY** correction of Pde6b^rd10 in mice via dual-AAV — **~41% editing retina-wide, ~76% in transduced cells**, preserved morphology and restored ERG and vision-driven behavior (Qin et al. 2023) — first clinically relevant retinal prime-editing proof of concept ([PMC10035435](https://pmc.ncbi.nlm.nih.gov/articles/PMC10035435/)); PE2 rescue of Rpe65^rd12 via triple-AAV also demonstrated ([Cell Trends Biotechnol review](https://www.cell.com/trends/biotechnology/fulltext/S0167-7799(23)00085-9)).
- **No published base- or prime-editing work targeting OPN1LW/OPN1MW yet** — the strategy below would be among the first.

---

## 4. CRISPR Strategy Options for Protan

### (a) Knock-in of a functional L-opsin gene (HDR-based replacement)
*Pros:* conceptually complete — restores a true L gene in the array.
*Cons:* HDR is extremely inefficient in postmitotic cones (~1.2% with Cas9/HDR vs 11–29% for BE/PE in the same rd12 comparison); requires a DSB (indel risk, potential array rearrangement — this locus is already NAHR-prone); a full OPN1LW cDNA (~1.1 kb) + promoter doesn't fit the AAV payload with editor machinery (prime editor is ~6.3 kb → dual/triple AAV); array recombination triggered by DSBs could worsen the genotype. **Not recommended.**

### (b) Prime-edit the L–M hybrid exons back to L spectral sequence
Targets the expressed hybrid/mis-specified first gene. To convert an M-spectrum pigment (~530 nm) to an L-spectrum pigment (~560 nm), the key edits are the exon-5 residues **F277Y (A285T)** — M→L restores ~21 nm; add **T230I** (+3–4 nm, exon 4) and **S180A→(A180S)** (+3–4 nm, exon 3 — note direction: L has **Ser180**, M has Ala180) and **S233A→(A233S)** (exon 4, minor). Exact M→L residue map ([PMC10946592 Table 3](https://pmc.ncbi.nlm.nih.gov/articles/PMC10946592/)):
- 180: M=Ala → L=Ser (exon 3)
- 230: M=Thr → L=Ile (exon 4)
- 233: M=Ser → L=Ala (exon 4)
- 277: M=Phe → L=Tyr (exon 5)
- 285: M=Ala → L=Thr (exon 5)

*Pros:* fixes the root cause in situ in the correct expression context (first-position gene, native LCR); no exogenous promoter; cones already viable; prime editing is DSB-free and can make several substitutions in one pegRNA (277 and 285 are both in exon 5 — a single pegRNA could conceivably edit both if within ~30–60 bp of the nick, otherwise one pegRNA each).
*Cons:* must edit **the right gene copy** — the array contains multiple near-identical copies (>96–98% identity), so guides must be validated for uniqueness against the full array haplotype of each patient (or, arguably, editing downstream M copies to L spectral type would be tolerable, but changes phenotype); editing efficiency needed in human cones unknown; dual-AAV PE delivery in human retina is unproven; bystander edits near target codons must be screened (exon 5 carries several polymorphic positions).

### (c) Base/prime editing of the LIAVA (and LVAVA) splice-effect variants
Restore splice-competent exon 3. From the pathological haplotype to the normal L **LVAIS** sequence, the nucleotide reversion needed for the principal splice disruptor is **c.532G>A (V178I)** — note the *correction direction is G→A on the coding strand*, which a **C→T base editor on the opposite strand** (or prime editing) achieves; **ABE (A→G) runs the wrong way** for this edit. Optionally also revert c.538T>G (S180A, Ser180 is the L-tuning residue) and c.511/513 (V171I) in one prime-edit "rewrite" of the exon-3 5′ segment. ([PMC4285181](https://pmc.ncbi.nlm.nih.gov/articles/PMC4285181/), [srep28253](https://www.nature.com/articles/srep28253), [PMC8391646](https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/))
*Pros:* single-nucleotide-class edit; corrects both the color defect *and* the associated cone dysfunction/high myopia; mechanistically the cleanest target since correcting only **c.532** may restore splicing (residue 178 protein change I178 is the normal L residue anyway — no conflict between splice code and protein code); LIAVA "empty cones" are structurally stable, so an editing-dose/efficiency window exists.
*Cons:* applies only to the splice-haplotype subpopulation of protan patients (requires genotyping to route patients); restoring splicing in a hybrid gene would still leave M-spectral tuning — for a hybrid carrying LIAVA, you'd also want strategy (b) edits; splice-code restoration must be verified in a minigene/retinal organoid splicing assay before claiming rescue.

### (d) C203R correction where present in a hybrid
C203R is c.607T>C (Cys TGC/CGC → Arg) — a **T→C** coding change; **ABE can correct it via C→T on the opposite strand? No — T→C on the coding strand is achievable by editing the opposite-strand A→G (ABE)**. So an adenine base editor (A→G on the complementary strand) can convert the Arg codon back to Cys; prime editing is also suitable.
*Pros:* the single most common missense lesion in the cluster; disulfide-bond restoration should re-enable folding/trafficking — in-vitro/in-vivo data show folding is the only defect; small, clean edit; C198R mouse + AAV augmentation data (§3.2) prove corrected cones are rescue-competent.
*Cons:* mostly a BCM/severe-cone-dystrophy lesion rather than simple protan; if C203R is also present in the downstream M gene, both copies need editing (two arrays of guides); misfolding may have already caused cone loss depending on age (treatment-window data, §3.2).

### (e) Gene augmentation (AAV-L-opsin) — non-CRISPR benchmark
*Pros:* only approach with primate proof of restored trichromacy (§3.1); nearest to clinic via the BCM program; independent of genotyping complexity; expression of the transgene in a subset of M cones sufficed in monkeys.
*Cons:* not a fix of the underlying allele; requires subretinal (or, for BGTF-027, intravitreal) surgery with attendant risk in a **non-degenerative** condition — the principal barrier regulators/clinicians will flag ([Neitz Vision](http://www.neitzvision.com/research/gene-therapy/)); long-term expression stability and dosing in humans unknown; doesn't address the LIAVA cone-dysfunction/myopia phenotype.

### Comparative ranking (opinion, grounded in §2–3)
1. **(c) splice-haplotype rescue** — most CRISPR-amenable lesion class in protan (few nucleotides, DSB-free editors feasible, cones viable, dual benefit).
2. **(b) hybrid exon-5/3/4 spectral recoding** — addresses the majority mechanism; medium complexity (multi-codon, copy specificity).
3. **(e) augmentation** — most translational maturity but not genome editing.
4. **(d) C203R correction** — niche, valuable where genotype indicates it.
5. **(a) HDR knock-in** — dominated by the above; not recommended.

---

## 5. Recommended Target Region(s)

**Primary recommendation: exon 5 of the first-position (expressed) hybrid gene — codons 277 and 285 — via prime editing.**
Reasoning:
- Residues 277/285 are the **binary L/M determinant** (~16–24 nm); converting F277→Y and A285→T flips the expressed pigment from M-class (~530 nm) to L-class (~556–560 nm) even in a hybrid backbone ([jamanetwork 413200](https://jamanetwork.com/journals/jamaophthalmology/fullarticle/413200), [PMC10946592](https://pmc.ncbi.nlm.nih.gov/articles/PMC10946592/)).
- Both codons lie in one exon (~300 bp), enabling one or two pegRNAs per codon with a shared editor; the hybrid's exon 5 is typically fully M-derived, so a single edit zone per patient.
- Protein-level outcome is well-understood (spectral tuning, not folding), and M→L substitutions at 277/285 are known to fold and bind chromophore (they are the normal L sequence).

**Secondary target: exon 3 splice region (c.532, and optionally c.511/513, c.538) for LIAVA/LVAVA patients** — route by genotyping; correct with CBE (for c.532 G→A via opposite-strand C→T) or prime editing; verify splice restoration first in minigene assay. Optionally combine with the 180 (A→S) edit in the same exon to also restore the full L-tuning residue set ([PMC4285181](https://pmc.ncbi.nlm.nih.gov/articles/PMC4285181/), [PMC8391646](https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/)).

**Tertiary (optional refinement): exon 4 codons 230 (T→I) and 233 (S→A)** add ~3 nm each toward L — worthwhile only if the exon-5 edits leave a residual protanomalous gap; the hybrid's exons 2–4 are usually a mosaic, so evaluate per genotype.

**Design constraints to honor:** (i) guide specificity across all array copies (patient-specific long-read array haplotyping is a prerequisite); (ii) dual-AAV or non-viral delivery sized for PE (or single-AAV for CBE); (iii) retinal delivery route — subretinal proven, intravitreal emerging (ADVM-062 capsid, §3.3); (iv) bystander-edit audit in exon 5 (codons 274, 275, 279, 298, 309 are polymorphic).

---

## 6. Key Papers & Resources

1. Mancuso K, Hauswirth WW, Li Q, Connor TB, Kuchenbecker JA, Mauck MC, Neitz J, Neitz M. **Gene therapy for red–green colour blindness in adult primates.** *Nature* 461:784–787 (2009). https://www.nature.com/articles/nature08401 (PDF: http://www.neitzvision.com/research/publications/publications/2009-Mancuso-Gene_therapy_for_red-green_colour_blindness-Nature.pdf)
2. Neitz M, Neitz J. **Intermixing the OPN1LW and OPN1MW Genes Disrupts the Exonic Splicing Code Causing an Array of Vision Disorders.** *Genes* 12(8):1180 (2021). https://pmc.ncbi.nlm.nih.gov/articles/PMC8391646/
3. Wang Y, Sun W, Xiao X, et al. **Unique Haplotypes in OPN1LW as a Common Cause of High Myopia With or Without Protanopia.** *Invest Ophthalmol Vis Sci* 64(4):29 (2023). https://pmc.ncbi.nlm.nih.gov/articles/PMC10148663/
4. Mizrahi-Meissonnier L, et al. / **Three Different Cone Opsin Gene Array Mutational Mechanisms** (incl. c.532A>G as principal splice disruptor). https://pmc.ncbi.nlm.nih.gov/articles/PMC4285181/
5. Ueyama H, et al. **De novo intrachromosomal gene conversion from OPN1MW to OPN1LW…** *Sci Rep* 6:28253 (2016). https://www.nature.com/articles/srep28253
6. Neitz M, Neitz J. **Photopigment genes, cones, and color update: disrupting the splicing code causes an array of vision disorders.** *Curr Opin Behav Sci* (2019). https://pmc.ncbi.nlm.nih.gov/articles/PMC7081934/
7. **Cone Opsins and Inherited Retinal Disease** (2025 review; mutation tables incl. K82E, P187S, C203R, M273K). https://pmc.ncbi.nlm.nih.gov/articles/PMC13297016/
8. Mizrahi-Meissonnier L / **Blue Cone Monochromacy and Gene Therapy.** *Int J Mol Sci* (2023). https://pmc.ncbi.nlm.nih.gov/articles/PMC10182257/
9. Mizuno S, et al. **Genotype determination of the OPN1LW/OPN1MW genes… Japanese BCM patients** (M273K; haplotype severity classes). *Sci Rep* (2018). https://pmc.ncbi.nlm.nih.gov/articles/PMC6068165/
10. **Structural and functional rescue of cones carrying the most common missense mutation (C203R)** — C198R mouse rescue. https://pmc.ncbi.nlm.nih.gov/articles/PMC10906232/
11. Deeb SS. **Molecular genetics of colour vision deficiencies.** *Clin Exp Optom* (2004/2005). https://www.blueconemonochromacy.org/wp-content/uploads/2011/08/Deeb_2004.pdf
12. **Gene Therapy in Opn1mw−/−/Opn1sw−/− Mice** (AAV5 PR2.1-hOPN1LW; timing). *Adv Exp Med Biol* (2022). https://pmc.ncbi.nlm.nih.gov/articles/PMC9347391/
13. **Molecular mechanisms limiting the AAV gene therapy treatment window in BCM mouse models** (AAV8-Y733F > AAV5). *Commun Biol* (2025). https://www.nature.com/articles/s42003-025-09045-0
14. **Gene therapy rescues cone function in an all-cone retina mouse model of BCM (C198RAC).** *PLOS ONE* (2025). https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0332684
15. Qin H-Z, et al. — **prime editing Pde6b^rd10** (via [PMC10035435](https://pmc.ncbi.nlm.nih.gov/articles/PMC10035435/) review, "Eye on genome editing"). Original: *EMBO Mol Med* / Cell reports 2023.
16. Du SW, Newby GA, … Liu DR, Palczewski K. **In vivo photoreceptor base editing ameliorates rhodopsin-E150K RP in mice.** *PNAS* (2024). https://doi.org/10.1073/pnas.2416827121
17. **Formulae for generating standard and individual human cone spectral sensitivities** (Table 3: spectral shifts of the 7 tuning residues). https://pmc.ncbi.nlm.nih.gov/articles/PMC10946592/
18. OMIM 303900 (protan colorblindness). https://www.omim.org/entry/303900
19. MedlinePlus Genetics: OPN1LW. https://medlineplus.gov/genetics/gene/opn1lw/
20. **Adaptive Optics Imaging of Inherited Retinal Disease** (cone mosaic integrity in dichromats). https://pmc.ncbi.nlm.nih.gov/articles/PMC10317068/
21. Managed Healthcare Executive: **BGTF-027 (ex-ADVM-062) BCM gene therapy advancing to phase 1 prep at CHLA.** https://www.managedhealthcareexecutive.com/view/gene-therapy-for-rare-eye-disease-to-advance-to-human-trial
22. Neitz Vision — gene therapy program page (risks/limitations for human translation). http://www.neitzvision.com/research/gene-therapy/

---

## 7. Open Questions

1. **Copy-specificity in the array:** can a single guide reliably distinguish the first-position gene from downstream OPN1MW copies (98% identity)? Does off-target editing of a second M gene matter phenotypically (it would also shift its spectrum toward L)? Long-read array haplotyping is a prerequisite; no published answer yet.
2. **Editing efficiency threshold in cones:** what fraction of L-position cones must be corrected for measurable trichromacy? Primate augmentation worked with 15–30% transduction of M cones, suggesting a lenient threshold, but no editing-equivalent data exist.
3. **Prime-editor delivery at scale to human cones:** dual-AAV PE in human foveal cones is unproven; the rd10 work (41% retina-wide) is the only in-vivo benchmark; intravitreal delivery of editors is likely beyond current capsid capacity.
4. **Does corrected splicing rescue the myopia/cone-dysfunction phenotype** of LIAVA carriers, or only color vision? (Cone gaps in LIAVA retinas suggest partial degeneration; "empty cones" are stable, but the two phenotypes—simple protanopia vs eoHM—may have different editability windows.)
5. **Behavioral integration after correction:** Mancuso 2009 shows adult primates integrate a *new* pigment; does a *shifted* pigment in already-wired cones integrate even more readily (predicted yes, but untested)?
6. **Bystander edits in exon 5** (polymorphic codons 274, 275, 279, 298, 309): acceptability thresholds and screens; no retinal-PE bystander data for this locus.
7. **Regulatory path for enhancement-type therapy:** protanopia is non-degenerative with normal acuity; subretinal surgery risk vs. benefit calculus remains the chief clinical barrier regardless of modality (Neitz lab explicitly flags this).
8. **Hybrid-gene exon boundaries:** hybrid fusion points vary (introns 1–4); the exact 5′L–3′M junction in each patient determines which exons carry M-derived sequence, so the edit set (exon 3/4/5) must be individualized — no standardized panel exists.
9. **ABE vs CBE vs PE for each lesion class:** c.532G>A needs G→A (CBE/PE); c.607T>C (C203R) needs T→C (ABE via opposite strand/PE); exon-5 recoding needs transversions at some positions (PE mandatory). Optimal editor choice per genotype is a design-stage question.
10. **Long-term expression and immunogenicity** of edited cones (no re-dosing option in the eye) — unknown for editing, partially answered for AAV augmentation (≥2 years in monkeys).
