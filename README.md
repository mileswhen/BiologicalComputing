# Overview

A proposal to enable faster cellular finite-state-machines. Basic idea is to use a cache hierarchy: construct a fast cache using transcription regulation (CRISPRi + CRISPRa), and a slow cache using an existing concept (DOMINO operator). The main innovation would be to transfer principles from computer architecture, and construct an SR latch using CRISPR. We could maybe speed up DOMINO if we could make base editors dissociate faster. It's been shown in single-molecule experiments that they take hours to dissociate. One idea could be to engineer a "toehold" switch sgRNA. This would destabilize the base editor *only* after it deaminates the right base.

See `proposal.pdf` and `slides.pdf` for more detail.


## Resources
### Biological Computing
* `slides` [Adleman's First Demonstration of DNA Computing](https://users.cs.duke.edu/~reif/courses/molcomplectures/DNA.Computing.Adleman/DNA.Computing.Adleman.pdf)
* `paper` [A Sticker-Based Model for DNA Computation](https://doi.org/10.1089/cmb.1998.5.615) 
* `review` [DNA computing for combinational logic](https://link.springer.com/content/pdf/10.1007/s11432-018-9530-x.pdf) 
* `website` [Cellular state machines for programming complex, state-dependent genetic circuits](https://tlo.mit.edu/technologies/cellular-state-machines-programming-complex-state-dependent-genetic-circuits#:~:text=State%20machines%20can%20exist%20in,response%20to%20chemical%20inducer%20inputs.)

### CRISPR-Cas Information Processing
* `paper` [A CRISPR/Cas9-based central processing unit to program complex logic computation in human cells](https://www.pnas.org/doi/10.1073/pnas.1821740116) `paper`
* `paper` [Single-Nucleotide-Resolution Computing and Memory in Living Cells](https://doi.org/10.1016/j.molcel.2019.07.011)
* `paper` [Multistable and dynamic CRISPRi-based synthetic circuits](https://www.nature.com/articles/s41467-020-16574-1) 
* `book` [Ch5. Positive Feedback, Bistability and Memory](https://doi.org/10.1201/9781420011432) 
* `paper` [Synthesizing AND gate genetic circuits based on CRISPR-Cas9 for identification of bladder cancer cells](https://doi.org/10.1038/ncomms6393)

### Information Storage
* `paper` [Nucleic Acid Databases and Molecular-Scale Computing](https://pubs.acs.org/doi/pdf/10.1021/acsnano.9b02562)
* `review` [DNA storage: research landscape and future prospects](https://doi.org/10.1093/nsr/nwaa007) 

### Theoretical Computing
* `wiki` [Von Neumann architecture](https://en.wikipedia.org/wiki/Von_Neumann_architecture) 
* `slides` [Cache, Parallelism, Concurrency](https://www.cse-lab.ethz.ch/wp-content/uploads/2021/10/Cache-and-Concurrency.pdf) 
* `slides` [Instruction / Data Level Parallelism](https://www.cse-lab.ethz.ch/wp-content/uploads/2021/10/ILP-DLP.pdf) 
* `review` [bit slicing](https://dl.acm.org/doi/pdf/10.5555/1074100.1074172) 
	>Bit slicing refers to the technique of constructing an
	m-bit arithmetic-logic unit (ALU) by interconnecting a
	set of identical n-bit (n 5 m) LSI chips called bit slices
* `wiki` [Automata Theory](https://cs.stanford.edu/people/eroberts/courses/soco/projects/2004-05/automata-theory/basics.html) 
* `diagram` [Automata classes](https://upload.wikimedia.org/wikipedia/commons/a/a2/Automata_theory.svg) 

### Comp Architecture
* `course` [ETHz: Digital Design & Computer Architecture 2021](https://safari.ethz.ch/digitaltechnik/spring2021/doku.php?id=schedule)
* `course` [Oxford: Microcontroller Systems 2014](https://www.robots.ox.ac.uk/~dwm/Courses/2CO_2014/)


## Questions to address
* fast-response to complex stimulus. Transient state preservation. As a tool to re-program gene circuits (modulo counter that changes the write address).
* encode some information in RNA to be written (PE)?
* use roofline model to conceptualize the problem?
* How to control write error? Less error-prone writer or error correction. Maybe use PE to reset cache?
* any advantage to making this synchronous via clocks?
