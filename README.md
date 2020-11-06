# Explainable Fact Checking: A Survey

This repository contains resources for the paper ["Explainable Fact Checking: A Survey" (Kotonya and Toni, 2020)](https://arxiv.org/abs/2011.****). This research will be presented at The 28th International Conference on Computational Linguistics (COLING 2020).

## Introduction

Fact checking is the process of verifying claims in order to establish their veracity i.e., to distinguish between false stories and facts. 

Over the past decade the use of machine learning methods for fact-checking and fake news detection has become a popular topic of study. Indeed, several exciting breakthroughs have occured in automated fact checking thanks to large datasets (e.g., FEVER) and advances in deep learning for NLP. However there are still some limitations in the research area, the one we focus on in this work in __explanations__ for automated fact checking. 

The pipeline commonly employed for automated fact-checking consists of four parts (subtasks): 

	(1) Detecting checkworthy claims (i.e., identifying claims for fact-checking)

	(2) Retrieving evidence documents relevant to the claim.

	(3) Selecting the more important snippets of evidence from these documents.

	(4) Predicting the entailment relation between these evidence snippets and the claim. 

We propose that post-hoc explanations are an important and necessary extension of this pipeline.

![alt-text](resources/pipeline.svg)

<!-- A number of exciting advances have been made in automated fact-checking thanks to increasingly larger datasets and more powerful systems, leading to improvements in the complexity of claims which can be accurately fact-checked. However, despite these advances, there are still desirable functionalities missing from the fact-checking pipeline. In this survey, we focus on the explanation functionality – that is fact-checking systems providing reasons for their predictions. We summarize existing methods for explaining the predictions of fact-checking systems and we explore trends in this topic. Further, we consider what makes for good explanations in this specific domain through a comparative analysis of existing fact-checking explanations against some desirable properties. Finally, we propose further research directions for generating fact-checking explanations, and describe how these may lead to improvements in the research area. -->



## Datasets for Fact-Checking and Fake News Detection

Here we present a comprehensive list of datasets for fact-checking and fake news detection organized by the source of the claims. 




## Methods



## Comparison




## Reference

If you use the dataset, please cite the paper as formatted below.

```
@inproceedings{kotonya2020survey,
  title = "Explainable Automated Fact-Checking: A Survey",
  author = "Kotonya, Neema  and Toni, Francesca",
  booktitle = "28th International Conference on Computational Linguistics (COLING 2020)",
  publisher = "Association for Computational Linguistics",
  address = "Online",
  month = dec,
  year = "2020"
}
```

## Contact

Please feel free to contact [Neema Kotonya](mailto:nk2418@ic.ac.uk) if you have any queries.