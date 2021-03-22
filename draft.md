---
bibliography: references.bib
---

# The situation

1.  One of the first steps in every research project is to become familiar with the relevant literature. While in some level this is true for all research projects, it is made much more explicit for reviews, be they narrative or systematic ones.

2.  Often - if not always - this curation of the relavant literature generates intermediate products containing organized, tabulated information about the articles of interest. These intermediate tables will then be the basis for preparing experiments or discussing results in a review. In systematic reviews, in particular, the data in these tables are used when articles are considered for inclusion. It is likely that information is collected for a large number of articles even if only a small fraction of the studies end up being included.

3.  Most scientists are already producing these small datasets - most of which, currently, are not made public. When pooled together, this might amount to enormous quantities of high-quality data, curated by people with the relevant local-expertise [@ferguson2014].

# The opportunity

1.  These intermediate tables are a rich source of organized information about the published literature. They are the distilled product of several days of highly-specialized work.

2.  Moreover, they are already organized (the scientists involved needed to organize it for their own projects!), which means they could easily be made available to the community.

3.  Large biocuration databases, like UniProt [*add other examples*], are a core resource of current research. This large amount of hidden small curated datasets, if combined and distributed, could make a similarly huge impact in the flow of scientific information.

# The why

1.  Making this data public brings many advantages, both to the researchers who curate the datasets and to the scientific community.

2.  First of all, your work has value: other researchers will love to see your curation, even if it is not perfect. It could save them many hours of work. Searching and harmonizing many small datasets that are relevant to your research is no small feat. For instance, in comparative neuroanatomy, a researcher has published a [tutorial] ([<https://dieterlukas.github.io/data.html>](https://dieterlukas.github.io/data.html){.uri}) enumerating the multiple steps one might have to follow to find and gather datasets.

3.  Second, your work will be findable by anyone who wants to work with the data. For instance, Google Datasets makes it very easy to find the work (see Box). Others will find it, and you will find it. It makes science a more communal and shared endeavor, it helps bring in scientists who otherwise couldn't participate [@nagaraj2020]. Also, most likely, it is you (or someone in your research group) that will be the one who will try to use the dataset again in the future. Say, in 5 years time, when you need it, you will be able to find your curated dataset on Google, instead of spending hours sifting through old e-mails, Google Drive, Dropbox or even hard drives. You are your most likely future collaborator.

4.  You will also be rewarded in other ways. A table in Zenodo with a DOI is citable, which mean you get recognition for your valuable work. Empirical research also suggests that publications whose datasets are open are cited more often [@colavizza2020]. In addition, openness is increasingly being recognized as an essential aspect of scientific work, one that should be recognized and rewarded [@moher2018]. Publishers and funders are recognizing the importance of open data and moving in that direction with their policies [@cousijn2018].

5.  Another indirect advantage is that making it public improves the curation quality, thereby in a cascade improving the quality of your own work, because you know someone will be able to use it later.

    `Aqui eu fico pensando se não dá uma impressão ruim de Big Brother, se não vai inibir as pessoas porque elas não querem ser observadas o tempo inteiro. Talvez seja contra produtivo ressaltar isso, talvez as pessoas não queiram ser lembradas de que tem gente olhando.`

6.  Lastly, if you connect your data to Wikidata, the community gets the all the benefits of an integrated knowledge graph. For instance, it enables powerful queries via the SPARQL query system. It enables the use of the Scholia platform to visualize the topics you have curated. It makes it visible for everyone to improve academic search engines. Although Wikidata is not yet in widespread use for academic purposes [@mora-cantallops2019], it has a lot of potential for research - specially for systematic reviews [@waagmeester2020].

# Final thoughts

1.  Thousands of systematic reviews are published each year [@møller2018] and a large part, if not most, of the curation performed in the course of these reviews remains invisible, unusable and unrecognized. Systematic reviews could be designed from the start to have their curated datasets in a format that makes it easy to share it later. We argued that this is a great opportunity for open science, where there is a lot to be gained from a small additional effort.

# The proposed approach (box)

`Tentei colocar essa parte no frame do FAIR, mas não sei se usar DOIs tá em reusable ou interoperable. De qualquer forma, acho que isso aqui devia ser uma caixinha no artigo, sabe? Separado do texto principal, como um "passo a passo sugerido pra fazer isso com os seus datasets". Por isso eu trouxe essa seção pro final e adicionei uns trechos redundantes com o "Why", caso alguém resolva ler só a caixinha.`

1.  Our proposal tries to balance the cost of making these intermediate datasets available with the value for the researchers who performed the data curation and for the scientific community at large [@stieglitz2020]. Hence our focus on systematic reviews, where the data curation is already a necessary step. Because the structured dataset is a side effect of the research project, the only added step is making the dataset available.

2.  Make it public: Nowadays, there are many possibilities for making datasets available. We recommend Zenodo, which will make the dataset citable, with its own DOI. As we mentioned above, the curation of these datasets is specialized work, it is a contribution to the scientific community. Being citable makes it easy for this work to be recognized. Another benefit is that Zenodo datasets are automatically indexed by data-specific search engines, such as Google Datasets.

3.  Make it reusable: Describe datasets with enough information to facilitate reuse. If On a similar note, whenever possible, use unique identifiers (e.g. identify scientific articles by their DOI, instead of a full citation).

4.  Make it interoperable: an extra-step, if you feel comfortable with it, is to add the data to open knowledge repositories, such as Wikidata (wikidata.org), while referencing your publicly available table. This makes your dataset available in a standard format, integrated with data from many other sources.
