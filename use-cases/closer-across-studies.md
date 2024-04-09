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

**Problem Within Study** – Researcher needs to view the longitudinal variables within a longitudinal population study (LPS)
**Potential DDI solution** - Create relationships between the similar variables across study waves using the variable cascade

CLOSER organises Groups (i.e. CLOSER LPS) which contain several StudyUnits (i.e. LPS waves) of DataCollections of survey Instruments (i.e. questionnaire) which contain QuestionConstructs. 
The longitudinal variable relationships across LPS waves can be described using the variable cascade. Each InstanceVariable within a DataFile with the same underlying concept (e.g regular smoking, see figure below) references a ConceptualVariable. Therefore, each ConceptualVariable is a representation of the longitudinal variable which has been repeated at least once across LPS waves. RepresentedVariables do not need to be specified and so these will not be included in order to reduce the overhead. 
This solution will allow researchers to see all instances of where that concept was measured organsied by which are ordered by the TemporalCoverage.
Example – Longitudinal variable ‘Respondent has regularly smoked cigarettes’ within ALSPAC LPS
Group: ALSPAC
ConceptualVariable: Respondent has regularly smoked cigarettes

QuestionText: Which of the following have you ever smoked regularly? Cigarettes
InstanceVariable label: J1c1: Respondent has regularly smoked cigarettes
StudyUnit: ALSPAC Childhood (5 years to 12 years 11 months)

QuestionText: Which of the following have you ever smoked regularly? Cigarettes
InstanceVariable label: G2c1: Respondent has ever smoked cigarettes regularly
StudyUnit: ALSPAC Childhood (5 years to 12 years 11 months)

**Problem Across Study** - Researcher needs to find similar variables across longitudinal population study (LPS) for potential harmonisation. 
**Potential DDI solution** - Create relationships between the similar variables across study waves using the variable cascade plus additional grouping.
Each LPS ConceptualVariable within a Group (LPS) which has a similar underlying concept (e.g ever smoked, see figure below) can be grouped together into a conceptual variable group.
Example – Ever smoked conceptual variable group with longitudinal variables from ALSPAC and NSHD LPS
Groups: ALSPAC and NSHD
Conceptual variable group: Ever smoked

QuestionText: Have you ever smoked as much as one cigarette per day for as long as a year?
InstanceVariable label: Have you ever smoked as much as 1 cigarette/day?
StudyUnit: 1982 (Age 36)

QuestionText: Have you ever smoked cigarettes regularly, by which I mean at least one cigarette a day for 12 months or more?
InstanceVariable label: Have you ever smoked cigarettes regularly: at least one cigarette a day for 12 months or more? 
StudyUnit: 1999 (Age 53)

