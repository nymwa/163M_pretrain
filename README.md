# 163M pretrain

pretrained models using 163M data presented in "Various Errors Improve Neural Grammatical Error Correction"

- bpe.model / bpe.vocab
	- models of sentencepiece (0.1.95)

- {1..5}.pt
	- pretrained models of fairseq (0.10.2)
	- trained using 163M sentences x 20 epochs
	- [1.pt](https://drive.google.com/file/d/1-_AUqFr5GfSKs9DVRXJkTB-rRKaUFcnU/view?usp=sharing)
	- [2.pt](https://drive.google.com/file/d/1tJwJc3Enck9XEVRuH3H0fwpFvY0Pk-mr/view?usp=sharing)
	- [3.pt](https://drive.google.com/file/d/1i9qy4TpEZkDHfcWJ70LRjHKnLiJf8SWC/view?usp=sharing)
	- [4.pt](https://drive.google.com/file/d/1N0k7RaqOQcOnlVzOvb1mvBUX8Z9sZ-E6/view?usp=sharing)
	- [5.pt](https://drive.google.com/file/d/1Ar38-lweGRGmzxtaqWi1a8HyGdU_jCVD/view?usp=sharing)
	- 

- data-bin/dict.{src,trg}.txt
	- vocabulary of fairseq models

- note
	- Please normalize inputs before applying BPE using reguligilo (https://github.com/nymwa/reguligilo).
	- Please use -a option like `reguligilo -a`.
	- input -> reguligilo -> bpe -> encoder-decoder -> remove bpe -> malreguligilo (denormalization) -> output

- scores (beam=12 lenpen=0.6)

| | BEA19 | CoNLL 14 | JFLEG |
| --- | --- | --- | --- |
| single 0 | 59.62 | 55.05 | 58.09 |
| single 1 | 59.71 | 55.29 | 58.01 |
| single 2 | 60.59 | 56.22 | 58.09 |
| single 3 | 59.76 | 55.35 | 58.56 |
| single 4 | 59.82 | 55.17 | 58.39 |
| average  | 59.90 | 55.42 | 58.23 |
| ensemble | 60.89 | 55.73 | 58.37 |

