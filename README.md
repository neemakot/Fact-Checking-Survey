# Explainable Fact Checking: A Survey

[![arXiv](https://img.shields.io/badge/arXiv-2011.03870-green.svg)](https://arxiv.org/abs/2011.03870)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/neemakot/Fact-Checking-Survey)
[![Last Commit](https://img.shields.io/github/last-commit/neemakot/Fact-Checking-Survey.svg)](https://github.com/neemakot/Fact-Checking-Survey)
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
- [Task Formulations](#task-definitions)
- [Datasets](#fact-checking-datasets)
  - [Naturally occurring claims](#datasets-of-naturally-occurring-claims)
    - [From social media](#social-media)
    - [From fact-checking and news websites](#fact-checking-and-news-websites)
  - [Hand crafted claims](#hand-crafted)
    - [From Wikipedia](#wikipedia)
    - [From scientific journals](#scientific-journals)
- [Fact Checking Systems](#fact-checking-systems)
  - [By dataset](#systems-by-dataset)
    - [LIAR dataset](#liar)
    - [FEVER dataset](#fever)
    - [MultiFC dataset](#multifc)
  - [By method](#systems-by-method)
    - [Support Vector Machines (SVMs)](#support-vector-machines)
    - [Convolutional Neural Networks (CNNs)](#convolutional-neural-networks)
    - [Recurrent Neural Networks (RNNs)](#recurrent-neural-networks)
    - [Attention Networks](#transformers-and-attention-networks)
    - [Hybrid](#hybrid)
- [Shared Tasks](#shared-tasks)
- [Explainable Fact Checking](#explainable-fact-checking)
  - [Systems](#systems)
    - [Saliency maps](#saliency-maps)
    - [Rule discovery and graph based methods](#rule-discovery-and-graph-based-methods)
    - [Summarization](#summarization)
  - [Adversarial Training for Fact Checking](#adversarial-training-for-automated-fact-checking)
  - [Error Correction of Claims](#error-correction-of-claims)
  - [Multi-hop Fact Checking](#multihop-reasoning-for-facting-checking)
  - [Fact Checking with Intrepretable Features](#fact-checking-with-intrepretable-features)
- [Surveys](#further-fact-checking-surveys)
- [Tutorials](#tutorials)



## Introduction

Fact checking is the process of establishing the veracity of claims i.e., to distinguish between false stories (e.g., misattributions, rumours, hoaxes) and facts. 

Over the past few years the use of deep learning methods for fact checking and fake news detection have become a popular. Indeed, several exciting breakthroughs have occurred in automated fact checking thanks in large part due to new datasets (e.g., [FEVER](https://fever.ai/)) and advances in machine learning for NLP. However there are still some limitations in this research area, the one we focus on in this work in our work is __explanations__ for automated fact checking. 

The pipeline commonly employed for automated fact-checking consists of four parts (subtasks). We propose that post-hoc explanations are an important and necessary extension of this pipeline.

![fact-checking-pipeline](images/pipeline.svg)


For an overview of the data and results mentioned in our survey, please visit [this webpage](https://neemakot.github.io/project/survey).


## Task Formulations

Here we list papers which address varied tasks related to fact checking and fake news detection.

* __Check-worthy Claim Detection__
    - Toward Automated Fact-Checking: Detecting Check-worthy Factual Claims by ClaimBuster (Hassan et al., 2017).
    [[paper](http://library.usc.edu.ph/ACM/KKD%202017/pdfs/p1803.pdf)]
    [[bib](https://dblp.org/rec/conf/kdd/HassanALT17.html?view=bibtex)]

* __Fauxtography and Multimodal Fake News Detection__
  - FauxBuster: A Content-free Fauxtography Detector Using Social Media Comments (Zhang et al., 2018).
    [[paper](https://www3.nd.edu/~sslab/pdf/bigdata18-fb.pdf)]
    [[bib](https://www.computer.org/csdl/api/v1/citation/bibtex/proceedings/17D45VtKisB/08622344)]
    [[slides](http://dyzhang.net/proj-images/p2.pdf)]
  - Fact-Checking Meets Fauxtography: Verifying Claims About Images (Zlatkova et al., 2019).
    [[paper](https://www.aclweb.org/anthology/D19-1216.pdf)]
    [[bib](https://www.aclweb.org/anthology/D19-1216.bib)]
  - Eann: Event adversarial neural networks for multi-modal fake news detection (Wang et al., 2018).
    [[paper](https://cse.buffalo.edu/~lusu/papers/KDD2018Yaqing.pdf)]
    [[bib](https://dblp.org/rec/conf/kdd/WangMJYXJSG18.html?view=bibtex)]

* __Identifying Previously Fact-Checked Claims__
  - That is a Known Lie: Detecting Previously Fact-Checked Claims (Shaar et al., 2020).
    [[paper](https://www.aclweb.org/anthology/2020.acl-main.332.pdf)]
    [[bib](https://www.aclweb.org/anthology/2020.acl-main.332.bib)]
  - Where Are the Facts? Searching for Fact-checked Information to Alleviate the Spread of Fake News (Vo and Lee, 2020).
    [[paper](https://www.aclweb.org/anthology/2020.emnlp-main.621.pdf)]
    [[bib](https://www.aclweb.org/anthology/2020.emnlp-main.621.bib)]

* __Neural Fake News Detection__
  - Defending against neural fake news (Zellers et al., 2019).
    [[paper](https://proceedings.neurips.cc/paper/2019/file/3e9f0fc9b2f89e043bc6233994dfcf76-Paper.pdf)]
    [[bib](https://dblp.org/rec/conf/nips/ZellersHRBFRC19.html?view=bibtex)]
  - Detecting Cross-Modal Inconsistency to Defend Against Neural Fake News (Tan et al., 2020).
    [[paper](https://www.aclweb.org/anthology/2020.emnlp-main.163.pdf)]
    [[bib](https://www.aclweb.org/anthology/2020.emnlp-main.163.bib)]

* __Rumour Verification and Resolution__
  - SemEval-2019 Task 7: RumourEval, Determining Rumour Veracity and Support for Rumours (Gorrell et al., 2019).
  [[paper](https://www.aclweb.org/anthology/S19-2147.pdf)]
  [[bib](https://www.aclweb.org/anthology/S19-2147.bib)]
  - Can Rumour Stance Alone Predict Veracity? (Dungs et al., 2018).
  [[paper](https://www.aclweb.org/anthology/C18-1284.pdf)]
  [[bib](https://www.aclweb.org/anthology/C18-1284.bib)]
  - SemEval-2017 Task 8: RumourEval: Determining rumour veracity and support for rumours (Derczynski et al., 2017).
  [[paper](https://www.aclweb.org/anthology/S17-2006.pdf)]
  [[bib](https://www.aclweb.org/anthology/S17-2006.bib)]

* __Stylometric Analysis of News Articles__
  - A stylometric inquiry into hyperpartisan and fake news (Potthast et al., 2017)
  [[paper](https://www.aclweb.org/anthology/P18-1022.pdf)]
  [[bib](https://www.aclweb.org/anthology/P18-1022.bib)]
  [[video](https://vimeo.com/285800660)]
  - Truth of Varying Shades: Analyzing Language in Fake News and Political Fact-Checking (Rashkin et al., 2017).
  [[paper](https://www.aclweb.org/anthology/D17-1317.pdf)]
  [[bib](https://www.aclweb.org/anthology/D17-1317.bib)]

* __Table-based Fact Verification__
  - TabFact: A Large-scale Dataset for Table-based Fact Verification (Chen et al., 2020). 
  [[paper](https://openreview.net/pdf?id=rkeJRhNYDH)]
  [[bib](https://dblp.org/rec/conf/iclr/ChenWCZWLZW20.html?view=bibtex)]


* [__Multi-hop Fact Checking__](#multihop-reasoning-for-facting-checking)

* [__Error Correction of Claims__](#error-correction-of-claims)


## Fact Checking Datasets

List of fact checking, rumour verification and fake news detection datasets:

### Datasets of naturally occurring claims
  
#### Social media

Claims from social media platforms sources e.g., Twitter, Facebook.

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

Claims for news and fact-checking platforms e.g., [Snopes](https://www.snopes.com/), [Politifact](https://www.politifact.com/).
  
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
[[data](https://alt.qcri.org/resources/arabic-fact-checking-and-stance-detection-corpus/)]
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


## Fact Checking Systems

A list of fact-checking and fake news detection systems.

### Systems by Dataset

#### [LIAR](https://www.aclweb.org/anthology/P17-2067.pdf)

* Where is your Evidence: Improving Fact-checking by Justification
Modeling (Alhindi et al., 2018).
[[paper](https://www.aclweb.org/anthology/W18-5513.pdf)]
[[bib](https://www.aclweb.org/anthology/W18-5513.bib)]
[[code](https://github.com/Tariq60/LIAR-PLUS)]
* Generating Fact Checking Explanations (Atanasova et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.acl-main.656.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.acl-main.656.bib)]


#### [FEVER](https://www.aclweb.org/anthology/N18-1074.pdf)

* [FEVER 1.0 Baseline](https://github.com/sheffieldnlp/fever-naacl-2018)
* Combining Fact Extraction and Verification with Neural Semantic Matching Networks (Nie et al., 2019).
  [[paper](https://arxiv.org/pdf/1811.07039.pdf)]
  [[bib](https://dblp.org/rec/conf/aaai/NieCB19.html?view=bibtex)]
  [[code](https://github.com/easonnie/combine-FEVER-NSMN/)]
* UCL Machine Reading Group: Four Factor Framework For Fact Finding (HexaF) (Yoneda et al., 2018).
  [[paper](https://www.aclweb.org/anthology/W18-5515.pdf)]
  [[bib](https://www.aclweb.org/anthology/W18-5515.bib)] 
  [[code](https://github.com/uclmr/fever)]
* UKP-Athene: Multi-Sentence Textual Entailment for Claim Verification (Hanselowski et al., 2018).
  [[paper](https://www.aclweb.org/anthology/W18-5516.pdf)]
  [[bib](https://www.aclweb.org/anthology/W18-5516.bib)]
  [[code](https://github.com/UKPLab/fever-2018-team-athene)]
* Team Papelo: Transformer Networks at FEVER (Malon, 2018).
  [[paper](https://www.aclweb.org/anthology/W18-5517.pdf)]
  [[bib](https://www.aclweb.org/anthology/W18-5517.bib)]
  [[code](https://github.com/necla-ml/fever2018)]
* Team DOMLIN: Exploiting Evidence Enhancement for the FEVER Shared Task (Stammbach and Neumann, 2019).
  [[paper](https://www.aclweb.org/anthology/D19-6616.pdf)]
  [[bib](https://www.aclweb.org/anthology/D19-6616.bib)]
  [[code](https://github.com/necla-ml/fever2018)]
* GEAR: Graph-based Evidence Aggregating and Reasoning for Fact Verification
  [[paper](https://www.aclweb.org/anthology/P19-1085.pdf)]
  [[bib](https://www.aclweb.org/anthology/P19-1085.pdf)]
  [[code](https://github.com/thunlp/GEAR)]
* Fine-grained Fact Verification with Kernel Graph Attention Network
  [[paper](https://www.aclweb.org/anthology/2020.acl-main.655.pdf)]
  [[bib](https://www.aclweb.org/anthology/2020.acl-main.655.bib)]
  [[code](https://github.com/thunlp/KernelGAT)]


#### [MultiFC](https://www.aclweb.org/anthology/D19-1475.pdf)
* Time-Aware Evidence Ranking for Fact-Checking (Allein et al., 2020).
  [[paper](https://arxiv.org/pdf/2009.06402.pdf)]
  [[bib](https://dblp.org/rec/journals/corr/abs-2009-06402.html?view=bibtex)]


### Systems by Method

#### Support Vector Machines

* Fake News or Truth? Using Satirical Cues to Detect Potentially Misleading News.
  [[paper](https://www.aclweb.org/anthology/W16-0802.pdf)]
  [[bib](https://www.aclweb.org/anthology/W16-0802.bib)]


#### Convolutional Neural Networks

* “Liar, Liar Pants on Fire”: A New Benchmark Dataset for Fake News Detection (Wang, 2017).
  [[paper](https://www.aclweb.org/anthology/P17-2067.pdf)]
  [[bib](https://www.aclweb.org/anthology/P17-2067.bib)]
* FAKTA: An Automatic End-to-End Fact Checking System (Nadeeem et al., 2019).
  [[paper](https://www.aclweb.org/anthology/N19-4014.pdf)]
  [[bib](https://www.aclweb.org/anthology/N19-4014.bib)]

#### Recurrent Neural Networks

* CSI: A Hybrid Deep Model for Fake News Detection (Ruchansky et al., 2017).
  [[paper](https://arxiv.org/pdf/1703.06959.pdf)]
* DeClarE: Debunking Fake News and False Claims using Evidence-Aware Deep Learning (Popat et al., 2018).
  [[paper](https://www.aclweb.org/anthology/D18-1003.pdf)]
  [[bib](https://www.aclweb.org/anthology/D18-1003.bib)]
* Truth of Varying Shades: Analyzing Language in Fake News and Political Fact-Checking (Rashkin et al., 2017).
  [[paper](https://www.aclweb.org/anthology/D17-1317.pdf)]
  [[bib](https://www.aclweb.org/anthology/D17-1317.bib)]
* Where is your Evidence: Improving Fact-checking by Justification Modeling (Alhindi et al., 2018).
  [[paper](https://www.aclweb.org/anthology/W18-5513.pdf)]
  [[bib](https://www.aclweb.org/anthology/W18-5513.bib)]


#### [Transformers](https://arxiv.org/pdf/1706.03762.pdf) and Attention Networks

* Two Stage Transformer Model for COVID-19 Fake News Detection and Fact Checking (Vijjali et al., 2020).
  [[paper](https://www.aclweb.org/anthology/2020.nlp4if-1.1.pdf)]
  [[bib](https://www.aclweb.org/anthology/2020.nlp4if-1.1.bib)]

#### Hybrid

* GCAN: Graph-aware Co-Attention Networks for Explainable Fake News Detection on Social Media (Lu and Li, 2020).
[[paper](https://www.aclweb.org/anthology/2020.acl-main.48.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.acl-main.48.bib)]
* DTCA: Decision Tree-based Co-Attention Networks for Explainable Claim Verification (Wu et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.acl-main.97.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.acl-main.97.bib)]
* XFake: Explainable Fake News Detector with Visualizations (Yang et al., 2019).
[[paper](https://arxiv.org/pdf/1907.07757.pdf)]
[[bib](https://dblp.uni-trier.de/rec/conf/www/YangPMDYLRJH19.html?view=bibtex)]


## Shared Tasks

📣  
indicates the shared task is ongoing!

* Statement Verification and Evidence Finding with Tables (SEM-TAB-FACT) [[Wang et al., 2021](https://competitions.codalab.org/competitions/27748)] 📣 (_Ends on Jan 29 2021_)
* SciFact Claim Verifiation [[Wadden et al., 2020](https://sdproc.org/2021/sharedtasks.html#sciver)] 📣
* Fakeddit Multimodal Fake News Detection Challenge [[Nakamura et al., 2020](https://competitions.codalab.org/competitions/25337#learn_the_details)] 📣 (_Ends on Feb 16 2021_)
* SemEval-2019 Task 7: RumourEval, Determining Rumour Veracity and Support for Rumours [[Gorrell et al., 2019](https://www.aclweb.org/anthology/S19-2147/)]
* SemEval-2019 Task 8: Fact Checking in Community Question Answering Forums [[Mihaylova et al., 2019](https://www.aclweb.org/anthology/S19-2149/)]
* The Fake News Challenge (FNC-1) [[Pomerleau and Rao, 2017](http://www.fakenewschallenge.org/)]
  * A Retrospective Analysis of the Fake News Challenge Stance-Detection Task [[Hanselowski et al., 2018](https://www.aclweb.org/anthology/C18-1158/)]
* The Fact Extraction and VERification (FEVER) Shared Task [[Thorne et al., 2018](https://www.aclweb.org/anthology/W18-5501/)]
* SemEval-2017 Task 8: RumourEval: Determining rumour veracity and support for rumours [[Derczynski et al., 2017](https://www.aclweb.org/anthology/S17-2006/)]


## Explainable Fact Checking

### Systems

A list of works on explainability in fact-checking and fake news detection:

#### Saliency maps

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

#### Rule discovery and graph based methods

* ExFaKT: A Framework for Explaining Facts over Knowledge Graphs and Text (Gad-Elrab et al., 2019).
[[paper](https://people.mpi-inf.mpg.de/~gadelrab/downloads/WSDM2019/ExFaKT_preprint.pdf)]
[[bib](https://dblp.org/rec/conf/wsdm/Gad-Elrab0UW19.html?view=bibtex)]
* Explainable Fact Checking with Probabilistic Answer Set Programming (Ahmadi et al., 2019).
[[paper](https://truthandtrustonline.files.wordpress.com/2019/09/paper_15.pdf)]
[[bib](https://dblp.org/rec/conf/tto/AhmadiLPS19.html?view=bibtex)] 
* Linked Credibility Reviews for Explainable
Misinformation Detection (Denaux et al., 2020).
[[paper](https://arxiv.org/pdf/2008.12742.pdf)
[[bib](https://dblp.org/rec/conf/semweb/DenauxG20.html?view=bibtex)]


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


### Error Correction of Claims

* Factual Error Correction of Claims (Thorne and Vlachos, 2020).
[[paper](https://arxiv.org/pdf/2012.15788.pdf)]
[[bib](https://dblp.org/rec/journals/corr/abs-2012-15788.html?view=bibtex)]


### Fact Checking with Intrepretable Features

* A Language-Based Approach to Fake News Detection Through Interpretable Features and BRNN (Qiao et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.rdsm-1.2.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.rdsm-1.2.bib)]


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


## Surveys

Automated fact checking and fake news detection surveys:

* A Survey of Fake News: Fundamental Theories, Detection Methods, and Opportunities (Zhou and Zafarani, 2020).
[[paper](https://dl.acm.org/doi/10.1145/3395046)]
[[bib](https://dblp.org/rec/journals/csur/ZhouZ20.html?view=bibtex)]
* A Review on Fact Extraction and VERification: The FEVER case (Bekoulis et al., 2020).
[[paper](https://arxiv.org/abs/2010.03001)]
[[bib](https://dblp.org/rec/journals/corr/abs-2010-03001.html?view=bibtex)]
* A Survey on Fake News and Rumour Detection Techniques (Bondielli and Marcelloni, 2020).
[[paper](https://www.sciencedirect.com/science/article/abs/pii/S0020025519304372?via%3Dihub)]
[[bib](https://dblp.org/rec/journals/isci/BondielliM19.html?view=bibtex)]
* A Survey on Natural Language Processing for Fake News Detection (Oshikawa et al., 2020).
[[paper](https://www.aclweb.org/anthology/2020.lrec-1.747.pdf)]
[[bib](https://www.aclweb.org/anthology/2020.lrec-1.747.bib)]
* Fake News Detection using Stance Classification: A Survey (Lillie and Middelboe, 2019).
[[paper](https://arxiv.org/pdf/1907.00181.pdf)]
[[bib](https://dblp.org/rec/journals/corr/abs-1907-00181.html?view=bibtex)]
* Detection and Resolution of Rumours in Social Media: A Survey (Zubiaga et al., 2018).
[[paper](http://kddlab.zjgsu.edu.cn:7200/research/rumor/Detection%20and%20Resolution%20of%20Rumours%20in%20Social%20Media_%20A%20Survey.pdf)]
[[bib](https://dblp.uni-trier.de/rec/journals/csur/ZubiagaABLP18.html?view=bibtex)]
* Automated Fact Checking: Task Formulations, Methods and Future Directions (Thorne and Vlachos, 2018).
[[paper](https://www.aclweb.org/anthology/C18-1283.pdf)]
[[bib](https://www.aclweb.org/anthology/C18-1283.bib)]
* Media-Rich Fake News Detection: A Survey (Parikh and Atrey, 2018).
[[paper](https://www.albany.edu/~sp191221/publications/Fake_Media_Rich_News_Detection_A_Survey.pdf)]
[[bib](https://dblp.org/rec/conf/mipr/ParikhA18.html?view=bibtex)]
* A Content Management Perspective on Fact-Checking (Cazalens et al., 2018).
[[paper](https://hal.archives-ouvertes.fr/hal-01722666/document)]
[[bib](https://dblp.org/rec/journals/pvldb/CazalensLMLT18.html?view=bibtex)]
* Fake News Detection on Social Media: A Data Mining Perspective (Shu et al., 2017).
[[paper](https://arxiv.org/pdf/1708.01967.pdf)]
[[bib](https://dblp.org/rec/journals/sigkdd/ShuSWTL17.html?view=bibtex)]

## Tutorials
* Fact Checking: Theory and Practice [[Dong et al., KDD 2018](https://shiralkarprashant.github.io/fact-checking-tutorial-KDD2018/)].
* Fact-Checking, Fake News, Propaganda, and Media Bias: Truth Seeking in the Post-Truth Era [[Nakov and Da San Martino, EMNLP 2020](https://propaganda.qcri.org/emnlp20-tutorial/)].
* Detection and Resolution of Rumors and Misinformation with NLP [[Derczynski and Zubiaga, COLING 2020](https://www.aclweb.org/anthology/2020.coling-tutorials.4.pdf)] [[slides](https://docs.google.com/presentation/d/1ZBVPtHcVgJW2c_ibrdVuoCH7sU9ha8NS7Fq9GCnBnls/edit?usp=sharing)].

## Contact 

Please feel free to contact [Neema Kotonya](mailto:nk2418@ic.ac.uk) if you have any questions or comments.

