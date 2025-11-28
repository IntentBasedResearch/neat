# IMPORTANT INFORMATION

Original project available at https://gitlab.imt-atlantique.fr/sotern-public/neat

# A Nile-English Aligned Translation dataset

This repository contains a synthetically generated dataset to train a Natural Language translator model from or into [Nile] statements for Intent-based Networks ([IBN]) systems. The intents are expressed using the Nile syntax, and the natural language translation are written in English.
This dataset is composed of 256913 lines with tab separated components in the format:
```
Nile: <A Nile statement> <tab> Text: "<The corresponding english translation>"
```

## Dataset usage examples
The tab separation was intended to make it convenient to use:
```bash
# extract all Nile intents
cut -f1 -d$'\t' NEAT.txt
# extract all English intents
cut -f2 -d$'\t' NEAT.txt
# separate into train/validation/test datasets (80%=205530)
sort -R NEAT.txt > _tmp.txt
head -n 205530 _tmp.txt > train.txt
head -n 231221 _tmp.txt | tail -n 25691 > validation.txt
tail -n 25692 _tmp.txt > test.txt
```


[IBN]:https://datatracker.ietf.org/doc/rfc9315/
[Nile]:https://dl.acm.org/doi/10.1145/3229584.3229590

## Citation
The methodology and the dataset were published in:
```
@article{MUNSON2025,
  title = {NEAT: A Nile-English Aligned Translation corpus based on a robust methodology for Intent Based Networking},
  journal = {Computer Networks},
  volume = {271},
  pages = {111519},
  year = {2025},
  issn = {1389-1286},
  doi = {https://doi.org/10.1016/j.comnet.2025.111519},
  url = {https://www.sciencedirect.com/science/article/pii/S1389128625004864},
  author = {Daisy Munson and Pierre Alain and Guillaume Doyen},
}
```
