 1. Text Processing Rules (Pre-Processing Rules)

These rules are applied before storing or comparing text.

1. Lowercase Conversion Rule

All characters in the text should be converted to lowercase to ensure uniform comparison and avoid case-sensitive mismatches.

2. Number Removal Rule

All numeric values should be removed if they are not relevant to text meaning. This prevents numbers from affecting similarity scores.

3. Punctuation Removal Rule

Special characters and punctuation marks should be removed to standardize text format.

4. Minimum Word Length Rule

Words shorter than a specified length (e.g., less than 3 characters) should be removed to eliminate noise and irrelevant tokens.

5. Stopword Removal Rule

Common words (such as “the”, “is”, “and”, “to”) should be removed because they do not add meaningful value to text comparison.

6. Whitespace Normalization Rule

Extra spaces, tabs, and line breaks should be removed to maintain consistent formatting.

7. URL and Email Removal Rule

Web links and email addresses should be removed to avoid irrelevant content in similarity analysis.

8. Duplicate Text Detection Rule

If identical raw text already exists in the database, it should not be processed again.

9. Maximum Text Length Rule

Very long text entries can be truncated to a predefined length to improve performance in multiprocessing.

 2. Comparison Rules (Similarity Rules)

These rules control how texts are compared.

1. Case-Insensitive Comparison Rule

Text comparison should ignore letter casing differences.

2. Preprocessed Text Comparison Rule

Only cleaned text (after applying processing rules) should be used for similarity calculation.

3. Minimum Similarity Threshold Rule

Two texts are considered similar only if their similarity score is above a predefined threshold (e.g., 0.65 or 65%).

4. Self-Comparison Avoidance Rule

A text should not be compared with itself.

5. Pairwise Unique Comparison Rule

Each pair of texts should be compared only once to avoid redundant computations.

6. Database Integrity Rule

Comparison results should reference valid text IDs stored in SQLite to maintain relational consistency.

 3. Multiprocessing Rules

These rules ensure efficient parallel execution.

1. Chunk Division Rule

Text data should be divided into equal chunks before being distributed to worker processes.

2. Independent Worker Rule

Each process should handle its own chunk independently to avoid shared memory conflicts.

3. Safe Database Update Rule

Database updates should occur only after multiprocessing completes, preventing SQLite write conflicts.

4. Resource Limitation Rule

The number of worker processes should not exceed available CPU cores to avoid system overload.
