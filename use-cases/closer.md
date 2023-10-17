# CLOSER use case for the DDI representation of variables in repetitive contexts

## General description

- CLOSER Discovery is a multi-purpose discovery platform. Multi-purpose has a number of different contexts:
  - The subject areas are numerous
  - The users have different perspectives on how they want to use the available data resources
  - The representation of 'comparable' variables repeated within and across studies needs to reflect the various potential uses of the data
  - CLOSER will not (at least initially) attempt to 'harmonise' variables, e.g. to group variables using DDI Represented Variables
  - We are proposing to compare questions (text and response domain) to identify related variables generated from these questions and assign them to conceptual variables
 
To support multiple purposes;
  - a. conceptual variables are created which concord (instance) variables within a single study (data collections on the same partipant sample)
  - b. cross study conceptual variable groups are created which reference study level conceptual variables
 

## Sources and variables

- Data collection information is available which describes the data collection methodology coverage
- Questionnaires (instruments) describe the way in which data is collected, including the question items and the routing of the question items.
- Data available are one or more variables which are collected from a question in a survey or clinical instrument
- Variables reference their originating question, and derived variabled reference there source variables
- Variables and questions groups based on the CLOSER Topic vocabulary reference all questions and variables

``` mermaid
graph TB
  Inst1[Instrument] --> QA[Question A]
  QA[Question A] --> VA1[Variables]
  QA[Question A] --> VA2[Variables]
  QA[Question A] --> VA3[Variables]
  VA1[Variables] --> CV1[Conceptual Variable A] 
  VA2[Variables] --> CV1[Conceptual Variable A] 
  VA3[Variables] --> CV1[Conceptual Variable A]
  Inst2[Instrument] --> QB[Question A]
  QB[Question A] --> VB1[Variables]
  QB[Question A] --> VB2[Variables]
  QB[Question A] --> VB3[Variables]
  VB1[Variables] --> CV1[Conceptual Variable A] 
  VB2[Variables] --> CV1[Conceptual Variable A] 
  VB3[Variables] --> CV1[Conceptual Variable A]
  Inst1[Instrument] -- next data collection -->   Inst2[Instrument] 
```

- Describe the repetitive aspect
  - Variables are referenced by the same conceptual variable within a single longitudinal study
  - Definition of a conceptual variable within a study is strongly related to the question item within a questionnaire
  - Conceptual variable groups are used to reference conceptual variables within more than one longitudinal study

## What do we want to represent?

- A conceptual group and description will be created at a cross-study level
- Open questions are representation / ontolgies for other contextual information for which Controlled vocabulaires exists
- Existing vocabularies include mode, geographical coverage
- Other contextual information which may be candidates for CVs could be explored, e.g. administrative data,  
- Other contextual information which may be candidates for CVs could be explored, e.g. administrative data

## Relevent resources:
- https://doi.org/10.5281/zenodo.8001540 (Question driven equivalence - IAssist presentation)
- https://doi.org/10.5281/zenodo.8410617 (Towards Metadata Driven Harmonisation - ESRA presentation)
- https://wiki.ucl.ac.uk/display/CLOS/Topics (CLOSER variable/question groups)
- https://wiki.ucl.ac.uk/pages/viewpage.action?pageId=62790771 (CLOSER DDI Profile)
- https://harmonize.icpsr.umich.edu/Account/Login?returnUrl=%2F (NACDA portal)
- https://deepblue.lib.umich.edu/handle/2027.42/156403 (NACDA white paper from 2020)
