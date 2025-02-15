# GWAS
# Identified high genetic diversity, surpassing that of modern European winter bread wheat varieties.
# Utilized data from the "Establishing the A. E. Watkins landrace cultivar collection as a resource for systematic gene discovery in bread wheat" (2014) to conduct Genome-Wide
# Association Studies (GWAS). The following points outline the samples and data used in the study:
      # Sample Size: 826 landrace cultivars of bread wheat (Triticum aestivum L.).
      # Genotyping Markers: 41 microsatellite markers employed for genetic analysis.
      # Geographic Diversity: Cultivars collected from 32 countries across Asia, Europe, and Africa.
      # Comparison Group: Genetic diversity compared with modern European winter bread wheat varieties from 1945 to 2000.

# -------------------------------------

#Intaliing GAPIT
source("http://zzlab.net/GAPIT/GAPIT.library.R")
source("http://zzlab.net/GAPIT/gapit_functions.txt")

#Importing Genotyping data

myG<-read.table("~/GWAS/Watkins_axiom35k_genotype.hmp.txt",head = FALSE)

#Import Phenotyping data
myY <- read.table("~/GWAS/Watkins_phenotype_H2006.txt", head = TRUE)

#Running GWAS
myGAPIT<-GAPIT(
Y=myY,
  G=myG,
  PCA.total=5,
  SNP.MAF =0.03,
  Multiple_analysis = TRUE,
  model=c("GLM","MLM"),
  Random.model=FALSE
)



