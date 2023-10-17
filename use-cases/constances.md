# Constances use case for the DDI representation of variables in repetitive contexts

## General description

In order to meet the requirements of researchers and various institutions using Constances data, a clear and precise description of the different available variables (at enrollment and follow-up) must be accessible. For this first use cases, we propose to focus on smoking-related data and data about the consumption of fruits and juices.

## Sources and variables

The complete list of variables for smoking status is available [here](./smoking-variables.md). Variables for fruits and juices are described below.


## What do we want to represent?

To better organize this data and facilitate decision-making, it is recommended to these variables in a standard DDI format. The detail of the variables available in the specific Excel table 
All described parts listed in the tables and also 
- Highlight comparable questions between inclusion and follow up
- Highlight participation (respondent) at each follow up
- Highlight the number on follow up wave for participants (median follow-up…) 

## Selected use cases


### Cigarettes

Instrument: Inclusion
- Question: If yes: Do you still smoke currently? 
  - Instance variable: AQ_COMPORT_TcFumAct
- If yes: Indicate how many cigarettes per day on average?
  - Instance variable: AQ_COMPORT_TcCigtJNb

Instrument: Follow-up Instrument
- Question: Currently, do you smoke (excluding e-cigarettes)? --> AQ_COMPORT_TcActFume
- Question: If yes, how many do you smoke per day on average (cigarettes)?
  - Instance variable: AQ_COMPORT_TcCigtJNb

### Fruits

![img](./img/constances-use-case-fruits.jpg)

Instrument: Inclusion V1 
- Concept: Fruit consumption
  - Question: How often do you eat raw or cooked fruit (including 100% fruit juice)? / A quelle fréquence consommez-vous des fruits crus ou cuits (y compris les jus 100% fruit) ?
    - InstanceVariable: AQ_ALIM_FreqConsFruit

Instrument: Inclusion V2
- Concept: Fresh fruit consumption / Consommation de fruits frais?
- (BasedOn Previous question) How often do you eat fresh fruit (including pressed fruit)? / A quelle fréquence mangez-vous des fruits frais (y compris fruits pressés)?
  - Instance variable: AQ_ALIM_FreqConsFruitCPJ_n

- Concept: Fruit juice consumption / Consommation de jus de fruit?
- (BasedOn Previous question) How often do you drink juice or nectar?
  - Instance variable: AQ_ALIM_FreqConsjusPJ_n

### General idea: follow pathologies over time

1. Code added between two follow-up
- Follow-up questionnaires (code named F-*yyyy*)
- A question that captures the pathologies declared by the individual. The response domain is a list of pathologies.
- The following year, the code for osteoporosis has been added to the list. This implies shifted code values (i.e. code value for "Parkinson's disease" moved from 41 to 42 between 2014 and 2015). On the other hand, categories are retained.
- The question is about the last 12 months

Problem: this is a multiple-choice question whose variable can be considered a vector variable collecting code values, as is the case in the current implementation of Constances. Because we don't know how to model it in DDI, the use case and its modelisation has been interpreted as add a new variable...maybe not an interesting use case...

Ideas for DDI modelisation:
- Questionnaire F-2014 --> Instrument
- Question Pathologie 2014 --> QuestionItem
- Parkinson's disease --> Concept
- Measure for Parkinson's disease (UnitType: Individual) --> ConceptualVariable
- Indicator for Parkinson's disease presence  (Representation: boolean/nominal?, Universe: Individuals over 18 years old at inclusion time) --> RepresentedVariable
- To be noted: can be also linked to the same ConceptualVariable, the representedVariable "Age of onset of Parkinson's disease" --> RepresentedVariable
- Indicator for Parkinson's disease presence - raw data (Name: V42 Individuals over 18 years old at inclusion time in metropolitan France in 2014) --> InstanceVariable
- Indicator for Parkinson's disease presence - processed data (Name: V41, Population: Individuals over 18 years old at inclusion time in metropolitan France in 2014) --> InstanceVariable


The same model applied to 2015
- Questionnaire F-2015 --> Instrument
- Question Pathologie 2015 (based on the 2014 Question Pathologie) --> QuestionItem
- Parkinson's disease --> Concept (the same concept as in 2014)
- Measure for Parkinson's disease (UnitType: Individual) --> ConceptualVariable (the same ConceptualVariable as in 2014)
- Indicator for Parkinson's disease presence  (Representation: boolean/nominal?, Universe: Individuals over 18 years old at inclusion time) --> RepresentedVariable (the same RepresentedVariable as in 2014)
- Indicator for Parkinson's disease presence - raw data (Name: V42 Individuals over 18 years old at inclusion time in metropolitan France in 2015) --> InstanceVariable
- Indicator for Parkinson's disease presence - processed data (Name: V42, Population: Individuals over 18 years old at inclusion time in metropolitan France in 2015) --> InstanceVariable

- Should we link both instance Variable using BasedOn?

To be noted: can be also linked to the same ConceptualVariable, the representedVariable "Age of onset of Parkinson's disease" and so linked instance variable



2. Link categories across questionnaires
- Medical Questionnaire (part of inclusion process)
- Asked by the doctor (intermediary)
- A question on pathologies is also asked, with a slightly different list of pathologies.
- The question concerns pathologies since birth.
- What we want is to link pathologies when they are :
  - identical
  - similar


Ideas for DDI modelisation:



----
- V17 (osteoporosis)
- V18 Polyarthrite (code value 18)
