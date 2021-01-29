### Visualizing synteny of *Eois olivacea* genome compared with model lepidopteran genomes

#### *Bombyx mori*

To begin, I downloaded the *Bombyx mori* genome from [silkbase](http://silkbase.ab.a.u-tokyo.ac.jp/cgi-bin/download.cgi). For synteny analysis, I analyzed only the 28 *B. mori* chromosomes. 

I also subset the *E. olivacea* genome to the largest 29 scaffolds. These scaffold lengths were similar or slightly longer, on average, than the *B. mori* chromosome lengths, which gave me some hope that they represented chromosomes or near-complete chromosomes. 

However, the results of the synteny alignment were not what I expected (see figure below). Its almost as though the *E. olivacea* chromosomes have been fused (e.g., scaffolds 29, 28, 27, 12, 11, 10, etc.). Because these results were unexpected, I naturally looked at the raw linkages to see whether something had simply gone awry during the process of plotting. But the circos graph reflects the linkages inferred by the whole-genome synteny alignment program. 

##### Satsuma 
Satsuma is a whole-genome synteny alignment program. It takes two genomes, computes alignments, and then keeps only the parts that are orthologous, i.e. following the conserved order and orientation of features, such as protein coding genes, non-coding genes, or neutral sequences. Satsuma does not require any pre-processing, such as repeat masking, since it will automatically detect ambiguous mappings.

I used default Satsuma parameters, similarly to other genome reports using Lepidopteran genomes. 

Results don't change whether Eoli or Bomo is the target genome (-t): 
```
/data/gpfs/home/kuckele/local/bin/satsuma-code/SatsumaSynteny -q /data/gpfs/assoc/denovo/kuckele/eois_genome/fasta/Bomo_chromosome_assembly.fa -t /data/gpfs/assoc/denovo/kuckele/eois_genome/fasta/Eoli_chromosome_assembly.fa -o xcorr_bmori_chromosomes_default 

```

To convert Satsuma output into a format that can be processed by Circos:
```
/data/gpfs/home/kuckele/local/bin/satsuma-code/BlockDisplaySatsuma -i satsuma_summary.chained.out -t /data/gpfs/assoc/denovo/kuckele/eois_genome/fasta/Eoli_chromosome_assembly.fa -q /data/gpfs/assoc/denovo/kuckele/eois_genome/fasta/Bomo_chromosome_assembly.fa > blockdisplayview.txt

grep '^Bomo_Chr' blockdisplayview.txt | cut -f 1,2,3,5,6,7 > blockdisplay_simple.txt
```

##### Visualized with Circos
Circos is a software package for visualizing data and information. It visualizes data in a circular layout — this makes Circos ideal for exploring relationships between objects or positions.

![circos_edit](https://user-images.githubusercontent.com/30299787/106081062-20377680-60cd-11eb-8575-1128359115f0.jpg)
