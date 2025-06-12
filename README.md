# Datasets for gender bias evaluation in Basque
We propose two datasets to evaluate gender bias in machine translation involving Basque. These have been designed to analyze how gender is handled when translating between Basque and gendered languages such as Spanish. 

**WinoMTeus** is a Basque adaptation of the [WinoMT](https://github.com/gabrielStanovsky/mt_gender) dataset, created by [Stanovsky et al. (2019)](https://arxiv.org/abs/1906.00591). It is designed to test whether translations from Basque to Spanish result in stereotypical gender assignments in the target language. 

We also extend [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/spa_Latn/devtest) with two gendered versions in Spanish: one with feminine referents and the other with masculine referents. The objective of this dataset is to evaluate whether the translation quality varies when translating into Basque depending on the gender of the referents in the Spanish text, following the approach proposed in [Multilingual HolisticBias](https://aclanthology.org/2023.emnlp-main.874/) by Costa-jussà et al. (2023).
