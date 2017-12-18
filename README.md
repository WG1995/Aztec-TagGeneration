# Aztec-TagGeneration

## The second largest heading
Data
data/PaperSet: all the 4953 PubMed paper
ProcessedNew: all the processed 4953 PubMed paper, all lowercased with space removed between capital letters in the original paper
parsed_0.8: output of segphrase parsing with parameter 0.8, all frequent phrases are connected with "_"

## The second largest heading
Source Code:

Doc2Vec.py: Read in processed and combined 4953 PubMed paper file, build and train a doc2vec model with dimension specified in the parameters

