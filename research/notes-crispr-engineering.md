# CRISPR engineering constraints for retinal in-vivo editing — working notes (raw, cited)

Status: gathering. Final dossier at research/60-crispr-engineering.md.

## 1. Editors, sizes, PAMs

- rAAV packaging limit <4.7 kb; hypercompact systems (CjCas9, SaCas9, Cas12f) enable single-vector in vivo delivery. Nature Gene Therapy 2025: https://www.nature.com/articles/s41434-025-00573-2
- SpCas9 CDS = 4,098 bp (~4.1 kb); SaCas9 = 3.2 kb. https://pmc.ncbi.nlm.nih.gov/articles/PMC9589773/
- CasMINI (engineered Cas12f, 529 aa / ~1.55 kb) fits single AAV; ABE8e-CasMINI tether fits AAV packaging (Xu et al.). https://pmc.ncbi.nlm.nih.gov/articles/PMC9569511/ ; CasMINI_v3.1/ge4.1 subretinal in Rho-P23H/+ mice: >70% editing in transduced retinal cells, Nr2e3 target. https://onlinelibrary.wiley.com/doi/10.1002/advs.202308095
- CasMINI PAM TTTR; Cas12a TTTV/TTTN; CasMINI editing window 3–4 bp downstream of PAM — constrains targetability. https://pmc.ncbi.nlm.nih.gov/articles/PMC9569511/
- CBE/ABE + gRNA ≈ 6 kb; prime editors >7 kb — beyond single AAV. https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/
- PAMs: SpCas9 NGG (3'); SaCas9 NNGRRT (3'); engineered: SaCas9 NNNRRT (Kleinstiver), SpG/SpRY near-PAM-less. https://pmc.ncbi.nlm.nih.gov/articles/PMC12204363/ ; https://www.nature.com/articles/s41592-020-0861-5 ; https://www.cell.com/molecular-therapy-family/molecular-therapy/fulltext/S1525-0016(23)00061-8
- eSaCas9-NNG engineered variant recognizes relaxed NNG PAM with reduced off-targets. https://www.nature.com/articles/s41467-026-71626-2
- Guide lengths: SpCas9 20 nt; SaCas9 21 nt; CjCas9 22 nt optimal. https://www.nature.com/articles/s41467-026-71626-2
- CEP290 LCA10 IVS26 c.2991+1655A>G: SaCas9, single AAV5, two guides; NHP editing 27.9±20.7% at 1e12 vg/mL. https://pmc.ncbi.nlm.nih.gov/articles/PMC7987357/

## 2. DSB risks / why base & prime editing in post-mitotic photoreceptors

- Nuclease DSBs → heterogeneous indels, AAV genome integration, chromosomal abnormalities; base editing avoids DSBs. Rho-E150K PNAS: https://www.pnas.org/doi/10.1073/pnas.2416827121
- HDR is cell-cycle restricted (S/G2); low in postmitotic retina. https://pmc.ncbi.nlm.nih.gov/articles/PMC10768554/
- rd10 Pde6b ABE via dual-AAV8 split-intein: up to 20.8% DNA-level, 55% cDNA-level correction. https://pmc.ncbi.nlm.nih.gov/articles/PMC9996133/
- Split-ABE (Rma inteins) dual-AAV2 retina: ~20–25% A-to-G at NR2E3 splice donor in adult mouse retina. https://onlinelibrary.wiley.com/doi/full/10.1002/smtd.202000309
- Dual-AAV CBE/ABE (PHP.B or Anc80 capsid) subretinal, 2-wk mice: 19–26% rod editing. Mol Ther review: https://www.cell.com/molecular-therapy-family/molecular-therapy/fulltext/S1525-0016(21)00457-3
- Base editing in cones: Choi et al. 2022 — lasting cone-function improvement, prevented photoreceptor degeneration. (via https://pmc.ncbi.nlm.nih.gov/articles/PMC10460145/)

## 3. Delivery (partial)

- Dual-AAV split-intein is the standard route for full-length base editors; efficiency penalty vs single vector. https://pmc.ncbi.nlm.nih.gov/articles/PMC13412194/
- Compact ABEs fitting single AAV: SaCas9/Nme2/CjCas9-based, minimized regulatory elements. https://pmc.ncbi.nlm.nih.gov/articles/PMC13412194/
- AAV serotypes 2,5,6,7,8,9 + engineered AAV2-7m8, AAV9-PHP.eB transduce photoreceptors subretinally. https://pmc.ncbi.nlm.nih.gov/articles/PMC12655462/
- AAV2 (native), AAV2.7m8 — 7m8 (exAtoh7 promoter studies). TODO: capsid details, promoters PR2.1/PR1.7/hCAR/hG1.7, cone tropism, subretinal vs intravitreal.
