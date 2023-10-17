# Guidelines

## Introduction

- aim of the document, intended audience, etc.
- governance: who owns the document, how to contribute?

## What are we talking about?

- types of data to describe (cross-sectional, longitudinal...) with examples corresponding to the use cases
- variables and questions
- value domain representation
- high-level description of the variable cascade (without reference to DDI)
- what do we mean by repetitive and longitudinal contexts
- what do we want to represent and why (provenance, reproducibility, machine-actionability...)

## What does DDI-L provide?

DDI-Lifecycle provides a range of different structures which can used alone or in combination to manage item types.
Item types structures which are important to the use cases include
- Concepts
- Conceptual Variables
- Represented Variables
- Variables (Instance variables)
  - code lists
    - code value
    - categories
  - numeric representation
  - substantive (valid) / sentinel (invalid) values
- Questions
  - response domains
- Universes
  - Population
    - Spatial
    - Temporal
- Unit type
- Measurement

## Controlled Vocabularies
Controlled vocabularies (standardised and organised arrangements of words and phrases and provide a consistent way to describe data) though not specific to DDI-L they can be used to describe the usage of a specific item type. An example is type of instrument used in data collection: https://vocabularies.cessda.eu/vocabulary/TypeOfInstrument?lang=en 

### Schemes
These are for organising a single item type, such as questions, variables, universes and code lists to support management and reuse across an organistion.

### Groups
These structures support discovery and organisation of item types by
- referencing a specific item type within one or many schemes, e.g. variables related to Age
  - CLOSER Topics Level 1 and 2
  - Insee example from LFS 
- group the same item types which are not managed in a scheme e.g. waves of data collection in an ongoing study
  - CLOSER 

### Relationships
These support the definition of the location and type of a object being referenced for example variable representation can be described as code list and a reference to the target URN of the object code list. A code list can be referenced from many variables supporting its reuse.

BasedOn supports annotation of the relationship between a specific item type to the same item type, with a textual description and / or controlled vocabulary that describes the nature of the relationship. This supports the provenance of a specific item type to the same item type. e.g. variable B is based on Variable A. 

### Variable Cascade
Supports the specialisation of variables with a reference
Conceptual -> Represented -> (Instance) Variable
*Note inherited item types are in* **bold**)

- Conceptual variable (concept + unit type)
- Represented variable (**concept + unit type** + value representation (substantive values))
- (Instance) Variable (**concept + unit type** + variable representation (**substantive** + sentinal values), universe reference, measurement, question reference etc)

- see [CLOSER document](../workshops/comparison-overview.md)

## Use cases

### For each use case

- description
- what do we want to formalize and why?
- precise example in pseudo-DDI
- alternative possibilities with pros and cons for each

(for CLOSER use case, mention automated methods for finding relations: NLP...)

### Links

- Constances [fruits use case](../use-cases/constances.md)
- Insee [general use case](../use-cases/insee.md)
- Insee [TCM use case](../use-cases/insee-tcm.md)

## What do we need (more than DDI-L)?

- baseOn categories (cf. NACDA)

## Conclusions

- DDI provides different tools, additional ones may be needed, some are in CDI
- There is no perfect answer, it depends on multiple factors (effort in metadata modelling, needs of users, etc.)

