# Phylogenetic_Analysis_Zika_Virus2
I've analyzed Zika virus genomes. I started by checking and trimming raw sequencing data with FastQC and Trimmomatic, then assembled consensus genomes. I then curated a global dataset from NCBI, downsampling it by country and date. I aligned all sequences with MAFFT, cleaned the alignment, and built a phylogenetic tree using IQ-TREE and iTOL.

## **Phylogenetic Analysis of Zika Virus Genomes** 🦠

This project details a complete bioinformatics pipeline for generating and analyzing Zika virus genomes. The primary goal was to place two local Zika isolates within a broader global phylogenetic context.

***

### **Workflow Summary**

* **Raw Data Processing**: Quality control and adapter trimming of FASTQ files.
* **Consensus Sequence Generation**: Assembly of local Zika isolates.
* **Global Dataset Curation**: Downsampling and retrieving Zika genomes from NCBI.
* **Multiple Sequence Alignment (MSA)**: Alignment of all sequences and data cleaning.
* **Phylogenetic Tree Inference**: Building and visualizing a rooted phylogenetic tree.

***

### **Methods and Tools**

This section lists the specific tools and commands used, making the analysis reproducible.

#### **1. Data Acquisition and Preprocessing**

* **Raw Data**: Two local Zika virus samples, `zika_s1` and `zika_s2` (mention the source if it is public).
* **Global Data**: Zika virus sequences were downloaded from the NCBI Virus database.
* **Quality Control**: Performed with **FastQC**.
* **Trimming**: **Trimmomatic** was used to trim low-quality reads and primer sequences.
* **Consensus Assembly**: (Mention the assembler you used, e.g., BWA, SAMtools, etc.).

#### **2. Dataset Curation**

* **NCBI Filtering**: Sequences were filtered for a minimum length of 8500 bp.
* **Downsampling**: A **Jupyter Notebook** was used to select a representative subset of sequences based on country, year, and month.
* **FASTA Retrieval**: A custom script was used to fetch the FASTA files for the filtered accession numbers.

#### **3. Phylogenetic Analysis**

* **Multiple Sequence Alignment (MSA)**: **MAFFT** was used to align the combined dataset.
* **Alignment Cleaning**: **Seqkit** was used to remove duplicate sequences and sequences with ambiguous 'N' bases.
* **Tree Inference**: **IQ-TREE** was used to construct a maximum-likelihood phylogenetic tree using the **GTR+G substitution model**.
* **Visualization**: **iTOL** was used to visualize the final tree, which was rooted with a specific reference genome (e.g., `KU729217.2_Zika_virus_isolate`).

***

# Repository Contents

* `raw_data/`: Directory containing the initial FASTQ files.
* `trimmed_data/`: Directory containing the Trimmomatic output files.
* `consensus_genomes/`: FASTA files for the final consensus sequences of `zika_s1` and `zika_s2`.
* `ncbi_accessions.txt`: A list of the accession numbers used for the global dataset.
* `ncbi_sequences.fasta`: The FASTA file for the downsampled NCBI sequences.
* `combined_alignment.fasta`: The final MAFFT alignment file.
* `iqtree_run.log`: The log file from the IQ-TREE analysis.
* `combined_alignment.fasta.treefile`: The final phylogenetic tree in NEWICK format.
* `tree_visualization.svg`: A high-quality image of the final tree, as visualized in iTOL.


# Conclusion

The resulting phylogenetic tree provides a clear visual representation of the evolutionary relationships among the Zika virus sequences. The two local isolates were successfully placed within the tree, allowing for a better understanding of their origin and spread.
