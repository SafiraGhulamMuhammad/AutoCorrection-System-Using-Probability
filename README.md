# AutoCorrection-System-Using-Probability

This project involves developing an autocorrection system that utilizes probabilities to identify and correct typos in text. The core idea is to find the most likely correction for a misspelled word based on a probabilistic model and minimum edit distance calculations.

## Overview

The autocorrection system works by:
1. Identifying misspelled words.
2. Generating possible corrections by finding strings within a certain edit distance.
3. Filtering these candidates to retain only valid words.
4. Selecting the most probable correction based on word frequency in the context.

### Example

For instance, given the input "Happy birthday deah friend", the system will correct it to "Happy birthday dear friend". However, if the input is "Happy birthday deer friend", it won't make any changes, since "deer" is a correctly spelled word, even though it may not fit the context perfectly.

## Steps in the Autocorrection Process

### 1. Identify Misspelled Words

To identify misspelled words, the system checks each word against a vocabulary list of known correct words. If a word is not found in the vocabulary, it is flagged as a potential typo.

### 2. Generate Possible Edits

For each misspelled word, the system generates all possible edits that are within a certain edit distance. The edit distance operations include:
- **Insert:** Adding a letter.
- **Delete:** Removing a letter.
- **Switch:** Swapping two adjacent letters.
- **Replace:** Changing one letter to another.

### 3. Filter Candidates

The system filters the generated candidates, keeping only those that are valid words in the vocabulary.

### 4. Calculate Word Probability

Among the valid candidates, the system calculates the probability of each word occurring in the given context. The candidate with the highest probability is selected as the correction.

### Minimum Edit Distance

To determine the similarity between two strings, the system uses the minimum edit distance algorithm. This algorithm computes the minimum number of operations required to transform one string into another. The operations and their respective costs are:
- **Insert:** Cost 1
- **Delete:** Cost 1
- **Replace:** Cost 2

#### Example Calculation

To change the word "play" to "stay":
1. Delete 'p' (cost 1)
2. Insert 's' (cost 1)
3. Delete 'l' (cost 1)
4. Insert 't' (cost 1)

Total cost: 4

### Dynamic Programming Approach

Using dynamic programming, the system computes the minimum edit distance efficiently, even for large datasets. The algorithm uses a tabular form to store intermediate results, reducing computational complexity.

## Conclusion

This autocorrection system combines probabilistic modeling with dynamic programming to accurately and efficiently correct misspelled words. By leveraging minimum edit distance and word probability, it provides a robust solution for text correction tasks.
