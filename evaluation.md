# Evaluation

We set up an initial benchmark for 3 tasks in PiC.
Please refer to [our paper](https://arxiv.org) for experiment details and [Github repo](https://github.com/Phrase-in-Context/eval) for reproducing results.

### Metrics 

Like other classification tasks, we present **Accuracy** for *Phrase Similarity*.
In *Phrase Retrieval* task, there are two approaches: ranking and Q/A (i.e., predict the start and the end indexes of the answer). We report **Top@K accuracy** and **Mean Reciprocal Rank (MRR@K)** for the former and **Exact Match (EM)** i.e., Top@1 accuracy and **F1** for the latter.
In *Phrase Sense Disambiguation* task, we focus on Q/A approach since it almost reaches human performance (95%). Also, the correct answer needs to be extracted from the correct paragraph that triggers the meaning semantically similar to the user query. Thus, we also report **EM + index** and **F1 + index**.


### 1. Phrase Similarity

<figure style="text-align:center">
  <a href="/assets/img/results_ps.png"><img src="/assets/img/results_ps.png" alt="" width="100%"></a>
  <figcaption style="text-align:center;">
  	Accuracy (%) of state-of-the-art models on the PS test set.
</figcaption>
</figure>


### 2. Phrase Retrieval

#### a. Ranking-based approach

<figure style="text-align:center">
  <a href="/assets/img/results_pr_pass.png"><img src="/assets/img/results_pr_pass.png" alt="" width="100%"></a>
  <figcaption style="text-align:left;">
  	Ranking accuracy on <b>PR-pass</b> using the state-of-the-art pretrained phrase embeddings (a) and those finetuned on PR-pass via QA-style training (b)
</figcaption>
</figure>

<br/>

<figure style="text-align:center">
  <a href="/assets/img/results_pr_page.png"><img src="/assets/img/results_pr_page.png" alt="" width="100%"></a>
  <figcaption style="text-align:left;">
  	Ranking accuracy on <b>PR-page</b> using the state-of-the-art pretrained phrase embeddings (a) and those finetuned on PR-pass via QA-style training (b)
</figcaption>
</figure>


#### b. Q/A approach

See the table below for (a) and (b).

### 3. Phrase Sense Disambiguation

<figure style="text-align:center">
  <a href="/assets/img/results_qa.png"><img src="/assets/img/results_qa.png" alt="" width="100%"></a>
  <figcaption style="text-align:left;">
  	Test-set performance of trained QA models. For (a) and (b), models are trained and tested on their same datasets while for (c) models here are tested on PSD but trained on PR-pass.
</figcaption>
</figure>
