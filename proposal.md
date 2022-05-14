% CRISPR caching to enable High Performance Biological Computing
% Miles Wang-Henderson
% 12 May 2022

The native framework of instruction-execution that CRISPR/Cas provides has recently enabled highly programmable information processing for logical operations. Specifically, a CRISPRi system was repurposed as an arithmetic logical unit (ALU); and guide RNA defined the "software" layer, whereby logical operations could be controlled combinatorially. [^crisprcpu]

An established paradigm for biological computing has been to use genetic circuits for boolean logic, a natural choice given its intrinsic appearance in cellular signal processing. These synthetic circuits are typically constructed in a static manner. In this regime, the circuit's topology remains fixed and is thus restricted to one-to-one input-output mappings.

More recent work has advanced these principles, allowing dynamic CRISPRi genetic circuits to also be synthesized, which accommodate a small number of stable states (usually two), and afford conditional mappings.[^crispri] However, instances of these networks remain fixed after instantiation (insertion into genome), and one can not take advantage of the computational formalism afforded by higher order automata which make it possible for external instructions to modify behavior via transitions from one internal state to another.

In vivo information storage on DNA substrate has been recently been applied to read-write operations (DOMINO), as well as write-only operations (Record-seq). [^domino] DOMINO makes use of self-targeted C-to-T base editing to encode instruction-level information within a DNA register. Each register consists of a "READ-address" protospacer and a "WRITE-address" for information storage. There are three notable disadvantages to this approach: 1) the overhead of base editing results in an approximately 8 hour latency to achieve a saturating output signal, 2) The use of a single deaminase leads to irreversible sequential filling of available memory and prevents reversible caching, 3) deamination by-products lead to destruction of registers.

Modern computing architectures typically address the issue of latency by dividing memory into a hierarchy, exploiting the spatial locality of smaller caches to reduce latency. We propose to analogously design a set of fast and slow caches, by exploiting concentration-dependent stable states (guide RNA) as fast registers, and slow DNA encoding as main memory. Potential issues to address will be to make caching reversible using prime editing instead of deaminases, how to transfer information between fast caches and slow caches, and the design of registers compatible with prime editing.

[^crisprcpu]: Kim, H., Bojar, D., Fussenegger, M. (2019). A CRISPR/Cas9-based central processing unit to program complex logic computation in human cells. PNAS. https://doi.org/10.1073/pnas.1821740116
[^crispri]: Santos-Moreno, J., Tasiudi, E., Stelling, J. et al. Multistable and dynamic CRISPRi-based synthetic circuits. Nat Commun 11, 2746 (2020). https://doi.org/10.1038/s41467-020-16574-1
[^domino]: Farzadfard, F., Lu, T.K., et al. (2019) Single-Nucleotide-Resolution Computing and Memory in Living Cells. Molecular Cell. https://doi.org/10.1016/j.molcel.2019.07.011

