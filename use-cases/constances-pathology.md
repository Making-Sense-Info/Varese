# Constances use case on Pathology for the DDI representation of variables in repetitive contexts

*Constances is a "general purpose" population-based epidemiological cohort. It is a nationally representative sample of 200,000 adults aged between 18 and 69 (at inclusion). This epidemiological cohort is designed to contribute to the development of epidemiological research and provide information for public health purposes.*

*People who have agreed to take part in Constances receive a self-administered questionnaire (let's name it "questionnaire at inclusion"). A medical questionnaire asked by the doctor (intermediray) is also completed as part of inclusion process. A follow-up questionnaire is sent annually to Constances volunteers, and comprises a common core and questions that vary from year to year (named follow-up questionnaire code named F-yyyy where yyyy corresponds to the year).*

*The data collected via this protocol is then cleaned before being made available to the scientific community.*

## General description
The general idea is to follow pathologies over time. Two different micro uses cases are presented:

1. **Add a new pathology (osteoporosis) within a list of pathologies**

A multiple-choice question captures the pathology suffered by the individual over the last 12 months. The response domain is a list of pathologies. The following year, the code for "osteoporosis" has been added to the list. This implies shifted code values (i.e. code value for "Parkinson's disease" moved from 41 to 42 between 2014 and 2015). On the other hand, categories are retained.

Problem: this is a multiple-choice question whose variable can be considered a vector variable collecting code values, as is the case in the current implementation of Constances. Because we don't know how to model it in DDI, the use case and its modelisation has been interpreted as add a new variable...

Data organisation currently in Constances

| Volunteer | Follow-Up | Pathology code value| Pathology label |
| -------- | -------- | -------- | -------- |
| V    | F2014     | 3 | Hypertension |
| V | F2014 | 41 | Parkinson disease |
| V    | F2015     | 3 | Hypertension |
| V | F2015 | 42 | Parkinson disease |

Researchers use to to compute data based on pathology label.

Data organisation considering DDI modelisation

| Volunteer | Follow-Up | Hypertension | Parkinson disease | Alzheimer disease |
|-----------|-----------|--------------|-------------------|-------------------|
| V         | F2014     | 1            | 1                 | 0                 |
| V         | F2015     | 1            | 1                 | 0                 |

2. **Link patholgies across questionnaires**

A question on pathologies since birth is asked in the medical questionnaire, with a slightly different list of pathologies. What we want is to link pathologies when they are:
  - identical
  - similar (i.e. "Chronic bronchitis" versus "Chronic bronchitis, COPD, emphysema, respiratory failure")

## Sources and variables
- Describe the variable to represent and how the data is produced
- Describe the repetitive aspect

## What do we want to represent?
- Detail on what specific aspects of variable representation are important in the context (e.g. lineage, evolutions of concept or representation, etc.)

## Precise example in pseudo-DDI
**Use case 1: Add a new pathology (osteoporosis) within a list of pathologies**

Ideas for DDI modelisation:
- Questionnaire F-2014 --> Instrument
- Question Pathologie 2014 --> QuestionGrid
- Parkinson's disease --> Concept
- Measure for Parkinson's disease (UnitType: Individual) --> ConceptualVariable
- Indicator for Parkinson's disease presence  (Representation: boolean/nominal?, Universe: Individuals over 18 years old at inclusion time) --> RepresentedVariable
- Indicator for Parkinson's disease presence - raw data (Name: V41 Individuals over 18 years old at inclusion time in metropolitan France in 2014) --> InstanceVariable
- Indicator for Parkinson's disease presence - processed/cleaned data (Name: V41, Population: Individuals over 18 years old at inclusion time in metropolitan France in 2014) --> InstanceVariable

The same model applied to 2015
- Questionnaire F-2015 --> Instrument
- Question Pathologie 2015 (based on the 2014 Question Pathologie) --> QuestionGrid
- Parkinson's disease --> Concept (the same concept as in 2014)
- Measure for Parkinson's disease (UnitType: Individual) --> ConceptualVariable (the same ConceptualVariable as in 2014)
- Indicator for Parkinson's disease presence  (Representation: boolean/nominal?, Universe: Individuals over 18 years old at inclusion time) --> RepresentedVariable (the same RepresentedVariable as in 2014)
- Indicator for Parkinson's disease presence - raw data (Name: V42 Individuals over 18 years old at inclusion time in metropolitan France in 2015) --> InstanceVariable
- Indicator for Parkinson's disease presence - processed/cleaned data (Name: V42, Population: Individuals over 18 years old at inclusion time in metropolitan France in 2015) --> InstanceVariable


**Use case 2: Link patholgies across questionnaires**

Ideas for DDI modelisation:
- If pathologies are identical, principles for modelisation are similar. Differences are about Questionnaire, question, time periode.
- If pathologies are similar, the same ideas for modelisation as before. Idea is to as a "similar" link between both concepts ("Chronic bronchitis" versus "Chronic bronchitis, COPD, emphysema, respiratory failure).


## Questions
- Should we link both instance Variable using BasedOn?
- What is the data processing/cleaning and how to represent it?
- Should we link instance variables from 2014 and 2015? How to reprensent instance variable lifecycle over time? Idea: Add based on reference across instance variables typed: "succeeds"
- Should we have a physical instance describing the raw data and referencing instance variables?
- Same question for processed data? 

To be noted: can be also linked to the same ConceptualVariable, the RepresentedVariable "Age of onset of Parkinson's disease" and so linked instance variable