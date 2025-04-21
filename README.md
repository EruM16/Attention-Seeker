# Attention-Seeker

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/attention-seeker-dynamic-self-attention/keyphrase-extraction-on-inspec)](https://paperswithcode.com/sota/keyphrase-extraction-on-inspec?p=attention-seeker-dynamic-self-attention)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/attention-seeker-dynamic-self-attention/keyphrase-extraction-on-krapivin)](https://paperswithcode.com/sota/keyphrase-extraction-on-krapivin?p=attention-seeker-dynamic-self-attention)

The present repository is for the paper: "Attention-Seeker: Dynamic Self-Attention Socring for Unsupervised Keyphrase Extraction"

The code to replicate the results of the paper is organized into seven notebooks. 
The first two notebooks cover the main experiments, the next two address the ablation study, and the remaining notebooks correspond to the appendices.

## Environment Setup

To run these notebooks, ensure your environment includes the following libraries:

- pandas 2.2.1
- numpy 1.24.3
- pytorch 2.3.0
- nltk 3.8.1
- transformers 4.38.2
- huggingface_hub 0.23.1
- tqdm 4.66.4


## Conda Environment Setup (Optional)

If you are using Anaconda on Windows, you can create the required environment using the provided "att_seek_env.yml" file:
```
conda env create -f att_seek_env.yml
```

## Standford CoreNLP Setup:

Additionally, you will need to run the Standford CoreNLP tool on your terminal:

0. Download the folder [stanford-corenlp-full-2018-02-27](https://drive.google.com/file/d/1JDwxS6Bm2lxOJJPtycQxtqZagTVgj9RU/view?usp=sharing) and place it in the main folder of Attention-Seeker (same level as the notebooks).

1. Ensure Java is installed:
Check if Java is installed by running:
```
java --version
```
2. Navigate to the Standford CoreNLP directory:
```
cd stanford-corenlp-full-2018-02-27/
```
3. Check available ports:
Ensure that the port you plan to use is available (you can replace 9000 with another port number if needed):
```
netstat -ano | findstr :9000
```
4. Run Standford CoreNLP:
Start the Standford CoreNLP server on an available port (Replace 9000 with your available port number):
```    
java -mx4g -cp "*" edu.stanford.nlp.pipeline.StanfordCoreNLPServer -preload tokenize,ssplit,pos -status_port 9000 -port 9000 -timeout 15000
```

## Running the Notebooks
Before running the notebook of your choice, make sure to activate the created environment and ensure that you modify the port number in the second line of the second cell to match the port used by Standard CoreNLP:
```
host = 'localhost'
port = 9000      <--- Modify
pos_tagger = PosTaggingCoreNLP(host, port)
```
