# What is PiC?


**Phrase in Context** is a curated benchmark for phrase understanding and semantic search, consisting of three tasks of increasing difficulty: Phrase Similarity (PS), Phrase Retrieval (PR) and Phrase Sense Disambiguation (PSD). The datasets are annotated by 13 linguistic experts on Upwork and verified by two groups: ~1000 AMT crowdworkers and another set of 5 linguistic experts. PiC benchmark is distributed under [CC-BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).



<!-- <div class="row">
  <div class="column-left">
    <figure>
    <a href="/assets/img/pic_sample.png"><img src="/assets/img/pic_sample.png" alt="" width="100%"></a>
    <figcaption style="text-align:center">An example in PS, PR, and PSD datasets.</figcaption>
  </figure>
  </div>
  <div class="column-right">
    <figure>
      <a href="/assets/img/pic_construction.png"><img src="/assets/img/pic_construction.png" alt="" width="100%"></a>
      <figcaption>Upwork experts rephrase “massive figure” in two pages (Q1 & Q2) and answer Q3 whether this phrase has the same meaning in two pages.</figcaption>
    </figure>
  </div>
</div> -->

<!-- <figure>
  <a href="/assets/img/pic_construction.png"><img src="/assets/img/pic_construction.png" alt="" width="60%"></a>
  <figcaption style="text-align:left">Upwork experts rephrase “massive figure” in two pages (Q1 & Q2) and answer Q3 whether this phrase has the same meaning in two pages.</figcaption>
</figure>  -->

<!-- <figure style="text-align:center">
  <a href="/assets/img/pic_tasks.png"><img src="/assets/img/pic_tasks.png" alt="" width="100%"></a>
  <figcaption style="text-align:left">Given each annotation i.e. phrase1 or phrase2 produced by Upwork experts above, from left to right, we construct a pair of positive and negative examples for PS (1), 1 PR-pass example (2) and 1 PR-page example (3) with the difference in document length. Only if the answer of Q3 is "No", we construct a PSD example (4) from each annotation.
</figcaption>
</figure>
 -->
 
 <figure style="text-align:center">
  <a href="/assets/img/pic_tasks.png"><img src="/assets/img/pic_construction_new.png" alt="" width="100%"></a>
  <figcaption style="text-align:left">
    Given a phrase, two associated Wikipedia pages, and expert annotations, i.e. answers to Q1, Q2, and Q3 (a), we are able to construct two pairs of positive and negative examples for PS (b), a PR-pass example (c), a PR-page example (d), and a PSD example only if the answer to Q3 is No (e).
  </figcaption>
</figure>


## PS: Phrase Similarity

PS is a binary classification task with the goal of predicting whether two multi-word noun phrases are semantically similar or not given the same context sentence. This dataset contains ~56K pairs of two phrases along with their contexts used for disambiguation, since two phrases only sometimes are not enough for semantic comparison. Around 28K positive examples were annotated by linguistic experts on [Upwork.com](https://upwork.com) while the other 28K negative examples were created by randomly replacing 50% of the phrase tokens in the positive examples.


<a style="width:200px" href="phrase_similarity" class="btn-bootstrap btn-outline-ps">Explore PS</a>
<a style="width:200px" href="https://huggingface.co/datasets/PiC/phrase_similarity" class="btn-bootstrap btn-outline-ps">Download PS</a>


## PR: Phrase Retrieval

PR is a phrase retrieval task with the goal of finding a phrase **t** in a given document **d** such that **t** is semantically similar to the query phrase, which is the paraphrase **q** provided by annotators. We release two versions of PR: **PR-pass** and **PR-page**, i.e., datasets of 3-tuples (query **q**, target phrase **t**, document **d**) where **d** is a random 11-sentence passage that contains **t** or an entire Wikipedia page. While PR-pass contains 28,147 examples, PR-page contains slightly fewer examples (28,098) as we remove those trivial examples whose Wikipedia pages contain exactly the query phrase (in addition to the target phrase). Both datasets are split into 5K/3K/~20K for test/dev/train, respectively.


<a style="width:200px" href="phrase_retrieval" class="btn-bootstrap btn-outline-pr">Explore PR</a>
<a style="width:200px" href="https://huggingface.co/datasets/PiC/phrase_retrieval" class="btn-bootstrap btn-outline-pr">Download PR</a>

## PSD: Phrase Sense Disambiguation

PSD is a phrase retrieval task like PR-pass and PR-page but more challenging since each example contains two short paragraphs (~11 sentences each) which trigger different senses of the same phrase. The goal is to find the instance of the target phrase **t** that is semantically similar to a paraphrase **q**. The dataset is split into 5,150/3,000/20,002 for test/dev/train, respectively.


<a style="width:200px" href="phrase_sense_disambiguation" class="btn-bootstrap btn-outline-psd">Explore PSD</a>
<a style="width:200px" href="https://huggingface.co/datasets/PiC/phrase_sense_disambiguation" class="btn-bootstrap btn-outline-psd">Download PSD</a>

<br/>

-----

Joint work between Adobe Research and Auburn University: [Thang Pham](https://twitter.com/pmthangxai), [Seunghyun Yoon](https://david-yoon.github.io), [Trung Bui](https://research.adobe.com/person/trung-bui/), and [Anh Nguyen](https://anhnguyen.me).


```
@article{pham2022PiC,
  title={PiC: A Phrase-in-Context Dataset for Phrase Understanding and Semantic Search},
  author={Pham, Thang M and Yoon, Seunghyun and Bui, Trung and Nguyen, Anh},
  journal={arXiv preprint arXiv:2207.09068},
  year={2022}
}
```

