# TARS vs Flair models for Low Resource Languages in NER tagging
This work is an overview of the possibilities of using TARS models for low language resources. The report and the notebook are available in this repository. 

In this study, our objective is to evaluate the performance of TARS models (Task Aware Representation of Sentences) with zero-shot classification in comparison to Flair-Embeddings, specifically in scenarios where data scarcity is a concern. We conduct extensive evaluations of these models in different languages, including Spanish, German, Japanese, and Basque, in order to assess their efficacy across languages with varying degrees of resource availability.

The overarching methodology involved multiple steps. Initially, we examined the performance of TARS models with Zero-Shot Classification. Subsequently, we trained the models with language-specific datasets, and finally, we evaluated the models using the same datasets to facilitate a comparative analysis of the results.

For our different approaches, we utilized the same datasets to enable accurate result comparison. Each language was associated with a specific dataset, which may not necessarily belong to the same domain: 'CONLL 03' for Spanish, ’CoNLL-03 Biodiversity literature NER’ for German, ’NER BASQUE’ for Basque and ’IOB2 Corpus’ for Japanese. 

# Conclusions
Zero-shot classification is not effective for languages other than English, especially for low-resource languages. The system struggles to accurately interpret named entities in non-IndoEuropean languages like Basque and Japanese. 

Combining TARS with Flair embeddings improves the performance of the models, yielding results that are closer to those of Flair. However, using only TARS without embeddings is not viable, as the F-score average was very low (below 0.1). Therefore, the combination of TARS and Flair embeddings seems to be suitable, especially when dealing with datasets from low-resource languages. However, it is necessary to keep in mind that, although mixing the models improves the performance of TARS, actually, when combining the labels of the corpus with the newly defined ones, the system has to find the labels within that mix, which is a disadvantage.

Based on the comparison, if TARS is to be used for training, it is recommended to combine it with Flair embeddings to achieve better performance. Additionally, TARS shows relatively good results for small datasets, making it a potential method for low-resource languages when there is a lack of sufficient data.
