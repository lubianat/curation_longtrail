# Pilot


Dataset: Studies on GEO related to neurogeneration or infections diseases.

Google Sheets: https://docs.google.com/spreadsheets/d/1LjF4h8n6Sy4PgTJoC-fJ7mGnqGCvqmWiatf2zD-5RM8/edit#gid=0

__Description__:

A set of transcriptomics studies on the Gene Expression Omnibus (GEO) platform somehow related to infectious or neurodegenerative diseases.

__Columns__:

  - __Study__: The study number in the Gene Expression Omnibus. End {$1} of the URL: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc={$1}.
  - __Disease__: The disease of interest in the study
  - __Platform__: The technology used to obtain the data. End {$1} of the URL: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc={$1}.
  - __Sample type__: The cell type or tissue type used for the analysis
  - __PMID__: The PubMed ID of the article that describes that study. End {$1} of the URL: https://pubmed.ncbi.nlm.nih.gov/{$1}.
  - __Control sample__: The label of the control samples in the dataset
  - __Perturbed sample__: The label of the perturbed samples in the dataset

__Funding__: 

This curation and release were supported by the grants #2018/10257-2 and  #2019/26284-1 from the São Paulo Research Foundation (FAPESP).


Pre-processing:

  - Standardize capitalization and punctuation where possible (not crucial). 
  - Table was _not_ reviewed again (as this would not be done in practice anyways) 
  - Original sheet named "original"
  - Download in .xlsx format
  - Download in .tsv format

Uploading to Zenodo:
  - New upload
  - Add both files (.tsv and .xlsx) that were downloaded in the previous step.
  - Click on the green button "Start upload"
  - Skip the "Community" section
  - Select upload type "dataset"
  - Add the basic information (no DOI, one will be assigned to your table):
      - A title
      - Your credentials (and of the other people that worked in the dataset)
      - The description of the dataset (alongside the description of each column!)

  - Add a version tag (you might want to update it in the future!). One option is set the first version be 1.0, and update with time.  
 Bump it to 1.1 if adding new tables (we will do that shortly!).
 Bump it to 2.0 if making a change that would break previous uses of the dataset (e.g. if you change the name of a column).
 
  - Add the primary language used on your table. It does not need  to be English!
  - Add a couple keywords. And the keyword "biocuration" so people know what type of dataset is there. 
  - Add a license. Release it in open access for maximal reuse of your curation.  The default "CC-BY" license is good enough for most purposes 
  (people can reuse, but they have to cite you).
  
  - Click "Save"
  - Click "Publish"


Done! Now the dataset is openly available and:

- Got a DOI: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4573573.svg)](https://doi.org/10.5281/zenodo.4573573)
- Can be shared: https://zenodo.org/record/4573573#.YD5TG3VKi00
- Can be cited (it has a DOI!) 
- Will soon be indexed and visible to Google Dataset Search. 


Next step: Add info to Wikidata! 









