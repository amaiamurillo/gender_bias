# FLORES+
Based on [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/spa_Latn/devtest), we have created a new version to evaluate whether the quality of the translation is affected by the predominant grammatical gender of the source sentence when translating from a gendered language (Spanish) into a genderless language (Basque). For this purpose, we divide the original dataset into two separate files: **Flores_ES_M.txt**, containing all the sentences of the dataset in masculine form, and **Flores_ES_F.txt**, containing the same sentences in feminine form. 

## Data Structure
Each file consists of 359 annotated sentences and is structured as follows:

* **Sentence.** The sentence in the gender of the file to which it belongs.
* **Treatment.** It indicates whether the sentence is in its original form or has been modified to reflect gender:
  - **O**: Original
  - **M**: Modified
* **Multi-entity.** This column specifies whether the sentence contains more than one gendered entity:
  - **0**: Not multi-entity
  - **1**: Multi-entity
* **Proper names.** This column is used to indicate whether the gendered entity that was modified is a personal name:
  - **0**: Not proper name
  - **1**: Proper name
* **Sensitive names.** It specifies whether the proper name is sensitive to modify due to public recognition:
  - **0**: Not sensitive
  - **1**: Sensitive
* **Unmarked masculine.** It indicates whether the masculine form used is unmarked.
  - **0**: Gender is explicitly marked
  - **1**: Masculine form is unmarked or generic
* **Sensitive instances.** In this column, we indicate whether the instance is problematic or sensitive:
  - **0**: No issue
  - **1**: Sensitive
  - **2**: Highly sensitive
 
## Evaluation

For the evaluation, we recommend using [SacreBLEU](https://github.com/mjpost/sacrebleu), a standardized and widely-used library for machine translation evaluation.

The following command evaluates system outputs against a reference file using multiple metrics:

```bash
python3 -m sacrebleu -m bleu chrf ter --chrf-word-order 2 --ter-case-sensitive --ter-normalized --score-only {REFERENCE} < {TRANSLATION}```


## Citation

If you use this dataset in your work, please make sure to also cite the original FLORES-200 paper, since FLORES+ is based on it:

```bibtex
@article{nllb-24,
    author="{NLLB Team} and Costa-juss{\`a}, Marta R. and Cross, James and {\c{C}}elebi, Onur and Elbayad, Maha and Heafield, Kenneth and Heffernan, Kevin and Kalbassi, Elahe and Lam, Janice and Licht, Daniel and Maillard, Jean and Sun, Anna and Wang, Skyler and Wenzek, Guillaume and Youngblood, Al and Akula, Bapi and Barrault, Loic and Gonzalez, Gabriel Mejia and Hansanti, Prangthip and Hoffman, John and Jarrett, Semarley and Sadagopan, Kaushik Ram and Rowe, Dirk and Spruit, Shannon and Tran, Chau and Andrews, Pierre and Ayan, Necip Fazil and Bhosale, Shruti and Edunov, Sergey and Fan, Angela and Gao, Cynthia and Goswami, Vedanuj and Guzm{\'a}n, Francisco and Koehn, Philipp and Mourachko, Alexandre and Ropers, Christophe and Saleem, Safiyyah and Schwenk, Holger and Wang, Jeff",
    title="Scaling neural machine translation to 200 languages",
    journal="Nature",
    year="2024",
    volume="630",
    number="8018",
    pages="841--846",
    issn="1476-4687",
    doi="10.1038/s41586-024-07335-x",
    url="https://doi.org/10.1038/s41586-024-07335-x"
}
