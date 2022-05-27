---
title: | 
			 \vspace{-2cm}High(er) Performance Biological Computing:\
			 CRISPR-based caching
author: "Miles Wang-Henderson"
date: "May 2022"
header-includes: 
	- \usepackage{endnotes}
	- \renewcommand{\notesname}{References}
	- \let\footnote=\endnote
...

An established paradigm for biological computing has been to use exploit bistable states to construct combinatorial logic gates.[^crisprcpu] Recent work has advanced these principles, demonstrating that complex *sequential* logic circuits can be produced using protein-based toggle switches. [^checkpoint] [^domino] These solutions are typically hindered by two issues. 1) The number of *orthogonal* proteins that can be expressed concurrently is limited. 2) The *latencies* that accumulate in the operation of a sequential circuit make it difficult to quickly perform signal processing, computation, and finally actuatation in response to transient stimuli.

Modern computing architectures typically address the issue of latency by dividing memory into a hierarchy, exploiting the spatial locality of fast caches to reduce latency. In order to enable programmable responses to transient signals, we propose to analogously design a set of fast and slow caches, by exploiting the orthogonality of CRISPR-based systems. 

### Aim 1. Fast caching: design a bistable CRISPR-based toggle switch that is cooperative, specific, and robust to perturbations.

**Challenge:** In computer architecture, one bit of "fast memory" is constructed using the same topology as a biological toggle-switch. The only implementation of a CRISPRi toggle-switch thus far has relied on unspecific off-target binding to achieve bistability. [^crispri] 
**Approach:** A canonical toggle-switch requires cooperativity. We will exploit the aptamer construct used in synergistic activation mediators (SAMs). Instead of recruiting multiple MS2 chimeras to enhance transcription, we will repurpose the system to enable cooperative binding: one dCas9-VP64 recruits additional dCas9-VP64 to the promoter. This produces a multiplicative effect and makes expression of gRNA a non-linear function of itself.
**Impact:** No off-target binding needed, which does not scale. Using enhancers would increase kinetics, making our fast cache even faster (minutes).

### Aim 2. Slow caching: improve the DOMINO operator to reduce latency from days to hours.

**Challenge:** DOMINO encodes information in DNA using base editors. These operators could in principle be used to construct an addressable memory, that can be written-to or read *in vivo*. However, sequential base editing is slow, on the order of days, and is rate-limited by slow dissociation of spCas9 (hours).
**Approach:** Engineer a toehold switch gRNA that preferentially hybdridizes to the non-target strand only after deamination by the base editor. 
**Impact:** This could disrupt the binding kinetics and increase dissociation rates whilst preserving editing efficiency.

### Aim 3. Protein engineering of Cas9 to optimize the association and dissociation kinetics of cache systems.

**Challenge:** For both systems, ideally association rates are high and dissociation rates are not too low. S. aureus Cas9 has naturally faster dissociation rates, but the mechanism has been tied to double strand breaks. [^sau]
**Approach:** Deep mutational scan of SauCas9 to enable rational mutagenesis.
**Impact:** This increases the turnover, and transfer of information. Enabling even faster sequential logic and response to signals.

Our project would open up more complex gene circuits to perform fast, context-aware signal processing. Using the above innovations, the main advantages are 1) computation would occur quickly, and is rate-limited by the latency of the fastest cache. 2) decoupling slow caches from computation allows us to use them for long-term memory storage or molecular recording.

\theendnotes

[^checkpoint]: Andrews, L., Nielsen, A., & Voigt, C. (2018). Cellular checkpoint control using programmable sequential logic. Science, 361(6408). doi: 10.1126/science.aap8987
[^crisprcpu]: Kim, H., Bojar, D., Fussenegger, M. (2019). A CRISPR/Cas9-based central processing unit to program complex logic computation in human cells. PNAS. https://doi.org/10.1073/pnas.1821740116
[^crispri]: Santos-Moreno, J., Tasiudi, E., Stelling, J. et al. Multistable and dynamic CRISPRi-based synthetic circuits. Nat Commun 11, 2746 (2020). https://doi.org/10.1038/s41467-020-16574-1
[^domino]: Farzadfard, F., Lu, T.K., et al. (2019) Single-Nucleotide-Resolution Computing and Memory in Living Cells. Molecular Cell. https://doi.org/10.1016/j.molcel.2019.07.011
[^sau]: Yourik, P., Fuchs, R. T., Mabuchi, M., Curcuru, J. L., & Robb, G. B. (2019). Staphylococcus aureus Cas9 is a multiple-turnover enzyme. RNA (New York, N.Y.), 25(1), 35–44. https://doi.org/10.1261/rna.067355.118
