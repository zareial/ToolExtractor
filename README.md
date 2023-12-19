<!-- WEASEL: AUTO-GENERATED DOCS START (do not remove) -->

# ToolExtractor

This repository hosts the dataset and complete source code for ToolExtractor project. The project structure and README file is based on the [Weasel](https://github.com/explosion/weasel) and [Spacy](https://github.com/explosion/weasel) documentations.

## ⚙️ Project Configuration

All details incl. assets, commands and workflows of the project and different configurations are available in the [`project.yml`](project.yml). Furhter details about Weasel are available at 
[Weasel documentation](https://github.com/explosion/weasel).


### 🗂 Assets

We included the following assets in the project. They can be listed via [`weasel assets`](https://github.com/explosion/weasel/tree/main/docs/cli.md#open_file_folder-assets).

| File | Source | Description |
| --- | --- | --- |
| `assets/corpus_full.jsonl` | [`URL`](https://owncloud.gwdg.de/index.php/s/3PftrgVgWJLaUr7) | A list of randomly selected sentences from PLOS in the topics of biology and social sciences (1,899,652 sentences).|
| [`assets/patterns.jsonl`](assets/patterns.jsonl) | Local | Full list of preprocessed software patterns extracted from TaPor, Wikidata and Softcite (11,948 phrases).|
| [`assets/tools_manual.jsonl`](assets/tools_manual.jsonl) | Local | The initial manual dataset annotated with `TOOL` (tool) entities (1000 accepted (relevant) examples). |
| [`assets/tools_corrections.jsonl`](assets/tools_corrected.jsonl) | Local | The full dataset including the extra examples corrected with `Prodigy ner.correct` (1614 accepted (relevant) examples). |
| `assets/tok2vec.bin` | [`URL`](https://owncloud.gwdg.de/index.php/s/CIMZR06J0vYXjcl) | Pretrained tok2vec weights on the full corpus to initialize the model. |

<!-- WEASEL: AUTO-GENERATED DOCS END (do not remove) -->

## 🧮 Results

| Model                                                                                                                         |   F-Score | Precision | Recall |
| ----------------------------------------------------------------------------------------------------------------------------- | --------: | --------: | -----: | 
| Transition Based Parser                                                                                       |     .89 |     .83 |  .86 | 
| Transition Based Parser with corrections                                                                                       |     .90 |     .88 |  .89 | 
| Transition Based Parser  + tok2vec<sup>1</sup>                                                                                       |     .86 |     .89 |  .84 | 
| Transition Based Parser with corrections  + tok2vec<sup>1</sup> | .92 |     .91 |  .92 | 
| Roberta Base Based Parser with corrections                                                                                       |    **.93** |     .94 |  .91 | 
| BiLSTM with corrections                                                                                       |     .85 |     .95 |  .79 | 
1. pretrained on gpu via
   [`spacy pretrain`](https://spacy.io/api/cli#pretrain) predicting the
   `en_vectors_web_lg` vectors (~5 hours on GPU).

