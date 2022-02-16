# HURTS

### Corpus
The corpus used here is from Elsevier, consisting of sentences from a total of 75M English language articles. The entire corpus is seperated into 84 files, but only 3 are used, which has about 100M sentences each.

### Method
I used the same disease names (extracted from Fig 2 in the manuscript), replaced these diseases with single words (e.g. ‘hearing loss’ -> ‘hearing_loss’ so that the embedding will recognize it as a single word) in the corpus. After the embedding with Word2Vec, I got the cosine similarity between the diseases with the words that indicating the disease suffering including: 'death', 'severe', 'pain', 'suffer' and 'ache', ranked from high (5) to low (1).

The averaged scores are calculated for each disease, as the weighted average of the cosine similarity between the specific disease and the 5 words. 

$$score = \sum(similarity_i * score_i)/\sum(similarity_i)$$

where $score_i$ is the score of the $ith$ word with value 1-5, and $similarity_i$ is the cosine similarity between the specific disease and the $ith$ word.

Three corpus are used, and three random seeds are appllied for each corpus, to get an idea on how stable the results are.
