# Guidelines

## Introduction

- aim of the document, intended audience, etc.
- governance: who owns the document, how to contribute?

## What are we talking about?

- variables and questions
- value domain representation
- high-level description of the variable cascade (without reference to DDI)
- what do we mean by repetitive and longitudinal contexts
- what do we want to represent and why (provenance, reproducibility, machine-actionability...)

## What does DDI-L provide?

DDI-Lifecycle provides a range of different structures which can used alone or in combination to manage item types.
Item types tructures which are important to the use cases
- Variables Iinstance variables)
  - code lists
  - categories
  - substantive / sentinenl values
- Questions
  - response domains
- Universes
- Populations
- Measurement
- Concepts
- Conceptual Variables
- Represented Variables

## Controlled Vocabularies


### Schemes
These are for organising a single item type, such as questions, variables, universes and code lists to support management and reuse across an organistion.

### Groups
These structures assist discovery and organisation of item types by
- referencing a specific item type within one or many schemes, e.g. variables related to Age
  - CLOSER Topics Level 1 and 2
  - Insee example from LFS 
- group the same item type which are not managed in a scheme e.g. waves of data collection in an ongoing study
  - CLOSER 

### Relationships
These support the definition of the location and type of a object being referenced for example variable representation can be described as code list and a reference to the target URN of the object code list. A code list can be referenced from many variables supporting reuse of a code list.

BasedOn supports annotation of the relationship with a textual description and / or controlled vocabulary. This supports the provenance of a specific item type to the same item type. e.g. variable B is based on Variable A 

### Variable Cascade
Supports the specialisation of variables with a reference
Conceptual -> Represented -> Variable (instance)

- see [CLOSER document](../workshops/comparison-overview.md)


## Use cases

### For each use cases

- description
- what do we want to formalize and why?
- precise example in pseudo-DDI
- alternative possibilities with pros and cons for each

(for CLOSER use case, mention automated methods for finding relations: NLP...)

### Links

- Constances [fruits use case](../use-cases/constances.md)
- Insee [general use case](../use-cases/insee.md)
- Insee [TCM use case](../use-cases/insee-tcm.md)

## What do we need (more that DDI-L)?

- baseOn categories (cf. NACDA)

## Conclusions

- DDI provides different tools, additional ones may be needed
- There is no perfect answer, it depends on multiple factors (effort in metadata modelling, needs of users, etc.)