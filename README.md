# Aztec-TagGeneration

## Running Steps:
1. Use modified SegPhrase code to generate parsed file with high frequency phrases. All the parsed results are stored in Data/parsed in this repo.
To Generate the parsed results, run with: ./parse.sh
2. Combine all the parsed files to a single file, feed file to Doc2Vec.py.It will generate doc2vec models with specified word embedding dimension. Run with python Doc2Vec.py.
3. doc2Vec_visual.py produces a single file contains all the significant phrases for each of the parsed file using a trained Doc2Vec model with specified wording embedding dimension.

## Data

data/PaperSet: all the 4953 PubMed paper <br />
ProcessedNew: all the processed 4953 PubMed paper, all lowercased with space removed between capital letters in the original paper <br />
parsed_0.8: output of segphrase parsing with parameter 0.8, all frequent phrases are connected with "_" <br />
parsed: output of segphrase parsing with default parameter 0.6, all frequent phrases are connected with "_" <br />
## Source Code

Doc2Vec.py: Read in processed and combined 4953 PubMed paper file, build and train a doc2vec model with dimension specified in the parameters <br />

dumpFiles.py: Extract all 4953 paper from a single file Output2.txt. These files have better format and less syntax errors. The extracted paper are further processed to train the doc2vec model. All the processed files are stored in /ProcessedNew <br />

insertSpace.py: Insert space between capital letters in the original papers then changed all these paper to lowercase for SegPhrase training purpose.

doc2vec_visual.py: dump the results of most significant words trained on the doc2vec model to results.txt. Usage: python doc2vec_visual.py [model dimension] [file range]

## Modified SegPhrase
[SegPhrase](https://github.com/shangjingbo1226/SegPhrase) is git cloned from the original author. The source code are modified for the purpose of the current task. <br />

src/online_query/segphrase_parser.cpp: the original code uses [] to indicate frequent phrases. Changed to "_" to connect phrase as a single word for the doc2vec training purpose.    <br />

These modified code and results are uploaded in the [google drive](https://drive.google.com/drive/folders/109w9CKtA0UbFscERUzMdQAQw7WW_Ckoz?usp=sharing). <br />
## Models

Doc2Vec trained models with word embedding dimension 50, 100 and 400 are uploaded in the [google drive](https://drive.google.com/drive/folders/109w9CKtA0UbFscERUzMdQAQw7WW_Ckoz?usp=sharing). <br /> 

##Results
data/results.txt: contains paper with corresponding significant word trained on the doc2vec model with specified word embedding dimension <br />

