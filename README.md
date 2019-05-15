# CorvusDFE
Distribution of fitness effects of several species in the genus Corvus

Custom python scripts used in bioinformatics analysis for Kutschera et al.

# findCpGpolymorphism.py
- Takes a gzipped VCF file containing variant and monomorphic/invariant sites, and finds the positions of CpG, CpA and TpG sites, incl CpG/CpA and TpG/CpG polymorphisms within the resequencing data.
- Not only REF and ALT, but also allele frequency (AF) and genotype information (individual GT) are considered. 
- Site pairs with positions not directly adjacent to each other will be ignored. 
- The output is printed to a bed file.
- Written for VCF files generated with GATK 3.4.0.
- Requires python 2.7.

# setGenotypesMissing.py
- Takes a gzipped VCF file to set a specific number of genotypes randomly to missing (./.) for each site until a certain number of called genotypes remains per site. 
- The aim is to obtain a VCF file in which each site contains the same number of actually called genotypes, e.g. 30 out of 115. In this case, 85 randomly picked genotypes need to be set to missing per site. 
- A tool like vcftools (https://vcftools.github.io/index.html) should be run before, deleting sites with more than a certain number of genotypes missing, e.g. 85 as in the example above.
- Requires python 2.7.
