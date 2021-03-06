SimpleQuestions dataset mapped into Wikidata and DBpedia
==========================

This repository provides a version of the [SimpleQuestions](https://research.fb.com/downloads/babi/) dataset mapped to Wikidata.

Data is organized in 3 files: `annotated_wd_data_{train, valid, test}.txt` .
Each file contains one example per line with the following format:
`subject [tab] property [tab] object [tab] question`, with `subject`, `property` and `object` being identifiers of Wikidata items or properties.
`Rxxx` property identifiers encode the inverse property of the Wikidata property `Pxxx`. For example `R19` encodes the properties "born here", i.e. the inverse of `P19` ("birth place").

The mapping code is in the `build.ipynb` file. The mapping of Freebase topics to Wikidata items is done using the `mid_to_qid.tsv` file and the one between properties is the one [stored on Wikidata](https://www.wikidata.org/wiki/Wikidata:WikiProject_Freebase/Mapping). Contributions to these mappings are welcome.

* `annotated_wd_data_train.txt` contains 34374 questions converted from the 75910 original questions.
* `annotated_wd_data_test.txt` contains 9961 questions converted from the 21687 original questions.
* `annotated_wd_data_valid.txt` contains 4867 questions converted from the 10845 original questions.

Converting from Wikidata to DBpedia (it's converted using owl:SameAs, owl:equivalentClass, owl:equivalentProperty properties)

Each file contains one example per line with the following format:
`answerEntity [tab] property [tab] questionEntity [tab] question`, with `answerEntity`, `property` and `questionEntity` being identifiers of DBpedia items or properties.
`answerEntity` is a expected URI, `questionEntity` is the URI mentioned in the question.

* `annotated_db_data_train.txt` contains 24138 questions converted from the 75910 original questions.
* `annotated_db_data_test.txt` contains 7006 questions converted from the 21687 original questions.
* `annotated_db_data_valid.txt` contains 3402 questions converted from the 10845 original questions.
