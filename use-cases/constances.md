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
- Follow-up questionnaires
- A question that captures the pathologies declared by the individual. The response domain is a list of pathologies.
- The following year, the code for osteoporosis has been added to the list. This implies shifted code values. On the other hand, categories are retained
- The question is about the last 12 months
  
2. Link categories across questionnaires
- Medical Questionnaire (part of inclusion process)
- Asked by the doctor (intermediary)
- A question on pathologies is also asked, with a slightly different list of pathologies.
- The question concerns pathologies since birth.
- What we want is to link pathologies when they are :
  - identical
  - similar
