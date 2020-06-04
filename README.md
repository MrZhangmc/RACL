# RACL
 Code and datasets of our paper "Relation-Aware Collaborative Learning for Unified Aspect-Based Sentiment Analysis" accepted by ACL 2020.

## 1.Requirements
 To reproduce the reported results accurately, install the specific version of each package.

* python 3.6.10
* tensorflow-gpu 1.5.0
* numpy 1.16.4
* scikit-learn 0.22.2

## 2. Usage
 We incorporate the training and evaluation of RACL in the **train_racl.py**. Just run it as below.

```
CUDA_VISIBLE_DEVICES=0 python train_racl.py --task res14 --load 0
```

 We use the datasets pre-processed by [IMN](https://github.com/ruidan/IMN-E2E-ABSA). The results of 5 runs should be like this.

 | Res14  | AE\-F1  | OE\-F1  | SC\-F1  | ABSA\-F1 |
 |--------|---------|---------|---------|----------|
 | round1 | 85\.38  | 85\.31  | 74\.72  | 70\.80   |
 | round2 | 85\.41  | 85\.03  | 74\.58  | 70\.72   |
 | round3 | 85\.20  | 85\.55  | 74\.26  | 70\.43   |
 | round4 | 85\.20  | 85\.29  | 74\.19  | 70\.43   |
 | round5 | 85\.68  | 85\.42  | 74\.56  | 70\.96   |
 | **AVG**    | **85\.37**  | **85\.32**  | **74\.46**  | **70\.67**   |

## 3. Checkpoints
 If you have problems in training RACL, you can also use the released pre-trained weights on the following links.

* Google Drive : [Click here.](https://drive.google.com/file/d/1nfdqwEZfWsnQe6uOO7tx-QlmMFuomOW2/view?usp=sharing)
* Baidu Cloud : [Click here.](https://pan.baidu.com/s/1OZODodg3O7DIG0hyjYQxJg) (password:78qy)

 Unzip the pre-trained weights in the **checkpoint** folder, and execute the command as below.  

```
CUDA_VISIBLE_DEVICES=0 python train_racl.py --task res14 --load 1
```

 The results after loading weights should be like this.

 | Dataset | AE\-F1  | OE\-F1  | SC\-F1  | ABSA\-F1 |
 |---------|---------|---------|---------|----------|
 | Res14   | 85\.33  | 86\.09  | 76\.31  | 71\.61   |
 | Lap14   | 82\.81  | 77\.91  | 73\.04  | 62\.59   |
 | Res15   | 71\.76  | 76\.74  | 67\.74  | 61\.20   |

## 4. Embeddings
 We have generated the word-idx mapping file and the global-purpose and domain-specific embeddings in the **data** folder. If you want to generate them from scratch, follow the steps below.

* Download [glove.840B.300d.txt](https://nlp.stanford.edu/projects/glove/), rename it to **glove_emb.txt**, and put it in the folder like **./data/res14**.
* Download [domain-specific vectors](https://howardhsu.github.io/) proposed by DE-CNN, rename it to **domain_emb.txt**, and put it in the folder like **./data/res14**. Notice that **restaurant_emb.vec** is for datasets Res14 and Res15, and **laptop_emb.vec** is for Lap14.
* Specify the task (i.e., Res14) in **embedding.py**, then run it.
* Word embeddings will be generated in the corresponding folder, e.g., **./data/res14/glove_embedding.npy**.

## 5. RACL-BERT
 We haven't yet integrated the BERT-based version at present. Since we create a separate project for RACL-BERT, it takes time to merge it to this repo. We may update it in late July. 

## 6. Citation
 Wait for publication. 
 We will update the information in time. :checkered_flag:
