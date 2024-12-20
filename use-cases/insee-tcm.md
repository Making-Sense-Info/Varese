# INSEE use case

For most households studies, Insee uses an harmonised series of questions to get information about the household, the persons and the dwelling (_TCM_ for Tronc Commun des Ménages, or Common Core for Households). It can be used for one-time, or repeated over time for longitudinal surveys. It can be used as a whole or partly depending on the survey’s needs.

Also, the TCM is splitted into several modules that can be cherry picked by survey as needed.

## General description

In the context of longitudinal surveys, we want to be able to track changes in variables and in response domains.

## Sources and variables

For each person in the dwelling the name (`PRENOM`), sex (`SEXE`) and age (`AGE`) is asked. It is the basis on which we will iterate in order to get more detailled information on every member of the household (or households if there are many in the dwelling). For example, we might want to know the employment status.


| Survey year | Person | Age | Employment status |
| ----------- | ------ | --- | ----------------- |
| 2019        | Alice  | 40  | 1                 |
| 2019        | Bob    | 15  | -                 |
| 2020        | Alice  | 40  | 1                 |
| 2020        | Bob    | 16  | 5                 |

In 2019, the employment status of Alice is 'employed' (code `1`), but we don't have a value for Bob who is not in the scope (we only want this information for 15+ people). In 2020, Bob is in the scope, so we get his status (`5`, a student).

Also, if a person is employed, we will ask for its profession through a dedicated classification - which of course evolves.
## What do we want to represent ?

We want to be able to:

- __track changes of variables__: in the example above, the employment status in 2019 is collected via the variable `SITUA`, in 2020 it is `SITUAEU`, the european variable
	- both the name and the representation have changed
	- we want to be able to link those variables one way or another
- __track changes in response domains__: in 2020 the new version of the official classification ([PCS](https://fr.wikipedia.org/wiki/Professions_et_cat%C3%A9gories_socioprofessionnelles_en_France)) has changed

## Pseudo DDI

### Tracking variable changes

Documenting the changes could be done by:
1. grouping represented variables at the conceptual level
2. typing the changes between variables using a controlled vocabulary

```mermaid
flowchart TD
    QUESTION_2019
    QUESTION_2020
    CODE_LIST_2019
    CODE_LIST_2020
    VARIABLE_2019
    VARIABLE_2020
    CONCEPT
    
    VARIABLE_2019 <-->|IsBasedOn.hasDifferentVarName| VARIABLE_2020
    VARIABLE_2019 -->|has| CONCEPT
    VARIABLE_2020 -->|has| CONCEPT

    subgraph TCM_2019
        QUESTION_2019 --> VARIABLE_2019
        CODE_LIST_2019 --> VARIABLE_2019
        QUESTION_2019 --> CODE_LIST_2019
    end

    subgraph TCM_2020
        QUESTION_2020 --> VARIABLE_2020
        CODE_LIST_2020 --> VARIABLE_2020
        QUESTION_2020 --> CODE_LIST_2020
    end
```

### Tracking changes in response domain

The above model will indirectly allows to track changes in response domain. However, to specify what has changed (eg mapping between codes) we could make use of specific DDI construct like [ClassificationMap](https://ddialliance.github.io/ddimodel-web/DDI-L-3.3/composite-types/ClassificationMapType/) or [GenericMap](https://ddialliance.github.io/ddimodel-web/DDI-L-3.3/item-types/GenericMap/). 

→ Question: how to link between categories and classification items?

Another possibility would be to regroup represented variables through schemes or groups, but a limit of the current model is that VariableSchemes are for (instance) variables.

→ Should we work at the represented or instance level?
