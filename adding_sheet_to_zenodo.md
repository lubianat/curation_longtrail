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

## Reconciling to Wikidata

Now the dataset is super searchable, what is great. 
However, we can extract even more value from the curation effort. 

We often represent concepts (such as diseases, cell types and tissues) by _strings_, natural language, human-readable words.

Words are tricky, and can hold many meanings. 
Moreover, they are meaningful to people, but very shallow to computers. 

One modern advancement is the use of Universal Resource Identifiers to map concepts to unique resources. 

This technique is on the base of virtually all biomedical ontologies, like the Gene Ontology. 
Wikidata is an open, general-use knowledgebase where people can find (and create!) identifiers for their concepts of interest.

Wikidata is linked to thousands of other bases. 
Thus, linking to Wikidata effectively raises the information to state-of-the-art information sharing, or what Tim Berner-Lee (the inventor of the web) would call 5- star linked ofen data. 

First we need to choose which columns to reconcile to Wikidata. 

In our example we have concepts findable on Wikidata, like: 

  - __Disease__: The disease of interest in the study
  - __PMID__: The PubMed ID of the article that describes that study. End {$1} of the URL: https://pubmed.ncbi.nlm.nih.gov/{$1}.

First we will:

- Find/Create Wikidata identifiers for each of the concepts on the table
- Add them to the Wikidata database citing the Zenodo dataset. 

### Finding the Wikidata identifiers

Using the Google Sheets Add-On Wikipedia and Wikidata, I do the following:

* Copy all disease terms to the first column
* In the second column, use the formula `=WIKIDATASEARCH(A1)` to get the Wikidata ID by searching that word on Wikidata. Extend it to all rows.
* In the third column, use the formula `=WIKIDATADESCRIPTIONS(A1)` to verify if the description is accurate. Extend it to all rows. 

In this case, the row "c9orf72-associated and sporadic ALS" did not have a match on Wikidata. I simplify it, then, to "ALS".

The tool found IDs for all diseases.

Now I want to find the Wikidata identifiers for all articles on that table.

The Google Sheets Add On does not work with PMIDs, so I'll need to use programatic tools. 
There is a shiny app available to do exactly that reconciliation at https://lubianat.shinyapps.io/doi2wiki/. 
It might not be up in the future, but the code for the Shiny App will always (I hope!) be at https://github.com/lubianat/doi2wiki.

I download the "csv" via the Google Sheets and feed it to the doi2wiki app. 
The app returns a tsv with the original table plus the Wikidata IDs found. 

### Updating file version on Zenodo

Our curation table is now enriched with Wikidata ids. 
Let's add "(with Wikidata)" to the title and a note to the descriptio saying:

Column names followed by __"_QID"___ hold the Wikidata IDs relative to that column. 

On Zenodo, I click on "Upload" and on the dataset we uploaded in the previous session. Then, on "New Version" I can add the new tables.
I won't change the ones that are already there. What I do, then is :

* Upload the new files (a "wikidata_reconciled" sheet and the .xlsx). 
* Add the new column details the Zenodo description.  
* Add the link to the Google Sheet: https://docs.google.com/spreadsheets/d/1LjF4h8n6Sy4PgTJoC-fJ7mGnqGCvqmWiatf2zD-5RM8. 
* Bump the file version to 1.1 

### Adding information to Wikidata

Now we have a set of diseases and the articles that talk about them. 
We can add that to Wikidata using a property called "main subject", which is basically a way to say "keyword" in the Wikidata universe. 











