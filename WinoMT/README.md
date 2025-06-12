# WinoMTeus

WinoMTeus is a translated subset of [WinoMT](https://github.com/gabrielStanovsky/mt_gender) that consists of 1,000 sentences. The aim of this adaptation is to evaluate gender stereotypes that emerge when translating sentences involving professions from a genderless language like Basque into a gendered language such as Spanish. This repository also includes the glossary we used to translate the occupations from the original dataset in English in a consistent manner.

## Evaluation

We analyze gender bias by examining the distribution of job entities by gender in the translation outputs, which allows us to identify potential imbalances or tendencies in how models assign gender to professional roles.

1. **Extract entities**: Extract all nouns preceded by articles in the Spanish translation outputs.
2. **Filter occupations**: Manually remove entities that do not refer to occupations.
3. **Aggregate and normalize counts**: Unify entity variants that refer to the same profession and compute the number of times each normalized occupation appears in the masculine or feminine form across all model outputs. The results include: total number of masculine and feminine forms per occupation, overall count, the ratio of masculine and feminine translations for each profession.
4. **Extract highest masculine and feminine ratios:** Extract the top 20 occupations with the highest masculine and feminine ratios to generate focused summaries.
5. **Analyze gender bias per model**: For each translation model, compute and normalize gendered translation counts separately. Identify the top 10 occupations most frequently translated in the masculine and feminine forms, respectively.

Evaluating stereotypes in more detail is left for future work. This would involve examining labor statistics in the Basque Country or carrying out a large-scale survey to understand how Basque speakers perceive the occupations.

## Citation

If you use WinoMTeus in your work, please make sure to also cite the original WinoMT paper:

```bibtex
@misc{stanovsky2019evaluatinggenderbiasmachine,
      title={Evaluating Gender Bias in Machine Translation}, 
      author={Gabriel Stanovsky and Noah A. Smith and Luke Zettlemoyer},
      year={2019},
      eprint={1906.00591},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/1906.00591}, 
}
