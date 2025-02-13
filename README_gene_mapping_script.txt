README_gene_mapping_script_v2
Fredrik Wermeling, PhD

The script was developed and successfully executed using RStudio version 2024.12.0 Build 467, and R version 4.4.1, using the dplyr, readr, stringr, and tidyr R packages.

Overview:
This R script takes a list of gene names and attempts to identify known synonyms as well as mouse/human orthologues. The script utilizes two synonym sources (MRK_List1.rpt; from Jax.org and human+mouse synonym.txt; based on Ensambl BioMart) and uses HMD_HumanPhenotype.rpt (from Jax.org) for mapping orthologues. This is useful when working with data that might have outdated or alternate gene symbols.

How to use:
The script processes four input files:
- A plain text file listing gene names (one per line) for which you want to find synonyms and orthologues. Save this file in a dedicated folder.
- MRK_List1.rpt  
  A tab-delimited file that contains gene synonyms from Jax.org. The script uses this to identify current marker symbols for genes. Download from https://www.informatics.jax.org/downloads/reports/index.html and unzip into the dedicated folder.
- HMD_HumanPhenotype.rpt  
  A tab-delimited file that maps mouse genes to their human counterparts. Download from https://www.informatics.jax.org/downloads/reports/index.html and place in the dedicated folder.
- human+mouse synonym.txt  
  A text file containing additional synonyms for both mouse and human genes generated from Ensambl BioMart, the file could be downloaded via https://github.com/EsbjornHenkel/Green-Listed-V2/blob/main/libraries/human%2Bmouse%20synonym.txt. Place this file in the same dedicated folder.

Output:
After processing, the script creates two CSV files in a new folder (named by the current date) within the same directory as your gene list file:
1. Detailed Mapping (detailed_gene_mapping.csv)  
   Lists each original gene along with its corresponding synonyms (from both MRK and human+mouse synonym sources) and mouse/human orthologues. It also includes columns showing the total number of unique suggestions and total orthologues found.
2. Condensed Mapping (condensed_gene_mapping.csv)  
   A two-column file where each row contains the original gene and one suggestion (either a synonym or an orthologue), with additional columns indicating the total number of suggestions and the total number of orthologues for that gene. This layout is convenient for copy-pasting or further analysis.

Version History
250210: Initial release 
250213: Updated script. Search for both mouse and human orthologues, inclusion of an additional synonym file, refined output file naming, and added total suggestion and orthologue counts.
