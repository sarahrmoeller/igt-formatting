# IGT Format Mapping

This repository contains examples of files in various formats that are used for language data, illustrating how the same data is formatted in various computational, archival, and fieldwork linguistics format/schemas. File formats are organized by directories. A directory contains one file for each language project/dataset and the other directories shows how that the information in that project/dataset would (or would not) appear in the other formats.  

# Why?
These mapped formats are meant to serve as a starting point for programmers looking to create converters between commonly used linguistic data formats. They can also be used by application designers to understand the structure of certain format schemas so they can add compatability between their programs and other linguistic softwares. Linguistic and computational knowledge is not assumed, but we do assume users are familiar underlying data models: XML, CSV/TSV, and plain text.

## What?
Primarily, this repository focuses on how various programs represent [interlinear glossed text](https://en.wikipedia.org/wiki/Interlinear_gloss) (IGT), particularly when morphological segmentation and glosses are included.

The table below shows the languages, the origin and format of the origina data sample, and which formats the sample has been reformatted into.

The examples of language data in this repository represent 2 categories: **Curated** (Cur.) and **Realistic** (Real.). **Curated** data tends to be much less extensive because we took very short examples from online curated databases to quickly and simplistically represent how the data can appear in a particular format. Since these tend to be curated and cleaned, small samples should be enough to illustrate their possibilities. **Realistic** data is significantly more extensive, usually provided by field linguists, containing all provided IGT data rather than a selected sample. The realistic samples are meant to illustrate typical linguistics project output, which tends to part of ongoing, dynamic work and therefore can be noisy with inconsistencies and typos. 

The `TAU`, `CHP`, and `BTZ` files serve as representative examples of realistic, low-resource documentary language data originating directly from linguistic fieldwork. The rest are from curated databases. 

The `Masters` directory contains examples of the data formats with all languages in one file. We split the individual languages into separate files to reflect typical treatment of different languages. We kept this folder for reference. 

The `FLEx` directory contains flextext XML exports which only contain IGT samples. This directory has a sub-directory which holds backup files of a full FLEx projects. We include the backups of the projects because not all information from other formats could be mapped to flextext XML files. The project shows where that information could be mapped to in a full FLEx database. 

# Data Models/Formats and Mapping
[Mapping_Guidelines.md](https://github.com/sarahrmoeller/igt-formatting/blob/main/MAPPING_GUIDELINES.md) explains the mapping in detail, including some arbitrary decisions we made, and why certain things may not appear in another format. 

## Data Formats used in Computational Linguistics / Natural Language Processing
* Universal Dependencies CoNLL-U (*.conllu*); [Schema](https://universaldependencies.org/format.html)
* Radboud University FoLiA (*.xml* OR *.folia*); [Website](https://proycon.github.io/folia/), [GitHub](https://github.com/proycon/folia)
## Data Formats intended for Archiving
* Cross-Linguistic Data Formats CLDF (*-CLDF.csv*); [GitHub](https://github.com/cldf/cldf), [Ontology](https://cldf.clld.org/v1.0/terms.rdf) (Download)
## Data Formats used by Specialized Linguistic Software 
* Max Planck Institute for Psycholinguistics's ELAN (*.eaf*) (XML)
* SIL Global's FieldWorks Language Explorer (FLEx), in three formats
	* Interlinear Texts (*.flextext*) (XML)
		* Represent, in XML, the structure of an interlinear glossed text, a method linguists use to break words into smaller units of meaning.
	* FLEx Project Files (*.fwbackup*, *.fwdata*)

|Type| Language (ISO-639-3)      | Source                                        | Source Original Format  | Converted Formats | Original Source File Name |
|:-------------:|:-------------:            |:-------------:                                |:-------------: | :---------------:| :------------------------:|
|Cur.| Akan (aka)                | [TypeCraft Akan Corpus 1.0]((https://typecraft.org/tc2wiki/TypeCraft_Akan_Data_Collection_Release_1.0)) via [CLDF Cookbook](https://github.com/cldf/cookbook)                | CLDF from TypeCraft| ELAN, FLEx, CLDF, CoNLL-U, FoLiA       |Release 1.0.zip |
|Cur.| Arabic (ara)              | [UD Arabic-PADT Treebank](http://hdl.handle.net/11234/1-6149)                       | CoNLL-U        | ELAN, FLEx, CLDF, CoNLL-U, FoLiA | ud-treebanks-v2.18.tgz|
|Real.| Batak Alas-Kluet (btz)          | [Andrew Brumleve](ajbrumleve.github.io)                               | FLEx           |                 ELAN, FLEx, CoNLL-U | btz-all_txts_ORIGINAL.flextext |
|Cur.| English (eng)             | [UD Georgetown University Multilayer Corpus (GUM)](http://hdl.handle.net/11234/1-6149) | CoNLL-U        | ELAN, FLEx, CLDF, CoNLL-U, FoLiA | ud-treebanks-v2.18.tgz|
|Cur.| Hindi (hin)               | [UD Hindi Treebank](http://hdl.handle.net/11234/1-6149)                             | CoNLL-U        | ELAN, FLEx, CLDF, CoNLL-U, FoLiA | ud-treebanks-v2.18.tgz|
|Cur.| Mandarin Chinese (cmn)    | [UD Chinese Beginner Treebank](http://hdl.handle.net/11234/1-6149)                  | CoNLL-U        | ELAN, FLEx, CLDF, CoNLL-U, FoLiA | ud-treebanks-v2.18.tgz|
|Cur.| Russian (rus)             | [UD Taiga Corpus](http://hdl.handle.net/11234/1-6149)                                  | CoNLL-U        | ELAN, FLEx, CLDF, CoNLL-U, FoLiA | ud-treebanks-v2.18.tgz|
|Cur.| Xibe (sjo)                | [UD Xibe Treebank](http://hdl.handle.net/11234/1-6149)                              | CoNLL-U        | ELAN, FLEx, CLDF, CoNLL-U, FoLiA | ud-treebanks-v2.18.tgz|
|Real.| Upper Tanana (tau)        | [Olga Lovick](https://artsandscience.usask.ca/profile/OLovick)                                   | ELAN           |   ELAN, FLEx, CLDF, CoNLL-U, FoLiA               | UTOFLA09Aug1201-18620.eaf |
|Real.| Dene Suline (chp)         | [Olga Lovick](https://artsandscience.usask.ca/profile/OLovick)                                   | ELAN           |   ELAN, FLEx, CLDF, CoNLL-U, FoLiA               | NET-2020-05-29-TDC.eaf    |

## Technical Notes & Schema Edge Cases

General mapping guidelines are in [Mapping_Guidelines.md](https://github.com/sarahrmoeller/igt-formatting/blob/main/MAPPING_GUIDELINES.md). Here we describe some edge cases and decisions that are specific to the languages and data samples in this repo.  

### Universal Dependencies (UD) & CoNLL-U

* *Transliteration Handling:* Practices vary by language repository as can be seen within `master.conllu`:
* *Word-level vs. Sentence-level:* Provided as a word-level attribute (Arabic) or a sentence-level comment (Hindi).
* *Phonological Transcription:* Transliterations may occasionally serve as phonological transcriptions (see Xibe, where data resides under the `# text[phon]` comment and `Translit` attribute).
* *Untokenized Data (`text_orig`):* Typically reserved for untokenized data. However, the Mandarin example anomalously uses this field to store tokenized data containing spaces.

### Language-Specific Edge Cases

* **Akan:** The selected sample contains `ɛɛbayɛ` instead of `ɛɛba yɛ` in the primary text, though it undergoes standard analysis as `ɛɛ-ba yɛ`. Additionally, the segmented prefix `ɛɛ-` contains a blank gloss field. These behaviors are preserved in the data as explicit edge cases.
