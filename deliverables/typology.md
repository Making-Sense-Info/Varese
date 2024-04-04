Typology of Use Cases
=====================

The typology below is a potential way of categorising different types of studies.

|                   | Cross-sectional | Cross-sectional | Longitudinal  | Longitudinal    |
| ----------------- | --------------- | --------------- | ------------- | --------------- |
|                   | Retrospective   |   Prospective   | Retrospective |   Prospective   |
| Single Study      |                 |  INSEE / LFS    |   NACDA       |                 |
| Single Study Long |                 |                 |               |   CONSTANCES    |
| Multiple Studies  |                 |      INSEE      |   CLOSER      | FRANCE-COHORTES |

This could be a way of approaching guidance for best practice

Primary rationale for representation of variables
-------------------------------------------------

- Discovery and comparison
  - Display of conceptually equivalent variables (all come from the 'same' question but representation may change over time for different resons
- Metadata management within a larger organisation
  - Management of 'canonical or recommended' representation of concepts
  - Automation and management of other dimensions such as universe
- Harmonisation of data
  - Grouping of represented variables with a time series
  
Practical Considerations
------------------------

a. No. of Represented variables == No. of instance variables

Where representation of variables has a high variance e.g. continuously changing codelists / classifications such as 
political parties or occupational categories is there a benefit to creating Represented variables - should the primary aim be the
tracking of the classifications rather than at the variable level

b. Importance of universe

For longitudinal cohort data, the universe is 'almost irrelevant' within a study, but VERY important between studies

c. Horizontal variable comparison vs comparison via a higher level structure

Constructs such as BasedOn on between instance or represented variables can be used in the absence of other grouping structures
The use of a controlled vocabulary can assist in describing the relationships in a controlled way that can be used to create filters
or other strcutures to select or describe comparabability. One should consider not just what is being compared but what is implicitly not being
captured by such controlled vocabularies. Care should be taken to ensure that the controlled vocabularies describes comparison of representation 
only where they are a subset of equivalent concepts. This aligns with the use of ISO11179.





