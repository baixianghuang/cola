# COLA: Chain-Of-Linguistics Authorship Prediction

## Overview
The repository contains all the code and datasets used in our CoLA paper. CoLA is an advanced technique for authorship analysis leveraging Large Language Models (LLMs). It mimics the analytical processes of linguists to extract and reason through stylometric and linguistic features, offering a novel approach in the field of digital forensics, cybersecurity, and content verification on web and social media platforms.

## Key Features
- **Innovative Authorship Analysis**: Utilizes LLMs to conduct linguist-like reasoning for authorship verification.
- **Zero-Shot Learning**: Excels in end-to-end prediction tasks without the need for transfer learning or domain-specific fine-tuning.
- **Cross-Domain Robustness**: Performs consistently across various genres and styles, overcoming traditional cross-domain challenges.
- **Interpretability**: Provides detailed insights into the decision-making process of LLMs, highlighting the linguistic features influencing their predictions.

## Datasets
CoLA has been evaluated on various datasets spanning different genres and styles. 

- Enron Email Dataset: Contains approximately half a million messages from senior Enron managers. It's valuable for studying corporate communication and criminal networks, characterized by lengthy texts and significant variation in text-per-author. [Data](https://www.kaggle.com/datasets/wcukierski/enron-email-dataset)

- IMDb62 Dataset: Consists of writings from 62 authors, with 1,283 texts per author. This dataset is useful for examining authorial style in a relatively controlled topical environment. [Data](https://umlt.infotech.monash.edu/?page_id=266)

- Blog Authorship Attribution Corpus: A collection of over 680,000 blog posts from more than 19,000 authors, sourced from blogger.com as of 2004. It provides a rich source of data for analyzing the impact of factors like age and gender on blogging habits, with an average of 35 posts per author and short texts averaging 79 tokens for the top five authors. [Data](https://www.kaggle.com/datasets/rtatman/blog-authorship-corpus)

- The Reddit dataset consists of 300 million posts from 1 million users, spanning from July 2015 to June 2016, and is sourced from the Pushshift Reddit corpus, focusing on users with 100 to 1000 posts to balance author history and minimize spam accounts ([Khan et al., 2021, NAACL](https://arxiv.org/pdf/2105.07263.pdf); [Baumgartner et al., 2020, AAAI](https://arxiv.org/pdf/2001.08435.pdf)).


All texts are in English, and the datasets cover a range of topics, with some like Reddit encompassing a particularly wide variety. In preprocessing, duplicates were removed, authors with less than two texts were excluded, and text language was verified using py3langid. A notable trend is that LLMs often predict different authors for any two given texts, likely due to their training on diverse datasets. This makes them adept at identifying stylistic differences rather than similarities. The variability within a single author's work, influenced by genre, topic, and audience, can be misinterpreted by LLMs as indicative of different authors. To address this, documents were sampled in a balanced manner—half from the same author and half from different authors. For each dataset, 200 pairs of texts were sampled, each pair consisting of two texts. The preprocessing code and the datasets are available on our GitHub repository for further research and exploration. The preprocessed and sampled data are stored in the `datasets` directory.

Please note that we do not have ownership of the data and therefore cannot provide a license or control its use. However, we kindly request that the data only be used for research purposes.
