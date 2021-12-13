# Kpf-Bert Sentence BERT

## 모델 소개

### KpfSBERT

Sentence BERT는 bert를 문장단위 Embedding을 통하여 빠르고 효율적으로 의미비교 등의 테스크에 활용되고, 또한 우수한 성능을 보여주고 있는 모델이다.
여기서는 kpfBERT모델을 활용하여 트레이닝 및 파인튜닝하여 kpfSBERT 모델을 제작하는 과정으로 이후 뉴스클러스터링에 활용하였다.
한국언론진흥재단에서 구축한 방대한 뉴스기사 코퍼스로 학습한 kpfBERT를 이용하여 특히 뉴스기사에 특화된 모델이다.

- 본 예제에 사용된 kpf-BERT는 [kpfBERT](https://github.com/KPFBERT/kpfbert)에 공개되어 있다.

- 한국어 데이터 셋은 카카오브레인에서 제공하는 [KorNLI and KorSTS](https://github.com/kakaobrain/KorNLUDatasets)를 사용하였다.


### Bert를 이용한 문서요약 관련 논문 및 코드

- 논문:  [Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/abs/1908.10084)
- 원코드: https://github.com/UKPLab/sentence-transformers

- Ko-Sentence-BERT : https://github.com/BM-K/KoSentenceBERT_ETRI


## 실행하기 위한 환경

1. 라이브러리

    ```
    python = 3.7
    PyTorch >= 1.6.0
    transformers >= 4.6.0
    sentence_transformers == 2.1.0
    
    ```
    
2. GPU

    ```
    NVIDIA - 2080 SUPER (8G) 환경에서 작성되었음
    ```

## Usage

1. 데이터 Preprocessing

   `./KorNLUDatasets/` 디렉토리에 KorNLUDatasets 데이터셋 화일을 넣어준다.

   - `KorNLUDatasets/KorNLI/snli_1.0_train.ko.tsv`: 트레이닝에 사용된 NLI.  
   - `KorNLUDatasets/KorSTS/tune_dev.tsv`: Ko-Sentence-BERT에서 사용한 튜닝된 STS 데이터.

   
2. Training  

    SBERT에서 가장 좋은 성능을 보여준 NLI+STS 방식으로 트레이닝 진행.

    - `kpfbert-base/` kpfbert 다운받은 화일들이 위치할 곳
    - `output/kpfSBERT` kpfSBERT 모델이 저장되는 곳.
    

## Citing
#### KorNLUDatasets
   ```
    @article{ham2020kornli,
  title={KorNLI and KorSTS: New Benchmark Datasets for Korean Natural Language Understanding},
  author={Ham, Jiyeon and Choe, Yo Joong and Park, Kyubyong and Choi, Ilji and Soh, Hyungjoon},
  journal={arXiv preprint arXiv:2004.03289},
  year={2020}
}
   ```
