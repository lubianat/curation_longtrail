---
bibliography: references.bib
---

# The situation

When starting a new line of work, researchers face searching for sources of information to become familiar with the relevant knowledge. Online search has fundamentally taken the place of book digging on libraries. The curation of the literature, once including physical cards and folders [\@wikidata:Q59134700] is carried today in various organizational ways, which are peculiar for every researcher. While this is somewhat true for all research projects, it is made explicitly for narrative and systematic reviews.

Even though each person has their organizational quirks, a common feature of many curation processes is the generation of intermediate products containing organized, tabulated information. From basic topic-tagging to the extraction of various types of information, these intermediate products provide the basis for the research process: they influence the mental models, serve as raw material for planning experiments, and are indispensable when writing introductions and discussions. In systematic reviews, this is an unavoidable step - the data in these tables are used when articles are considered for inclusion. It is often the case that information is collected for many articles, even if only a tiny fraction of the studies end up being included. However, these data, produced after many hours of focused, specialized work, are almost always relegated to forgotten folders.

These intermediate tables are a rich source of organized information about the published literature. They are the distilled product of several days of highly-specialized work. Moreover, they are already organized (the scientists involved needed to organize it for their projects!), which means they could easily be made available to the community.

Most scientists are already producing these small datasets - most of which, currently, are not made public. When pooled together, this might amount to enormous quantities of high-quality data curated by people with the relevant local-expertise [\@wikidata:Q24790499] [@ferguson2014]. Massive biocuration projects, such as UniProt and Gene Ontology, are core tools of modern life sciences and cover a fraction of any researcher's topics of interest.

We advocate for sharing small (or not so small) curated datasets made by every researcher. We argue that this would benefit both the researchers' careers and, collectively, provide a new core knowledge resource for life scientists.

First of all, your work has value: other researchers will love to see your curation, even if it is not perfect. It could save them many hours of work. Searching and harmonizing many small datasets that are relevant to your research is no small feat. For instance, in comparative neuroanatomy, a researcher has published a [tutorial] ([\<https://dieterlukas.github.io/data.html\>](https://dieterlukas.github.io/data.html){.uri}) enumerating the multiple steps one might have to follow to find and gather datasets.

Second, your work will be findable by anyone who wants to work with the data. For instance, Google Datasets makes it very easy to find the work (see Box). Others will find it, and you will find it. It makes science a more communal and shared endeavor, it helps bring in scientists who otherwise could not participate [@nagaraj2020]. Also, most likely, it is you (or someone in your research group) that will be the one who will try to use the dataset again in the future. Say, in 5 years time, when you need it, you will be able to find your curated dataset on Google, instead of spending hours sifting through old e-mails, Google Drive, Dropbox, or even hard drives. You are your most likely future collaborator.

You will also be rewarded in other ways. A table in Zenodo with a DOI is citable, which means you get recognition for your valuable work. Empirical research also suggests that publications whose datasets are open are cited more often [@colavizza2020]. Also, openness is increasingly recognized as an essential aspect of scientific work that should be recognized and rewarded [@moher2018]. Publishers and funders recognize the importance of open data and are moving in that direction with their policies [@cousijn2018].

Lastly, if you connect your data to Wikidata, the community benefits from an integrated knowledge graph. For instance, it enables powerful queries via the SPARQL query system. It enables the use of the Scholia platform to visualize the topics you have curated. It makes it visible for everyone to improve academic search engines. Although Wikidata is not yet in widespread use for academic purposes [@mora-cantallops2019], it has a lot of potential for research - especially for biocuration and organized reviews [@waagmeester2020].

Thousands of systematic reviews are published each year [@møller2018], and a large part, if not most, of the curation performed in the course of these reviews remains invisible, unusable, and unrecognized. Systematic reviews could be designed from the start to have their curated datasets in a format that makes it easy to share them later. We argued that this is an excellent opportunity for open science, where there is a lot to be gained from a small additional effort. .This large amount of hidden small curated datasets, if combined and distributed, could make a massive impact on the flow of scientific information in the life sciences.

# The proposed approach (box)

`Tentei colocar essa parte no frame do FAIR, mas não sei se usar DOIs tá em reusable ou interoperable. De qualquer forma, acho que isso aqui devia ser uma caixinha no artigo, sabe? Separado do texto principal, como um "passo a passo sugerido pra fazer isso com os seus datasets". Por isso eu trouxe essa seção pro final e adicionei uns trechos redundantes com o "Why", caso alguém resolva ler só a caixinha.`

1.  Our proposal tries to balance the cost of making these intermediate datasets available with the value for the researchers who performed the data curation and for the scientific community at large [@stieglitz2020]. Hence our focus on systematic reviews, where the data curation is already a necessary step. Because the structured dataset is a side effect of the research project, the only added step is making the dataset available.

2.  Make it public: Nowadays, there are many possibilities for making datasets available. We recommend Zenodo, which will make the dataset citable, with its own DOI. As we mentioned above, the curation of these datasets is specialized work; it is a contribution to the scientific community. Being citable makes it easy for this work to be recognized. Another benefit is that Zenodo datasets are automatically indexed by data-specific search engines, such as Google Datasets.

3.  Make it reusable: Describe datasets with enough information to facilitate reuse. If On a similar note, whenever possible, use unique identifiers (e.g., identify scientific articles by their DOI, instead of a full citation).

4.  Make it interoperable: an extra-step, if you feel comfortable with it, is to add the data to open knowledge repositories, such as Wikidata (wikidata.org), while referencing your publicly available table. This makes your dataset available in a standard format, integrated with data from many other sources.
