### Visualizing synteny of *Eois olivacea* genome compared with model lepidopteran genomes

#### *Bombyx mori*

##### Satsuma 
Satsuma is a whole-genome synteny alignment program. It takes two genomes, computes alignments, and then keeps only the parts that are orthologous, i.e. following the conserved order and orientation of features, such as protein coding genes, non-coding genes, or neutral sequences. Satsuma does not require any pre-processing, such as repeat masking, since it will automatically detect ambiguous mappings.

```
/data/gpfs/home/kuckele/local/bin/satsuma-code/SatsumaSynteny -q /data/gpfs/assoc/denovo/kuckele/eois_genome/fasta/Eoli_chromosome_assembly.fa -t /data/gpfs/assoc/denovo/kuckele/eois_genome/fasta/Bomo_chromosome_assembly.fa -o xcorr_bmori_chromosomes -m 1 -ni 10 -n 30

```

##### Visualized with Circos
Circos is a software package for visualizing data and information. It visualizes data in a circular layout — this makes Circos ideal for exploring relationships between objects or positions.

![circos_edit](https://user-images.githubusercontent.com/30299787/106081062-20377680-60cd-11eb-8575-1128359115f0.jpg)
