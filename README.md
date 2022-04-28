# M-Phasis
This is the data repository for the LREC 2022 publication "Placing M-Phasis on the Plurality of Hate: A Feature-Based Corpus of Hate Online".
Before you download anything, **please note our license**, which:
- requires **attribution** (see bibtex below)
- does **not allow commercial use**
- **no sharing** of the uploaded material or derivatives thereof with others through means other than this Github repository

Please see our licence for full details.

The repository is structured as follows:
- annotations: original data and annotations.
- model_outputs: various test set predictions of the models presented in the paper.
- train_dev_test_splits: the train, development and test splits used in the experiment section of the paper.
- annotation_protocol.pdf: the annotation protocol used to annotate the dataset.

# Annotations
German (de) and French datasets under {de,fr}.data.csv.

The columns are the following:
- id: instance id to match data instance with respective annotations in {de,fr}.annotations.{articles,comments}.csv.
- content: the content of the instance. For articles this content is simply the URL pointing to the respective article.
- user_id: anonymised internal user (i.e., author) id.
- article_id: internal id of the article the comment is refering to. For articles this is empty.
- direct_parent_id: internal id of the direct instance (comment or article) the current comment is refering to. For articles this is empty.
- internal_id: internal id of current sample.
- outlet: name of news outlet.
- outlet2: internal numerical id of news outlet.
- type: type of instance (article, comment, reply).
- type2: internal numerical id of type (article=1, comment=2, reply=3).
- length: number of characters.
- words: number of words.

The respective annotations are found under {de,fr}.annotations.{articles,comments}.csv.

The columns are the following:
- id: instance id to match annotation with data instace in {de,fr}.data.csv.
- annotator: id of annotator.
- all others: please refer to the annotation protocol for a full explanation of all variables.

Many modules allow several iterations over a sample. In this case, the columns have added numberings to show which iteration is currently annotated. For example, c_ne allows the annotation of several negatively evaluated actors over several iterations. We therefore see columns such as c_ne_1_0 to c_ne_1_5, which are all annotations of question c_ne_1, but for 6 different negatively evaluated actors. The following c_ne_2_x is then the follow-up annotation to c_ne_1_x, and so forth. Please see the annotation protocol for more.

# Model Outputs
Each model output file contains one test instance per line. For each test instance, we give the model outputs over 10 randomly seeded runs, which are space separated.

# Train-Dev-Test Splits
The splits used for the experimental section have the following format:
- id: instance id.
- content: content of instance.
- e1-a3c: respective label per sub-task for the instance. 99 means this instance should not be used for the subtask.

# Annotation Protocol
If you use or adapt our annotation protocol in any way, please cite the authors as given on the first page of the annotation protocol PDF.

# Bibtex
If you use any of the data contained in this Github, please cite our paper:

```
@InProceedings{ruiter_reiners:2022:LREC,
  author    = {Ruiter, Dana  and  Reiners, Liane and Geet D'Sa, Ashwin and Kleinbauer, Thomas and Fohr, Dominique and Illina, Irina and Klakow, Dietrich and Schemer, Christian and Monnier, Angeliki},
  title     = {Placing M-Phasis on the Plurality of Hate: A Feature-Based Corpus of Hate Online},
  booktitle      = {Proceedings of The 14th Language Resources and Evaluation Conference},
  month          = {June},
  year           = {2022},
  address        = {Marseille, France},
  publisher      = {European Language Resources Association}
}
```

