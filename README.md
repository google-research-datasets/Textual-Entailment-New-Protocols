Textual Entailment: New Protocols
===================================

This data release is meant to accompany and document the paper:

https://arxiv.org/abs/2004.11997 \
**Collecting Entailment Data for Pretraining: New Protocols and Negative Results** \
by Samuel R. Bowman, Jennimaria Palomaki, Livio Baldini Soares, and Emily Pitler

The `data/` directory contains the five datasets described in the paper: `base`, `paragraph`, `edit_premise`,
`edit_other` and `contrast`.

Each of the five datasets is split into a training set of 8,500 examples and a
validation set containing the remaining collected examples (with an exact size
varying across the five). Each dataset is distributed in three formats, with the
intention that you should be able to load the dataset with any code that is
capable of loading MNLI:

- A .tsv file containing tab-separated values using column names and column
  order that match the GLUE Benchmark's integer-indexed version of MNLI.

- A .txt file containing tab-separated values using column names and column
  order that match the .txt version of the original MNLI 1.0 data release.

- A .jsonl file containing JSON-formatted examples using field names that follow
  the .jsonl version of the original MNLI 1.0 data release.


Unlike the original MNLI data release, we do not distribute a syntactically-parsed version
of this data. This results in many blank columns in the .tsv and .txt files.

The .jsonl versions of each dataset contain two fields not found in the original MNLI data release:

- sentence1_source: The Wikipedia page ID, page title, and URL for the page from
  which the corresponding sentence1 was extracted. Text was were extracted from
  the 2019-06-20 'dump' of English Wikipedia.

- sentence2_author: An anonymized identifier for the annotator who composed the
  corresponding sentence2. These are assigned consistently across files, so
  annotator "bpbp02" in base/train.jsonl is the same person as annotator
  "bpbp02" in paragraph/val.jsonl.


All of the input data for this task comes from Wikipedia, which is licensed for
public use by the Creative Commons Attribution-ShareAlike 3.0 Unported License
(CC BY-SA) and the GNU Free Documentation License (GFDL).

## Citation

```bibtex
@inproceedings{Bowman2020EntailmentNewProtocols,
  title={Collecting Entailment Data for Pretraining: New Protocols and Negative Results},
  author={Samuel R. Bowman and Jennimaria Palomaki and Livio Baldini Soares and Emily Pitler},
  year={2020},
  booktitle={Proceedings of EMNLP}
}
```

## Experiments

Instructions for reproducing the experiments reported in the paper are available here:

https://github.com/nyu-mll/jiant/tree/nli-data
