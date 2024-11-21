# Readability Assessment

## Project Presentation

The goal of this project is the development of a method using Artificial Intelligence to assess the language difficulty of a text (or readability assessment).

Readability assessment is a process used to evaluate the ease with which a reader can understand a written text. Two approaches have been developed over the years: statistical approach with readability formulae and Natural Language Processing (NLP) approach notably with a transformer-based solution. Recently a third approach combining the 2 other approaches emerged:  NLP with statistical features or hand-crafted features. This new approach was quite successful. 

We decided to use the last approach combining NLP with hand-crafted features. We used a BERT model and 3 statistical features which can be extracted from text from any language. Our hand-craft features are: 
- The sentence length
- Average of noun per phrase
- the mean height of the dependency tree.

To evaluate the performance of our model and have results comparable with our peers, we use the k-folds cross-validation technique.

this work follows on from \[10]

## Datasets Presentation

For this project, we used 2 datasets: One Stop English \[11] and Vikiwiki \[9]. One Stop English is a compilation of text produced by the onestop english association. It contains texts only in English but those are divided into 3 difficulties: Beginner, Intermediate and Advanced. Vikiwiki \[9] is a dataset containing texts in 6 languages: Basque, Catalan, English, French, Italian and Spanish divided in 2 difficulties: beginner and advanced. The table below summarises the characteristics of our datasets:

![image](https://github.com/user-attachments/assets/1f534a00-5191-437f-9b03-ffa110768504)

This table shows that the different classes representing the level of difficulty of the text are balanced in the 2 datasets. So we won't need to re-balance it using Oversampling or Undersampling.

## Our Approach

The statistical features in readability formulae showed pretty good results but the features are handcrafted thus are linked to a language or a subset of languages. NLP could extract important information from text. We decided to take the best of the 2 worlds:  using NLP with handcrafted statistical features. We choose to use the BERT (Bidirectional Encoder Representations from Transformers)  model with different features such as the mean sentence length, the average depth of the dependency tree and the average of noun phrases.

To add those features, the hypothesis was that difficult text may consist of more complex sentences. For the mean sentence length feature, we consider the complexity of a sentence tends to be higher with the sentence’s length. For the average depth of the dependency tree feature, we consider the complexity of a sentence tends to be higher with the complexity of the sentence syntactic structure. For the average of noun phrases we consider that the complexity of a sentence tends to be higher with the number of noun phrases.

# References

\[1] Azpiazu, I. M., & Pera, M. S. (2019). Multiattentive recurrent neural network architecture for multilingual readability assessment. Transactions of the Association for Computational Linguistics, 7, 421-436. 

\[2] Bengoetxea, K., & Gonzalez-Dios, I. (2021). MultiAzterTest: a Multilingual Analyzer on Multiple Levels of Language for Readability Assessment. arXiv preprint arXiv:2109.04870. 

\[3] Ding, Han & Zhong, Qiyu & Zhang, Shaohong & Yang, Liu. (2022). Text Difficulty Classification by Combining Machine Learning and Language Features. 10.1007/978-3-030-89698-0_108.

\[4] Dale, Edgar, and Ralph W. Tyler. “A Study of the Factors Influencing the Difficulty of Reading Materials for Adults of Limited Reading Ability.” The Library Quarterly: Information, Community, Policy, vol. 4, no. 3, 1934, pp. 384–412. 

\[5] Flesch, R. (1948). A Readability Formula in Practice. Elementary English, 25(6), 344–351. 

\[6] Jacob Devlin, Ming-Wei Chang, Kenton Lee, and Kristina Toutanova. 2019. BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding. In Proceedings of the 2019 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies, Volume 1 (Long and Short Papers), pages 4171–4186, Minneapolis, Minnesota. Association for Computational Linguistics. 

\[7] Lively, Bertha A. and Pressey S.L. 1923. A method for measuring the 'vocabulary burden' of textbooks. Educational administration and supervision. 9:389–398. 

\[8] Vogel, Mabel, and Carleton Washburne. “A Year of Winnetka Research.” The Journal of Educational Research, vol. 17, no. 2, 1928, pp. 90–101. 

\[9] Github, VikiWiki, https://github.com/ionmadrazo/VikiWiki
 
\[10] Github, https://github.com/Kostrykina18/Readability_Assessment

\[11] Hugging Face, onestop_engish,  https://huggingface.co/datasets/onestop_english

\[12] Inria, Wimmics,  https://www.inria.fr/fr/wimmics 
