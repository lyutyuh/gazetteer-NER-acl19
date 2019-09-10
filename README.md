# Soft Dictionary enhanced NER model
## Towards Improving Neural Named Entity Recognition with Gazetteers
https://www.aclweb.org/anthology/P19-1524

## Overall architecture
<img src="fig/architecture.png" width="400">

## Installation

First of all:
```bash
   git clone https://github.com/lyutyuh/acl19_subtagger.git ; cd acl19_subtagger
```

1. Create a virtual environment with Conda
```bash
    conda create -n softdict --file requirements_conda.txt -c conda-forge/label/broken -c conda-forge
```

2. Activate the new environment
```bash
    conda activate softdict
```

3. Install the pip requirements
```bash
    pip install -r requirements_pip.txt
```

4. Prepare the configurations
```bash
    sed -i 's@INSTALLATION_DIR@'"$PWD"'@' configs/*.config
```

## Training

```bash
    allennlp train configs/HSCRF_softDictionary.conll2003.config -s dump_directory/ --include-package models 
```

## Evaluating

```bash
    allennlp evaluate dump_directory/model.tar.gz https://www.jeffliu.page/files/DATA/conll2003/test.txt --include-package models    
```

## The Gazetteer
A pretrained subtagger module can be found at https://www.jeffliu.page/files/state.th

The gazetteer from [*Design challenges and misconceptions in named entity recognition*](https://www.aclweb.org/anthology/W09-1119) which we use can be found at "https://www.jeffliu.page/files/gazetteers_UIUC.zip"

The cleaned and mapped gazetteer to train our subtagger can be found at "https://www.jeffliu.page/files/softdict.zip"
