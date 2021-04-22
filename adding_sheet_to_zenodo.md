#  How to publish your biocuration spreadsheet on Zenodo

A biocuration spreadsheet in this situation is a table that came from curation y
End goal: Have your table published like:

- https://zenodo.org/record/4589519#.YIDHRnVKi00
- https://zenodo.org/record/4631221#.YIDHR3VKi00

## Pre-processing:

  - Clean up the dataset (as much as you like, it is your call) 
  - Don't be afraid to remove columns that are not relevant for other people 
  - On a text file, add a short explanation of what your dataset is about
  - Below the explantation, write a _dictionary_ ("__Columns__" session), mapping the names of the column headers to some explanation. This will end up on the description on Zenodo, and will be part of the description of your dataset on the plataform.  

For example:

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

## Uploading to Zenodo:
  - Download your table  in two formats: .xlsx and .tsv format. The .tsv format is more machine readable, while .xlsx (the Excel format) is more common among human beings.  
  - Go to https://zenodo.org/
  - Login or sign up
  - Click on Upload (on the top) 
  - Click on new upload
  - Add both files (.tsv and .xlsx) that were downloaded previously.
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

tl;dr: Send tiago.lubiana.alves at usp.br and email, and he (I) will make that / help you with the process. 

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

* Upload the new files (a "wikidata_reconciled" sheet and the .xlsx). ("Choose Files" + "Start Upload")
* Add the new column details the Zenodo description.  
* Add the link to the Google Sheet: https://docs.google.com/spreadsheets/d/1LjF4h8n6Sy4PgTJoC-fJ7mGnqGCvqmWiatf2zD-5RM8. 
* Bump the file version to 1.1 

- Click "Save"
- Click "Publish"

### Adding information to Wikidata

Now we have a set of diseases and the articles that talk about them. 
We can add that directly to the Wikidata database using a property called "main subject", which is basically a way to say "keyword" in the Wikidata universe. 

For that, we will use a syntax called "Quickstatements V1". 
On a spreadsheet, we use the columns to build a series of "statements" like:

Q35073924	P921	Q12156	S854	"https://zenodo.org/record/4573573#.YEaYGnVKi00"
																					
Which means that this specific article (Q35073924) is about (P921) malaria (Q12156) as said in the url (S854) "https://zenodo.org/record/4573573#.YEaYGnVKi00".

On a new sheet, we add a column of "P921" between articles and diseases and the 2 reference columns in the end. 

These "statements" are pasted into the Quickstatements system (<https://quickstatements.toolforge.org/#/batch>) which is a way to make batch edits to Wikidata. 

(To use the system, you need 100 manual edits in the system. One way of achieving that is adding aliases on Wikidata for a few terms here and there). 

On Quickstatements:

* Log in with your Wikidata account
* Click on New Batch
* Paste your series of commands in the format above
* Click on "Import V1 commands"
* Check if everything looks at expected (the system will render human-readable statements for you to check)
* If it looks ok, click on "Run" 

Nice, now your curation is live on Wikidata!

Everyone can benefit from it, including you. 

To showcase the power, I will reconcile the column with the Gene Expression Omnibus IDs to Wikidata. 
For that, I'll use the "external data" (P1325) property. The triples go like this:

Q35073924	P1325	"https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE5418"	S854	"https://zenodo.org/record/4589519"

Which reads like this specific article (Q35073924) has external data (P1325) at the url "https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE5418" as said in the url (S854) "https://zenodo.org/record/4589519".

I follow once more the steps on Quickstatements to add to Wikidata. 

### Using the power of Wikidata for your curation

Now we can use the Wikidata query system and the ontological structure to make very useful queries. 

For example, let's look for articles about any neurodegenerative disease and their external datasets. 

For that, we build a query in the SPARQL language at <query.wikidata.org>, which can be acessed here: https://w.wiki/34rP. 

As of March 8 2021, Wikidata has 18 matches for that query, some of which came from my curation, and some that were already there. 

SPARQL queries are very flexible, and allow us to navigate this sea of knowledge. 

In this simple example, it already helped me to discover new datasets. 

Now imagine that all mini tables, like the ones you already have, were represented on Wikidata? 

That could have a transformative change in the daily life of _all_ researchers, streamlining biocuration and saving millions of person/hours per year. 
  













