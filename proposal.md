# A CRISPR Finite State Machine

The native framework of instruction-execution that CRISPR/Cas provides has recently enabled highly programmable information processing for logical operations. Specifically, a CRISPRi system was repurposed as a logical unit; and guide RNA defined the "software" layer, whereby logical operations could be controlled combinatorially. [^crisprcpu]

An established paradigm for biological computing has been to use genetic circuits for boolean logic, a natural choice given its intrinsic appearance in cellular signal processing. Synthetic circuits have been exploited to extend cellular physiology, by extending signalling processing to enable extrinsic functionality. These synthetic cricuits are typically constructed in a static (injective) manner. In this regime, the circuit's topology remains fixed and is thus restricted to one-to-one input-output mappings.

More recent work has advanced these principles, allowing dynamic CRISPRi genetic circuits to also be synthesized, which accommodate two internal states, and afford conditional mappings, but instances of these networks remain fixed after instantiation (insertion into genome), and one can not take advantage of the computational formalism afforded by higher order automata that allow external instructions to modify behavior via transitions from one internal state to another.

In vivo information storage on DNA substrate has been succesfully applied to write-only operations like transcriptional recording [^recordseq]. Here we propose to extend this principle and design a set of registers that allow for fast and reversible state transitions, using self-targeted Prime Editing (PE). Potential problems to address will be targeting for read and write operations, orthogonalizing storage, and ensuring fast state transitions.

[^crisprcpu]: [A CRISPR/Cas9-based central processing unit to program complex logic computation in human cells](https://www.pnas.org/doi/10.1073/pnas.1821740116)
[^recordseq]: [Recording transcriptional histories using Record-seq](https://www.nature.com/articles/s41596-019-0253-4#:~:text=In%20contrast%20to%20RNA%2Dseq,of%20plasmid%2Dborne%20CRISPR%20arrays.)
