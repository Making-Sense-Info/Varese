# Use case for the DDI representation of variables in repetitive contexts

## Introduction

- Name and origin of the use case (institution, survey, information system), etc.

## General description
ELIPSS has a yearly core questionnaire (the Annual survey) to update sociodemgraphic data on panelists. Then, each month a new research survey is collected on a specific topic. The monthly survey can be cross-sectional (one-shot, for instance: fertility and birth control) or an additional wave of a longtudinal project (ex. Digital practices (wave 9)).

![](./img/cdsp-elipss-studies.PNG)
Dataset shared with the research community is a combination of variables from the monthly survey questionnaire (on a specific topic) and a set of additional sociodemographic data from the Annual survey of the current year. 

## Sources and variables

- Describe the variable to represent and how the data is produced
- Describe the repetitive aspect

## What do we want to represent?

We want to represent the organisation at high level.

- Detail on what specific aspects of variable representation are important in the context (e.g. lineage, evolutions of concept or representation, etc.)

## Example in pseudo-DDI
Gp: Group
SU: StudyUnit
RP: Resource Package

ELIPSS Panel (Gp)
- Resource Package (RP)
  *Reusable concepts, represented variables...*
- Annual survey (Gp)
  - Reusable metadata (RP)
  
  - Annual survey 2013 (SU)
  - ...
  - Annual survey 2023
- Longitudinal survey (Gp)
  - Digital practices (Gp)
    - Digital practices 2013 - Wave 1 (SU)
    - ...
    - Digital practices 2023 - Wave 9 (SU)
- Cross-sectional surveys (Gp)
  - Year 2021 (GP)
    - Inclusive writing 2021 (SU)
   
## Questions and topics for discussion
