# Soft Dictionary enhanced NER model
## Towards Improving Neural Named Entity Recognition with Gazetteers
https://www.aclweb.org/anthology/P19-1524

## Overall architecture
<img src="fig/architecture.png" width="400">

## Installation

1. Create a virtual environment with Conda

```bash
    conda create -n softdict --file requirements_conda.txt
```

2. Activate the new environment

```bash
    source activate softdict
```

3. Install the pip requirements

```bash
    pip install -r requirements_pip.txt
```

## Training

```bash
    allennlp train configs/HSCRF_softDictionary.conll2003.config -s dump_directory/ --include-package models
    
```