# A deep learning relation extraction approach to support a biomedical semi-automatic curation task
****

**Background**. Discover relevant biomedical interactions in the literature is crucial for enhancing biology research. It has an essential role in studying the different processes and interactions reported that affect the biological process (e.g., genome, metabolome, and transcriptome). Therefore, the objective of this work is twofold: reduce the manual effort required to curate and review the existing biochemical interactions reported in the gluten-related bibliome while proposing a novel relation extraction deep learning approach that assists in a real curation task by learning from the previous decisions of the curators.

**Methods**. Compared to previous works, the main contribution of this work lies in proposing a deep learning model that incorporates a novel vector-space that combine (_i_) high-level lexical and syntactic inference features as Wordnets and Health-related domain ontologies, (_ii_) unsupervised domain syntactic and semantic resources as word embeddings, (_iii_) semantical and sentence structure knowledge (e.g., part of speech, negation information, verb information), (_iv_) abbreviation resolution support, (_v_) several state-of-the-art Named-entity recognition methods, and (_vi_) different feature construction and optimization techniques to support a semi-automatic curation workflow.

**Results**.The application of the semi-automatic curation workflow over a classified set of 2,451 relevant gluten-related documents produces a total of 8,349 relevant relations and 471,813 irrelevant relations of the next relation categories: (_i_) Related health issue, (_ii_) Improve, (_iii_) Aggravate, (_iv_) Stimulation, (_v_) Inhibition, (_vi_) Activation, (_vii_) Deactivation, (_viii_) Downregulation, (_ix_) Upregulation, (_x_) increase symptoms, (_xi_) decrease symptoms, (_xii_) weak relation and (_xiii_) no effect. Therefore, the mean achieved F-score for the different relation categories established was 0.731, with the lowest F.score at 0.47 (with 200 positive identified relations) and the highest F.score at 0.929 (with 2,129 positive identified relations).

Experimental results showed that the presented workflow is an excellent approach for a semi-automatic RE task. It was able to obtain satisfactory results in the early stages of a real-world curation task and saved manual annotation efforts by learning from the decisions made by manual curators. On the other hand, the presented sentence vector-space can be integrated into several state-of-the-art machine learning models to recognize relevant relations with satisfactory results. Finally, this work highlights the benefit of use domain knowledge as ontologies and entity recognizers to improve the automatic recognition of health-related interactions in the literature.


## Data Folder
****
- **AbbreviationDictionary_domain**: Contains the abbreviation resolution rules
- **englishCommonStopWords**: A simple list of common stop words used to annotate the sentences
- **lexicon**: The full parsed lexicon used to discover relevant entities, and the normalized identified words
- **relation_rulesV10.json**: Relation probabilities taking into account the possible entities that interact
- **relationDatasetBaseline**: Curated relation dataset. Identified negative and positive sentences that contains (or not) a possible relevant interaction
- **relationDataset**: Pre-processed curated relation dataset before applying the proposed vector-space construction techniques. 
  (contains the sentence text, the recognized annotations by the different named entity recognisers, the verb information, the PoS information... in order to avoid the use of third parties libraries as Dnorm,LINNAEUS, Stanford CoreNLP, etc to process the baseline sentence dataset)
- **stopWords**: A curated list of the task stop words
- **word2vec_MyDictionary**: TSV serialization of the Word2Vec space used to normalize the sentences

## Code
****
This folder contains the workflow and the code blocks implemented in the Rapidminer tool as an example to carried out the explained steps proposed.

- Sentence processing
- Vector-space transformation (One hot encoding, Normalisation, etc)
- Feature selection
- Deep learning construction (use the H2O library https://docs.rapidminer.com/latest/studio/operators/modeling/predictive/neural_nets/deep_learning.html)
- Deep learning layer grid search
- Deep learning L1 and dropout optimization
- Deep learning cross Validation evaluation


## Other  files with each own site and own license required to process the relationDataset.tsv
- WordNet: https://wordnet.princeton.edu/
