README_gene_mapping_script_v2
Fredrik Wermeling, PhD

The script was developed and successfully executed using RStudio version 2024.12.0 Build 467, and R version 4.4.1, using the dplyr, readr, stringt, and tidyr R packages.

Overview:
This R script takes a list of gene names and attempts to identify known synonyms and mouse/human orthologues. This can be useful when working with data that might have outdated or alternate gene symbols.

How to use:
The script processes three input files:
- A plain text file listing gene names (one per line) of the genes you want to find synonyms and orthologues for. Save in a dedicated folder. 
- MRK_List1.rpt
  A tab-delimited file that contains gene synonyms. The script uses this to identify current marker symbols for genes. Download from https://www.informatics.jax.org/downloads/reports/index.html and unzip into the dedicated folder. 	
- HMD_HumanPhenotype.rpt
  A tab-delimited file that maps mouse genes to their human counterparts. Download from https://www.informatics.jax.org/downloads/reports/index.html and place in the dedicated folder. 	
  
Output:
After processing, the script creates two CSV files in a new folder (named by the current date):
1. Detailed Mapping (`detailed_gene_mapping.csv`)  
   Lists each original gene along with its corresponding synonyms and human orthologues.
2. Simplified Mapping (`two_column_gene_mapping.csv`)
   A two-column file where each row contains the original gene and one suggestion (either a synonym or an orthologue). This layout is convenient for copy-pasting or further analysis.

Version History
250210: Initial release 
250211: Updated script. Search for both mouse and human orthologues. Better saving of output file.  

