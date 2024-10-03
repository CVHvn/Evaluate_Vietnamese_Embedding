# Evaluate_Vietnamese_Embedding
Evaluate Vietnamese Embedding Models

## Introduction
This project evaluates embedding models on [Semantic Textual Similarity on STS Benchmark](https://huggingface.co/datasets/anti-ai/ViSTS). The evaluation metrics used are Spearman correlation (spearman_styled) and Pearson correlation (pearson_styled).

## List model
- jinaai/jina-embeddings-v3
- openai/text-embedding-3-small
- openai/text-embedding-3-large
- openai/text-embedding-ada-002
- dangvantuan/vietnamese-embedding
- dangvantuan/vietnamese-embedding-LongContext
- Alibaba-NLP/gte-multilingual-base
- Alibaba-NLP/gte-multilingual-mlm-base
- BAAI/bge-m3
- BAAI/bge-m3-unsupervised
- BAAI/bge-m3-retromae
- intfloat/multilingual-e5-small
- intfloat/multilingual-e5-base
- intfloat/multilingual-e5-large
- nampham1106/bkcare-embedding
- VoVanPhuc/unsup-SimCSE-VietNamese-phobert-base
- VoVanPhuc/sup-SimCSE-VietNamese-phobert-base
- keepitreal/vietnamese-sbert
- bkai-foundation-models/vietnamese-bi-encoder
- hiieu/halong_embedding

## Results
- Rows with "_pyvi_tokenizer" indicate the use of pyvi.tokenizer.
- For Jina v3, "_matching" indicates the use of the parameter task = 'text-matching', and "_retrieval" indicates the use of the parameters task = 'retrieval' and prompt_name as "retrieval.query" and "retrieval.passage".

### spearman_styled
- You can view result in [df_spearman_styled.xlsx](df_spearman_styled.xlsx)

|                                                               |   STS-B |   STS12 |   STS13 |   STS14 |   STS15 |   STS16 |   STS-Sickr |    Mean |
|:--------------------------------------------------------------|--------:|--------:|--------:|--------:|--------:|--------:|------------:|--------:|
| dangvantuan/vietnamese-embedding_pyvi_tokenizer               |   84.84 |   **79.04** |   **85.3**  |   81.38 |   87.06 |   79.95 |       79.58 | **82.45**   |
| dangvantuan/vietnamese-embedding-LongContext                  |   85.25 |   75.77 |   83.82 |   **81.69** |   **88.48** |   81.5  |       78.2  | 82.1014 |
| jinaai/jina-embeddings-v3_matching                            |   **86.51** |   77.3  |   83.05 |   77.42 |   84.53 |   **82.75** |       **82.72** | 82.04   |
| jinaai/jina-embeddings-v3                                     |   84.01 |   74.06 |   82.45 |   75.74 |   84.9  |   81.27 |       77.33 | 79.9657 |
| jinaai/jina-embeddings-v3_matching_pyvi_tokenizer             |   85.07 |   72.93 |   77.87 |   73.71 |   83.13 |   79.13 |       80.83 | 78.9529 |
| Alibaba-NLP/gte-multilingual-base                             |   82.65 |   73.85 |   77.57 |   74.62 |   85.94 |   79.85 |       77.34 | 78.8314 |
| VoVanPhuc/sup-SimCSE-VietNamese-phobert-base_pyvi_tokenizer   |   81.43 |   76.51 |   79.19 |   74.91 |   81.72 |   76.57 |       76.45 | 78.1114 |
| BAAI/bge-m3                                                   |   82.01 |   73.47 |   75.17 |   71.93 |   84.54 |   82.26 |       77.31 | 78.0986 |
| dangvantuan/vietnamese-embedding-LongContext_pyvi_tokenizer   |   81.79 |   72.3  |   77.64 |   75.24 |   85.89 |   76.69 |       76.04 | 77.9414 |
| jinaai/jina-embeddings-v3_pyvi_tokenizer                      |   81.92 |   70.6  |   79.46 |   72.94 |   83.52 |   78.21 |       75.65 | 77.4714 |
| intfloat/multilingual-e5-large                                |   81.62 |   71.77 |   71.86 |   68.88 |   84.53 |   81.34 |       77.61 | 76.8014 |
| dangvantuan/vietnamese-embedding                              |   78.67 |   70.28 |   78.42 |   74.73 |   82.92 |   75.73 |       74.03 | 76.3971 |
| keepitreal/vietnamese-sbert_pyvi_tokenizer                    |   80.16 |   69.08 |   80.99 |   73.67 |   82.81 |   74.3  |       73.4  | 76.3443 |
| openai/text-embedding-3-large                                 |   78.94 |   67.21 |   78.71 |   69.78 |   80.66 |   81.24 |       75.36 | 75.9857 |
| nampham1106/bkcare-embedding_pyvi_tokenizer                   |   79.88 |   72.66 |   78.35 |   70.74 |   77.61 |   75.14 |       77.38 | 75.9657 |
| intfloat/multilingual-e5-base                                 |   80.03 |   71.03 |   72.27 |   68.29 |   81.76 |   80.21 |       76.22 | 75.6871 |
| intfloat/multilingual-e5-large_pyvi_tokenizer                 |   80.69 |   71.37 |   69.96 |   68.77 |   81.44 |   80.09 |       75.12 | 75.3486 |
| openai/text-embedding-3-large_pyvi_tokenizer                  |   77.2  |   66.06 |   77.58 |   69.29 |   79.93 |   80.56 |       74.39 | 75.0014 |
| keepitreal/vietnamese-sbert                                   |   78.09 |   68.28 |   78.45 |   73.62 |   82.95 |   72.71 |       70.7  | 74.9714 |
| BAAI/bge-m3_pyvi_tokenizer                                    |   78.41 |   70.72 |   69.08 |   68.65 |   82.79 |   79.28 |       75.72 | 74.95   |
| hiieu/halong_embedding                                        |   78.36 |   67.66 |   76.06 |   69.38 |   79.97 |   78.92 |       74.08 | 74.9186 |
| intfloat/multilingual-e5-small                                |   78.24 |   72.92 |   69.88 |   67.74 |   81.57 |   78.82 |       74.98 | 74.8786 |
| Alibaba-NLP/gte-multilingual-base_pyvi_tokenizer              |   77.94 |   69.51 |   71.17 |   68.44 |   83.05 |   74.52 |       75.18 | 74.2586 |
| BAAI/bge-m3-unsupervised                                      |   76.53 |   64.02 |   72.85 |   68.02 |   80.35 |   79.47 |       74.04 | 73.6114 |
| intfloat/multilingual-e5-base_pyvi_tokenizer                  |   76.75 |   69.2  |   67.26 |   65.73 |   79.35 |   77.53 |       72.4  | 72.6029 |
| VoVanPhuc/sup-SimCSE-VietNamese-phobert-base                  |   75.22 |   69.23 |   72.3  |   69.04 |   77.99 |   72.7  |       71.25 | 72.5329 |
| BAAI/bge-m3-unsupervised_pyvi_tokenizer                       |   74.2  |   63.01 |   70.06 |   66.6  |   78.82 |   77.82 |       70.95 | 71.6371 |
| hiieu/halong_embedding_pyvi_tokenizer                         |   74.54 |   62.74 |   71.41 |   65.51 |   78.66 |   75.35 |       70.86 | 71.2957 |
| intfloat/multilingual-e5-small_pyvi_tokenizer                 |   74.7  |   69.58 |   64.91 |   64.72 |   78.67 |   75.95 |       70.54 | 71.2957 |
| openai/text-embedding-3-small                                 |   71.66 |   61.65 |   69.62 |   64.95 |   76.67 |   75.93 |       68.24 | 69.8171 |
| nampham1106/bkcare-embedding                                  |   73.38 |   63.64 |   69.43 |   63.92 |   74.73 |   71.9  |       70.87 | 69.6957 |
| jinaai/jina-embeddings-v3_retrieval                           |   72.23 |   52.36 |   76.79 |   65.67 |   80.35 |   72.45 |       61.51 | 68.7657 |
| VoVanPhuc/unsup-SimCSE-VietNamese-phobert-base_pyvi_tokenizer |   68.81 |   61.6  |   70.95 |   64.28 |   75.72 |   70.74 |       69.23 | 68.7614 |
| openai/text-embedding-3-small_pyvi_tokenizer                  |   69.85 |   60.59 |   65.73 |   62.47 |   76.25 |   74.88 |       67.77 | 68.22   |
| openai/text-embedding-ada-002                                 |   71.36 |   58.65 |   66.7  |   59.36 |   72.44 |   75.58 |       67.84 | 67.4186 |
| VoVanPhuc/unsup-SimCSE-VietNamese-phobert-base                |   65.02 |   56.81 |   69.15 |   62.81 |   73.27 |   68.46 |       65.96 | 65.9257 |
| openai/text-embedding-ada-002_pyvi_tokenizer                  |   69.5  |   56.99 |   63.91 |   56.95 |   71.3  |   74.3  |       67.06 | 65.7157 |
| jinaai/jina-embeddings-v3_retrieval_pyvi_tokenizer            |   65.12 |   53.93 |   70.2  |   62.99 |   77.55 |   69.99 |       58.31 | 65.4414 |
| BAAI/bge-m3-retromae                                          |   64.24 |   56.13 |   56.32 |   55.99 |   65.65 |   66.38 |       63.27 | 61.14   |
| BAAI/bge-m3-retromae_pyvi_tokenizer                           |   60.61 |   56.66 |   50.02 |   52.61 |   56.93 |   60.96 |       58.62 | 56.63   |
| Alibaba-NLP/gte-multilingual-mlm-base_pyvi_tokenizer          |   50.7  |   46.2  |   39.62 |   42.38 |   51.61 |   58.16 |       52.17 | 48.6914 |
| Alibaba-NLP/gte-multilingual-mlm-base                         |   48.33 |   42.49 |   39.82 |   38.64 |   56.12 |   57.88 |       53.86 | 48.1629 |

### pearson_styled
- You can view result in [df_pearson_styled.xlsx](df_pearson_styled.xlsx)

|                                                               |   STS-B |   STS12 |   STS13 |   STS14 |   STS15 |   STS16 |   STS-Sickr |    Mean |
|:--------------------------------------------------------------|--------:|--------:|--------:|--------:|--------:|--------:|------------:|--------:|
| dangvantuan/vietnamese-embedding-LongContext                  |   85.06 |   86.21 |   84.32 |   **83.28** |   **88.3**  |   80.87 |       82.86 | **84.4143** |
| dangvantuan/vietnamese-embedding_pyvi_tokenizer               |   84.87 |   **87.23** |   **85.39** |   82.94 |   86.91 |   79.39 |       82.77 | 84.2143 |
| jinaai/jina-embeddings-v3_matching                            |   **86.03** |   83.59 |   81.91 |   78.96 |   83.81 |   **81.43** |       **86.99** | 83.2457 |
| jinaai/jina-embeddings-v3                                     |   84.23 |   81.97 |   81.22 |   77.3  |   84.27 |   80.4  |       83.2  | 81.7986 |
| dangvantuan/vietnamese-embedding-LongContext_pyvi_tokenizer   |   81.96 |   82.19 |   78    |   77.49 |   85.69 |   76.35 |       80.78 | 80.3514 |
| jinaai/jina-embeddings-v3_matching_pyvi_tokenizer             |   84.7  |   79.41 |   76.7  |   75.46 |   82.61 |   78    |       85.24 | 80.3029 |
| Alibaba-NLP/gte-multilingual-base                             |   82.43 |   81.33 |   77.02 |   75.97 |   85.49 |   79.09 |       80.27 | 80.2286 |
| VoVanPhuc/sup-SimCSE-VietNamese-phobert-base_pyvi_tokenizer   |   81.52 |   85.02 |   78.22 |   75.94 |   81.53 |   75.39 |       77.75 | 79.3386 |
| jinaai/jina-embeddings-v3_pyvi_tokenizer                      |   82.11 |   78.25 |   78.41 |   74.64 |   82.93 |   77.44 |       81.24 | 79.2886 |
| BAAI/bge-m3                                                   |   81.56 |   79.38 |   74.52 |   71.6  |   84.13 |   81.37 |       80.25 | 78.9729 |
| keepitreal/vietnamese-sbert_pyvi_tokenizer                    |   80.54 |   78.58 |   80.75 |   76.98 |   82.57 |   73.21 |       80.16 | 78.97   |
| intfloat/multilingual-e5-large                                |   82.1  |   79.55 |   71.42 |   70.05 |   84.13 |   81.07 |       81.19 | 78.5014 |
| dangvantuan/vietnamese-embedding                              |   78.97 |   77.82 |   78.37 |   76.73 |   82.77 |   75.65 |       76.84 | 78.1643 |
| nampham1106/bkcare-embedding_pyvi_tokenizer                   |   80.63 |   80.59 |   78.06 |   73.97 |   77.58 |   74.16 |       81.23 | 78.0314 |
| keepitreal/vietnamese-sbert                                   |   78.83 |   78.36 |   78.42 |   76.93 |   82.74 |   72.46 |       77.98 | 77.96   |
| openai/text-embedding-3-large                                 |   79.85 |   72.07 |   78.44 |   72.27 |   80.62 |   80.76 |       79.82 | 77.69   |
| intfloat/multilingual-e5-base                                 |   80.51 |   77.59 |   71.33 |   69.5  |   81.49 |   79.64 |       81.13 | 77.3129 |
| hiieu/halong_embedding                                        |   79.28 |   73.6  |   75.64 |   72.41 |   79.77 |   78.48 |       80.54 | 77.1029 |
| intfloat/multilingual-e5-large_pyvi_tokenizer                 |   81.23 |   77.89 |   69.95 |   69.15 |   81.08 |   79.51 |       78.34 | 76.7357 |
| intfloat/multilingual-e5-small                                |   78.62 |   79.74 |   68.93 |   68.98 |   81.18 |   78.08 |       80.05 | 76.5114 |
| openai/text-embedding-3-large_pyvi_tokenizer                  |   78.03 |   69.62 |   77.15 |   71.79 |   79.93 |   80.07 |       78.95 | 76.5057 |
| Alibaba-NLP/gte-multilingual-base_pyvi_tokenizer              |   78.18 |   75.81 |   71.04 |   70.24 |   82.71 |   74.13 |       78.09 | 75.7429 |
| BAAI/bge-m3_pyvi_tokenizer                                    |   78.14 |   74.67 |   69.1  |   68.39 |   82.43 |   78.62 |       78.3  | 75.6643 |
| BAAI/bge-m3-unsupervised                                      |   76.53 |   65.41 |   72.86 |   69.14 |   79.76 |   78.98 |       78.96 | 74.52   |
| intfloat/multilingual-e5-base_pyvi_tokenizer                  |   77.5  |   74.67 |   67.04 |   66.35 |   79.05 |   77.07 |       76.85 | 74.0757 |
| VoVanPhuc/sup-SimCSE-VietNamese-phobert-base                  |   75.84 |   77.54 |   71.38 |   70.98 |   77.85 |   72.03 |       72.56 | 74.0257 |
| hiieu/halong_embedding_pyvi_tokenizer                         |   75.67 |   67.08 |   71.08 |   68.29 |   78.55 |   75.04 |       77.3  | 73.2871 |
| jinaai/jina-embeddings-v3_retrieval                           |   73.85 |   66.9  |   75.77 |   70    |   79.83 |   72.21 |       70.76 | 72.76   |
| intfloat/multilingual-e5-small_pyvi_tokenizer                 |   75.39 |   74.77 |   64.74 |   65.61 |   78.25 |   75.33 |       74.69 | 72.6829 |
| BAAI/bge-m3-unsupervised_pyvi_tokenizer                       |   74.54 |   64.38 |   70.01 |   67.82 |   78.3  |   77.22 |       75.95 | 72.6029 |
| nampham1106/bkcare-embedding                                  |   74.2  |   69.67 |   69.07 |   67.85 |   74.72 |   71.72 |       74.53 | 71.68   |
| openai/text-embedding-3-small                                 |   72.19 |   62.91 |   69.72 |   66.63 |   76.68 |   75.75 |       72.02 | 70.8429 |
| VoVanPhuc/unsup-SimCSE-VietNamese-phobert-base_pyvi_tokenizer |   68.93 |   62.47 |   70.62 |   65.02 |   75.63 |   69.56 |       72.34 | 69.2243 |
| openai/text-embedding-3-small_pyvi_tokenizer                  |   70.44 |   61.39 |   66.09 |   63.85 |   76.25 |   74.77 |       71.61 | 69.2    |
| jinaai/jina-embeddings-v3_retrieval_pyvi_tokenizer            |   66.67 |   66.29 |   69.98 |   66.68 |   77.19 |   69.68 |       66.06 | 68.9357 |
| openai/text-embedding-ada-002                                 |   71.75 |   60.71 |   66.63 |   60.27 |   72.5  |   75.38 |       70.52 | 68.2514 |
| VoVanPhuc/unsup-SimCSE-VietNamese-phobert-base                |   65.86 |   58.5  |   68.85 |   64.69 |   73.23 |   68.11 |       69.47 | 66.9586 |
| openai/text-embedding-ada-002_pyvi_tokenizer                  |   69.6  |   57.42 |   64.01 |   57.81 |   71.41 |   74.16 |       69.75 | 66.3086 |
| BAAI/bge-m3-retromae                                          |   61.67 |   48.43 |   56.38 |   55.51 |   63.75 |   60.74 |       67.2  | 59.0971 |
| BAAI/bge-m3-retromae_pyvi_tokenizer                           |   58.45 |   47.23 |   46.57 |   49.63 |   53.59 |   55.25 |       61.83 | 53.2214 |
| Alibaba-NLP/gte-multilingual-mlm-base                         |   45.47 |   33.63 |   38.38 |   38.38 |   55.32 |   55.54 |       54.29 | 45.8586 |
| Alibaba-NLP/gte-multilingual-mlm-base_pyvi_tokenizer          |   48.5  |   36.14 |   35.83 |   40.65 |   50.13 |   54.91 |       53.89 | 45.7214 |

## How to run my code
- Just run all my jupyter notebook file
- Use can add more model

## Insight
From the results, we can see that:
- Pyvi improves the results of some models while decreasing the performance of others.
- For Jina v3, adding the parameter task = 'text-matching' significantly improves the results.
- The best-performing models are dangvantuan/vietnamese-embedding, dangvantuan/vietnamese-embedding-LongContext, jinaai/jina-embeddings-v3, Alibaba-NLP/gte-multilingual-base, and VoVanPhuc/sup-SimCSE-VietNamese-phobert-base.
- These datasets focus on the problem of text matching or text similarity (the more similar in meaning two sentences are, the more similar their embeddings are). Based on the results of Jina-v3 when using task = 'text-matching' and task = 'retrieval', it can be seen that this problem is different from retrieval:
    - Therefore, to evaluate results for the retrieval task, a different dataset that consists of questions and corresponding answers will be needed.
    - Depending on the target task—whether it's text matching (as in this dataset) or retrieval (used for RAG or QA models), you will need to prepare a different dataset and select different models, rather than using the same model for both tasks.
    - The results show that the open-source models perform significantly better than OpenAI embeddings on these datasets.