# Constances use case on Pathology for the DDI representation of variables in repetitive contexts
*Constances is a "general purpose" population-based epidemiological cohort. It is a nationally representative sample of 200,000 adults aged between 18 and 69 (at inclusion). This epidemiological cohort is designed to contribute to the development of epidemiological research and provide information for public health purposes.*

*People who have agreed to take part in Constances receive a self-administered questionnaire (let's name it "questionnaire at inclusion"). A medical questionnaire asked by the doctor (intermediary) is also completed as part of inclusion process. A follow-up questionnaire is sent annually to Constances volunteers, and comprises a common core and questions that vary from year to year (named follow-up questionnaire code named F-yyyy where yyyy corresponds to the year).*

*The data collected via this protocol is then cleaned before being made available to the scientific community.*

## General description
Constances cohort captures pathologies suffered by the individual the last 12 months. In 2015, "osteoporosis" has been added within the list of disease. This implied shifted code values (i.e. code value for "Parkinson's disease" moved from 41 to 42 between 2014 and 2015). On the other hand, categories were retained.
The user wants to retrieve data about Parkinson's disease over time.
Researchers usually compute results based on the pathology label (most stable information).

## Sources and variables
A multiple-choice question captures the pathology suffered by the individual over the last 12 months. Each choice is represented by one checkbox.

Data is stored in a vector variable where for each follow-Up questionnaire and for each volunteer, pathology code value and pathology label are indicated where checkbox is checked.

Below is an example:

| Volunteer | Follow-Up | Pathology code value| Pathology label |
| -------- | -------- | -------- | -------- |
| V    | F-2014     | 3 | Hypertension |
| V | F-2014 | 41 | Parkinson disease |
| V    | F-2015     | 3 | Hypertension |
| V | F-2015 | 42 | Parkinson disease |

By definition of the general context (see introduction), variables are repeated over time. 

## What do we want to represent?
- Detail on what specific aspects of variable representation are important in the context (e.g. lineage, evolutions of concept or representation, etc.)
### Specific problem of representation
As previously mentionned, Constances organizes its data on pathologies in a vector variable. Because we don't know how to model this in DDI, data organization has been re-considered as one variable per pathology with boolean value stored.

Below is the example of the new data organization:

| Volunteer | Follow-Up  | Hypertension | Parkinson disease | Alzheimer disease |
|-----------|------------|--------------|-------------------|-------------------|
| V         | F-2014     | 1            | 1                 | 0                 |
| V         | F-2015     | 1            | 1                 | 0                 |


What we want to represent is the link between variables dealing with Parkinson disease over time.

## Precise example in pseudo-DDI
Ideas for DDI modelisation:
- Questionnaire F-2014 --> Instrument
- Question Pathologie 2014 --> QuestionGrid (first dimension is a code list)
- Parkinson's disease --> Concept
- Measure for Parkinson's disease (UnitType: Individual) --> ConceptualVariable
- Indicator for Parkinson's disease presence  (Representation: boolean/nominal?, Universe: Individuals over 18 years old at inclusion time) --> RepresentedVariable
- Indicator for Parkinson's disease presence - raw data (Name: V41 Individuals over 18 years old at inclusion time in metropolitan France in 2014) --> InstanceVariable
- Indicator for Parkinson's disease presence - processed/cleaned data (Name: V41, Population: Individuals over 18 years old at inclusion time in metropolitan France in 2014) --> InstanceVariable

The same model applied to 2015
- Questionnaire F-2015 --> Instrument
- Question Pathologie 2015 (based on the 2014 Question Pathologie) --> QuestionGrid (first dimension is a code list reusing categories of the 2014 code list)
- Parkinson's disease --> Concept (the same concept as in 2014)
- Measure for Parkinson's disease (UnitType: Individual) --> ConceptualVariable (the same ConceptualVariable as in 2014)
- Indicator for Parkinson's disease presence  (Representation: boolean/nominal?, Universe: Individuals over 18 years old at inclusion time) --> RepresentedVariable (the same RepresentedVariable as in 2014)
- Indicator for Parkinson's disease presence - raw data (Name: V42 Individuals over 18 years old at inclusion time in metropolitan France in 2015) --> InstanceVariable
- Indicator for Parkinson's disease presence - processed/cleaned data (Name: V42, Population: Individuals over 18 years old at inclusion time in metropolitan France in 2015) --> InstanceVariable

## Questions
- Should we link both instance Variable using BasedOn?
- What is the data processing/cleaning and how to represent it?
- Should we link instance variables from 2014 and 2015? How to reprensent instance variable lifecycle over time? Idea: Add based on reference across instance variables typed: "succeeds"
- Should we have a physical instance describing the raw data and referencing instance variables?
- Same question for processed data? 

To be noted: can be also linked to the same ConceptualVariable, the RepresentedVariable "Age of onset of Parkinson's disease" and so linked instance variable