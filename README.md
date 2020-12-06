# Explainable Fact Checking: A Survey

[![arXiv](https://img.shields.io/badge/arXiv-2011.03870-green.svg)](https://arxiv.org/abs/2011.03870)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/neemakot/Fact-Checking-Survey)
[![Contribution_welcome](https://img.shields.io/badge/Contributions-welcome-blue)](https://github.com/neemakot/Fact-Checking-Survey/blob/main/CONTRIBUTING.md)


This repository and the accompanying [webpage](https://neemakot.github.io/project/survey) contain resources for the paper ["Explainable Fact Checking: A Survey"](https://www.aclweb.org/anthology/2020.coling-main.474.pdf). In the paper, we offer a critical review of the state-of-the-art in automated fact-checking with a particular focus on interpretability. 


## Reference

If you find our work useful, please cite the paper as formatted below. 

```bibtex
  @inproceedings{kotonya-toni-2020-explainable-automated,
    title = "Explainable Automated Fact-Checking: A Survey",
    author = "Kotonya, Neema  and
      Toni, Francesca",
    booktitle = "Proceedings of the 28th International Conference on Computational Linguistics",
    month = dec,
    year = "2020",
    address = "Barcelona, Spain (Online)",
    publisher = "International Committee on Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2020.coling-main.474",
    pages = "5430--5443"
  }
```


## Contents

Here is an overview of papers mentioned in this work, and more recent papers which have been added.

- [Introduction](#introduction)
- [Datasets](#fact-checking-datasets)
  - [Naturally occuring](#naturally-occurring)
    - [Social media](#social-media)
    - [Fact-checking and news websites](#fact-checking-and-news-websites)
  - [Hand crafted](#hand-crafted)
    - [Wikipedia](#wikipedia)
    - [Scientific journals](#scientific-journals)
- [Shared Tasks](#shared-tasks)
- [Explainable Fact Checking](#explainable-fact-checking)
  - [Systems](#systems)
    - [Attention mechanisms](#attention-mechanism)
    - [Rule discovery](#rule-discovery)
    - [Summarization](#summarization)
  - [Adversarial Training for Fact Checking](#adversarial-training-for-automated-fact-checking)
  - [Multi-hop Fact Checking](#multihop-reasoning-for-facting-checking)
  - [Fact Checking with Intrepretable Features](#fact-checking-with-interpretable-features)
- [Surveys](#further-fact-checking-surveys)
- [Tutorials](#tutorials)



## Introduction

Fact checking is the process of establishing the veracity of claims i.e., to distinguish between false stories (e.g., misattributions, rumours, hoaxes) and facts. 

Over the past few years the use of deep learning methods for fact checking and fake news detection have become a popular. Indeed, several exciting breakthroughs have occured in automated fact checking thanks in large part due to new datasets (e.g., [FEVER](https://fever.ai/)) and advances in machine learning for NLP. However there are still some limitations in this research area, the one we focus on in this work in our work is __explanations__ for automated fact checking. 

The pipeline commonly employed for automated fact-checking consists of four parts (subtasks). We propose that post-hoc explanations are an important and necessary extension of this pipeline.

![fact-checking-pipeline](images/pipeline.svg)


For an overview of the data and results mentioned in our survey, please visit [this webpage](https://neemakot.github.io/project/survey).


## Fact Checking Datasets

List of fact checking, rumour verification and fake news detection datasets:

### Naturally occurring
  
#### Social media

Claims from social media sources e.g., Twitter, Facebook.

* r/Fakeddit: A New Multimodal Benchmark Dataset for Fine-grained Fake News Detection (Nakamura et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.lrec-1.755.pdf)]
[[data](https://github.com/entitize/fakeddit)]
[[bib](https://www.aclweb.org/anthology/2020.lrec-1.755.bib)]
* SemEval-2019 Task 7: RumourEval, Determining Rumour Veracity and Support for Rumours (Gorrell et al., 2019).
[[paper](https://www.aclweb.org/anthology/S19-2147.pdf)]
[[data](https://competitions.codalab.org/competitions/19938)]
[[bib](https://www.aclweb.org/anthology/S19-2147.bib)]
* All-in-one: Multi-task Learning for Rumour Verification (Kochkina et al., 2018). 
[[paper](https://www.aclweb.org/anthology/C18-1288.pdf)]
[[data](https://figshare.com/articles/PHEME_dataset_for_Rumour_Detection_and_Veracity_Classification/6392078)]†
[[bib](https://www.aclweb.org/anthology/C18-1288.bib)]
* SemEval-2017 Task 8: RumourEval: Determining rumour veracity and support for rumours (Derczynski et al., 2017).
[[paper](https://www.aclweb.org/anthology/S17-2006.pdf)]
[[data](https://alt.qcri.org/semeval2017/task8/index.php?id=data-and-tools)]
[[bib](https://www.aclweb.org/anthology/S17-2006.bib)]
* Hyperpartisan Facebook Pages Are Publishing False And Misleading Information At An Alarming Rate (Silverman et al., 2017).
[[article](https://www.buzzfeednews.com/article/craigsilverman/partisan-fb-pages-analysis)]
[[data](https://github.com/BuzzFeedNews/2016-10-facebook-fact-check)]
* Detect Rumors in Microblog Posts Using Propagation Structure via Kernel Learning (Ma et al., 2017).
[[paper](https://www.aclweb.org/anthology/P17-1066.pdf)]
[[data](https://www.dropbox.com/s/7ewzdrbelpmrnxu/rumdetect2017.zip?dl=0)]
[[bib](https://www.aclweb.org/anthology/P17-1066.bib)]
* Analysing How People Orient to and Spread Rumours in Social Media by Looking at Conversational Threads (Zubiaga et al., 2016).
[[paper](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0150989)]
[[data](https://figshare.com/articles/PHEME_rumour_scheme_dataset_journalism_use_case/2068650)]
[[bib](https://journals.plos.org/plosone/article/citation?id=10.1371/journal.pone.0150989)]
* CREDBANK: A Large-Scale Social Media Corpus with Associated Credibility Annotations (Mitra and Gilbert, 2015).
[[paper](http://eegilbert.org/papers/icwsm15.credbank.mitra.pdf)]
[[data](https://github.com/compsocial/CREDBANK-data)]
[[bib](https://dblp.org/rec/conf/icwsm/MitraG15.html?view=bibtex)]

† This dataset is an extention of the PHEME rumour dataset.

#### Fact checking and news websites

E.g., Snopes, Politifact
  
* Explainable Automated Fact-Checking for Public Health Claims (Kotonya and Toni, 2020). 
[[paper](https://arxiv.org/abs/2010.09926)]
[[data](https://github.com/neemakot/Health-Fact-Checking)]
[[bib](https://www.aclweb.org/anthology/2020.emnlp-main.623.bib)]
* STANDER: An Expert-Annotated Dataset for News Stance Detection and Evidence Retrieval (Conforti et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.findings-emnlp.365.pdf)]
[[data](https://github.com/cambridge-wtwt/emnlp2020-stander-news)]
[[bib](https://www.aclweb.org/anthology/2020.findings-emnlp.365.bib)]
* FakeCovid-- A Multilingual Cross-domain Fact Check News Dataset for COVID-19 (Shahi and Nandini, 2020). 
[[paper](https://arxiv.org/pdf/2006.11343.pdf)]
[[data](https://gautamshahi.github.io/FakeCovid/)]
[[bib](https://ui.adsabs.harvard.edu/abs/2020arXiv200611343K/exportcitation)]
* MultiFC: A Real-World Multi-Domain Dataset for Evidence-Based Fact Checking of Claims (Augenstein et al., 2019).
[[paper](https://www.aclweb.org/anthology/D19-1475.pdf)]
[[bib](https://www.aclweb.org/anthology/D19-1475.bib)]
[[data](https://competitions.codalab.org/competitions/21163)]  
* A Richly Annotated Corpus for Different Tasks in Automated Fact-Checking (Hanselowski et al., 2019).
[[paper](https://www.aclweb.org/anthology/K19-1046.pdf)]
[[code](https://github.com/UKPLab/conll2019-snopes-crawling)]
[[data](https://tudatalib.ulb.tu-darmstadt.de/handle/tudatalib/2081)]
[[bib](https://www.aclweb.org/anthology/K19-1046.bib)]
* Integrating Stance Detection and Fact Checking in a Unified Corpus (Baly et al., 2018).
[[paper](https://www.aclweb.org/anthology/N18-2004.pdf)]
[[data]](https://alt.qcri.org/resources/arabic-fact-checking-and-stance-detection-corpus/)]
[[bib](https://www.aclweb.org/anthology/N18-2004.bib)]
* FakeNewsNet: A Data Repository with News Content, Social Context and Spatialtemporal Information for Studying Fake News on Social Media (Shu et al., 2018).
[[paper](https://arxiv.org/pdf/1809.01286.pdf)]
[[data](https://github.com/KaiDMML/FakeNewsNet)]
* “Liar, Liar Pants on Fire”: A New Benchmark Dataset for Fake News Detection (Wang, 2017).
[[paper](https://www.aclweb.org/anthology/P17-2067.pdf)]
[[data](https://sites.cs.ucsb.edu/~william/software.html)]
[[bib](https://www.aclweb.org/anthology/P17-2067.bib)]
* Truth of Varying Shades: Analyzing Language in Fake News and Political Fact-Checking (Rashkin et al., 2017).
[[paper](https://www.aclweb.org/anthology/D17-1317.pdf)]
[[data](https://hrashkin.github.io/factcheck.html)]
[[bib](https://www.aclweb.org/anthology/D17-1317.bib)]
* The Fake News Challenge (Pomerleau and Rao, 2017) 
[[data](https://github.com/FakeNewsChallenge/fnc-1)]


### Hand crafted

This covers claims which are generated manually e.g. through re-writing statements.

#### Wikipedia
* TabFact: A Large-scale Dataset for Table-based Fact Verification (Chen et al., 2020). 
[[paper](https://openreview.net/pdf?id=rkeJRhNYDH)]
[[data](https://github.com/wenhuchen/Table-Fact-Checking)]
[[bib](https://dblp.org/rec/conf/iclr/ChenWCZWLZW20.html?view=bibtex)]
* FEVER: a Large-scale Dataset for Fact Extraction and VERification (Thorne et al., 2018).
[[paper](https://www.aclweb.org/anthology/N18-1074.pdf)] 
[[data](https://fever.ai/resources.html)] 
[[bib](https://www.aclweb.org/anthology/N18-1074.bib)] 
* Automated Fact-Checking of Claims from Wikipedia (Sathe et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.lrec-1.849.pdf)] 
[[data](https://github.com/wikifactcheck-english/wikifactcheck-english)]
[[bib](https://www.aclweb.org/anthology/2020.lrec-1.849.bib)]
* Generating Fact Checking Briefs (Fan et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.emnlp-main.580.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.emnlp-main.580.bib)]
#### Scientific journals
* Fact or Fiction: Verifying Scientific Claims (Wadden et al., EMNLP 2020).
[[paper](https://www.aclweb.org/anthology/2020.emnlp-main.609.pdf)]
[[data](https://github.com/allenai/scifact)]
[[bib](https://www.aclweb.org/anthology/2020.emnlp-main.609.bib )]


## Shared Tasks

* SciFact Claim Verifiation [[Wadden et al., 2020](https://scifact.apps.allenai.org/)]
* Fakeddit Multimodal Fake News Detection Challenge [[Nakamura et al., 2020](https://competitions.codalab.org/competitions/25337#learn_the_details)]
* SemEval-2019 Task 7: RumourEval, Determining Rumour Veracity and Support for Rumours [[Gorrell et al., 2019](https://www.aclweb.org/anthology/S19-2147/)]
* SemEval-2019 Task 8: Fact Checking in Community Question Answering Forums [[Mihaylova et al., 2019](https://www.aclweb.org/anthology/S19-2149/)]
* The Fake News Challenge (FNC-1) [[Pomerleau and Rao, 2017](http://www.fakenewschallenge.org/)]
  * A Retrospective Analysis of the Fake News Challenge Stance-Detection Task [[Hanselowski et al., 2018](https://www.aclweb.org/anthology/C18-1158/)]
* The Fact Extraction and VERification (FEVER) Shared Task [[Thorne et al., 2018](https://www.aclweb.org/anthology/W18-5501/)]
* SemEval-2017 Task 8: RumourEval: Determining rumour veracity and support for rumours [[Derczynski et al., 2017](https://www.aclweb.org/anthology/S17-2006/)]


## Explainable Fact Checking

### Systems

A list of works on explainability in fact-checking and fake news detection:

#### Attention mechanism

* dEFEND: Explainable Fake News Detection (Shu et al., 2019). 
[[paper](http://pike.psu.edu/publications/kdd19.pdf)]
[[bib](https://dblp.org/rec/conf/kdd/ShuCW0L19.html?view=bibtex)]
[[video](https://www.youtube.com/watch?v=7kfpGL8Ts2M&ab_channel=KDD2019)]
* GCAN: Graph-aware Co-Attention Networks for Explainable Fake News Detection on Social Media (Lu and Li, 2020).
[[paper](https://www.aclweb.org/anthology/2020.acl-main.48.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.acl-main.48.bib)]
* DTCA: Decision Tree-based Co-Attention Networks for Explainable Claim Verification (Wu et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.acl-main.97.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.acl-main.97.bib)]
* DeClarE: Debunking Fake News and False Claims using Evidence-Aware Deep Learning (Popat et al., 2018).
[[paper](https://www.aclweb.org/anthology/D18-1003.pdf)]
[[bib](https://www.aclweb.org/anthology/D18-1003.bib)]
* CredEye: A Credibility Lens for Analyzing and Explaining Misinformation (Popat et al., 2018).
[[paper](https://people.mpi-inf.mpg.de/~kpopat/publications/www18_demo.pdf)]
[[bib](https://dblp.org/rec/conf/www/PopatMSW18.html?view=bibtex)]
[[demo](https://gate.d5.mpi-inf.mpg.de/credeye/)]
* XFake: Explainable Fake News Detector with Visualizations (Yang et al., 2019).
[[paper](https://arxiv.org/pdf/1907.07757.pdf)]
[[bib](https://dblp.uni-trier.de/rec/conf/www/YangPMDYLRJH19.html?view=bibtex)]
* Credibility Assessment of Textual Claims on the Web (Popat et al., 2017).
[[paper](http://resources.mpi-inf.mpg.de/impact/web_credibility_analysis/cikm2016-popat.pdf)]
[[bib](https://dblp.org/rec/conf/cikm/PopatMSW16.html?view=bibtex)]

#### Rule discovery
* ExFaKT: A Framework for Explaining Facts over Knowledge Graphs and Text (Gad-Elrab et al., 2019).
[[paper](https://people.mpi-inf.mpg.de/~gadelrab/downloads/WSDM2019/ExFaKT_preprint.pdf)]
[[bib](https://dblp.org/rec/conf/wsdm/Gad-Elrab0UW19.html?view=bibtex)]
* Explainable Fact Checking with Probabilistic Answer Set Programming (Ahmadi et al., 2019).
[[paper](https://truthandtrustonline.files.wordpress.com/2019/09/paper_15.pdf)]
[[bib](https://dblp.org/rec/conf/tto/AhmadiLPS19.html?view=bibtex)] 


#### Summarization
* e-FEVER: Explanations and Summaries for Automated Fact Checking (Stammbach and Ash, 2020).
[[paper](https://truthandtrustonline.com/wp-content/uploads/2020/10/TTO04.pdf)]
[[bib](https://dblp.org/rec/conf/tto/StammbachA20.html?view=bibtex)]
* Generating Fact Checking Explanations (Atanasova et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.acl-main.656.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.acl-main.656.bib)]
* Explainable Automated Fact Checking for Public Health Claims (Kotonya and Toni, 2020).
[[paper](https://arxiv.org/pdf/2010.09926.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.emnlp-main.623.bib)]



### Adversarial Training for Automated Fact Checking

List of papers which look at adversarial training for robust fact-checking:

* Generating Label Cohesive and Well-Formed Adversarial Claims (Atanasova et al.,2020).
[[paper](https://www.aclweb.org/anthology/2020.emnlp-main.256.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.emnlp-main.256.bib)]
[[code](https://github.com/copenlu/fever-adversarial-attacks)]
* Evaluating adversarial attacks against multiple fact verification systems (Thorne et al., 2019).
[[paper](https://www.aclweb.org/anthology/D19-1292.pdf)]
[[bib](https://www.aclweb.org/anthology/D19-1292.bib)]
[[video](https://vimeo.com/411299595)]
* DeSePtion: Dual Sequence Prediction and Adversarial Examples for Improved Fact-Checking (Hidey et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.acl-main.761.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.acl-main.761.bib)]
* Fake news detection via NLP is vulnerable to adversarial attacks (Zhou et al., 2019).
[[paper](https://arxiv.org/pdf/1901.09657.pdf)]
[[bib](https://dblp.org/rec/conf/icaart/ZhouGBH19.html?view=bibtex)]
* GEM: Generative enhanced model for adversarial attacks (Niewinski et al., 2019).
[[paper](https://www.aclweb.org/anthology/D19-6604.pdf)]
[[bib](https://www.aclweb.org/anthology/D19-6604.bib)]
* FEVER Breaker’s Run of Team NbAuzDrLqg (Kim and Allan, 2019).
[[paper](https://www.aclweb.org/anthology/D19-6615.pdf)]
[[bib](https://www.aclweb.org/anthology/D19-6615.bib)]

### Multihop Reasoning for Facting Checking

Multi-hop reasoning is closely important for explainability in fact-checking, recently there have been a number of papers which look to address this task:

* HoVer: A Dataset for Many-Hop Fact Extraction And Claim Verification (Jiang et al., 2020). 
[[paper](https://www.aclweb.org/anthology/2020.findings-emnlp.309.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.findings-emnlp.309.bib)]
[[project](https://hover-nlp.github.io/)]
* Multi-Hop Fact Checking of Political Claims (Ostrowski et al., 2020).
[[paper](https://arxiv.org/pdf/2009.06401.pdf)]
[[bib](https://dblp.org/rec/journals/corr/abs-2009-06401.html?view=bibtex)]
[[code](https://github.com/copenlu/politihop)]
* Chains-of-Reasoning at TextGraphs 2019 Shared Task: Reasoning over Chains of Facts for Explainable Multi-hop Inference (Das et al., 2019).
[[paper](https://www.aclweb.org/anthology/D19-5313.pdf)]
[[bib](https://www.aclweb.org/anthology/D19-5313.bib)]

### Fact Checking with Intrepretable Features

* A Language-Based Approach to Fake News Detection Through Interpretable Features and BRNN (Qiao et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.rdsm-1.2.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.rdsm-1.2.bib)]

## Surveys

Automated fact checking and fake news detection surveys:

* A Survey of Fake News: Fundamental Theories, Detection Methods, and Opportunities [[Zhou and Zafarani, ACM Computing Surveys 2020](https://dl.acm.org/doi/10.1145/3395046)].
* A Review on Fact Extraction and VERification: The FEVER case [[Bekoulis et al., 2020](https://arxiv.org/abs/2010.03001)].
* A Survey on Natural Language Processing for Fake News Detection [[Oshikawa et al., LREC 2020](https://arxiv.org/abs/1811.00770)].
* Automated Fact Checking: Task Formulations, Methods and Future Directions [[Thorne and Vlachos, COLING'18](https://www.aclweb.org/anthology/C18-1283/)].
* Media-Rich Fake News Detection: A Survey [[Parikh and Atrey MIPR '18](https://ieeexplore.ieee.org/abstract/document/8397049)]
* Fake News Detection on Social Media: A Data Mining Perspective [[Shu et al., ACM SIGKDD Explorations Newsletter Sep 2017](https://dl.acm.org/doi/abs/10.1145/3137597.3137600)].
* Detection and resolution of rumours in social media: A survey [[Zubiaga et al., 2018](https://dl.acm.org/doi/10.1145/3161603)].

## Tutorials
* Fact Checking: Theory and Practice [[Dong et al., KDD 2018](https://shiralkarprashant.github.io/fact-checking-tutorial-KDD2018/)].
* Detection and Resolution of Rumors and Misinformation with NLP [[Derczynski and Zubiaga, COLING 2020](https://www.aclweb.org/anthology/2020.coling-tutorials.4.pdf)].

## Contact 

Please feel free to contact [Neema Kotonya](mailto:nk2418@ic.ac.uk) if you have any questions or comments.

