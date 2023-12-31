# Overview of DDI ways of comparing items

## Grouping

### Variable and Question Groups
Use of these specialised structures allows a list of references to items which can be grouped themetically normally to a controlled vocabulary.
Variable Groups example: https://discovery.closer.ac.uk/Item/uk.closer/766a9222-4c66-4f84-9259-b78ceda9ceab/1
```mermaid
graph TB
  VGr[Age] -- Variable Reference --> Day[Date on Individual Questionnaire-day]
  VGr[Age] -- Variable Reference --> Month[Date on Individual Questionnaire-month]
  VGr[Age] -- Variable Reference --> Year[Date on Individual Questionnaire-year]
```
### StudyUnit Groups
Group study units

```mermaid
graph TB
  Gr[Labour Force Survey] -- StudyUnit Reference --> LFS2021[LFS 2021]
  Gr[Labour Force Survey] -- StudyUnit Reference --> LFS2022[LFS 2022]
  Gr[Labour Force Survey] -- StudyUnit Reference --> LFS2023[LFS 2023]
```

### BasedOn
This allows an item to reference another item using the source URN and also supports both a textual description and use of  a controlled vocabulary.

#### Single source
```mermaid
graph RL
WellC[Wellness Questions-CAPI]  -- BasedOn --> WellP[Wellness Questions-Paper]
WellT[Wellness Questions-Telephone] -- BasedOn --> WellP[Wellness Questions-Paper]
WellW[Wellness Questions-Web] -- BasedOn --> WellP[Wellness Questions-Paper]
```
#### Lifecycle evolution of a question and resulting variables
```mermaid
graph TB
  Pol90[Which Party did you vote for in the 1990 General Election] -- BasedOn -->  Pol80[Which Party did you vote for in the 1980 General Election]
  subgraph 1990
    Pol90[Which Party did you vote for in the 1990 General Election] --> Pol90Var[Party voted for in 1990]
  end  subgraph 1980
    Pol80[Which Party did you vote for in the 1980 General Election] --> Pol80Var[Party voted for in 1980]
  end
```

#### Lifecycle evolution of a variable
```mermaid
graph RL
  Pol90Var[Party voted for in 1990] -- BasedOn -->  Pol80Var[Party voted for in 1980] -- BasedOn -->  Pol78Var[Party voted for in 1978]
```

### Variable Cascade
This is a hierachy of
- A conceptual variable
- Represented variables
- Instance variable

```mermaid
graph BT
   Pol78Var[Party voted for in 1978] -- Represented Variable Reference --> PolRep1 -- Conceptual Variable Reference --> PolConcept[Political Party Affiliation]
   Pol80Var[Party voted for in 1980] -- Represented Variable Reference --> PolRep1 -- Conceptual Variable Reference --> PolConcept[Political Party Affiliation]
   Pol90Var[Party voted for in 1990] -- Represented Variable Reference --> PolRep2 -- Conceptual Variable Reference --> PolConcept[Political Party Affiliation]
```

The variable cascade does not require all three to be specified, for example, omitting the representation
- A conceptual variable
- Instance variables
```mermaid
graph BT
  Pol90Var[Party voted for in 1990] -- Conceptual Variable Reference -->  PolConcept[Political Party Affiliation]
  Pol80Var[Party voted for in 1980] -- Conceptual Variable Reference -->  PolConcept[Political Party Affiliation]
  Pol78Var[Party voted for in 1978] -- Conceptual Variable Reference -->  PolConcept[Political Party Affiliation]
```

If there is a repeated question is used, these relationships can also be expresed
```mermaid
graph BT
  Pol90Var[Party voted for in 1990] -- Question Reference --> PolQ[Which Party did you vote for in the last General Election]
  Pol80Var[Party voted for in 1980] -- Question Reference ---> PolQ[Which Party did you vote for in the last General Election]
  Pol78Var[Party voted for in 1978] -- Question Reference ---> PolQ[Which Party did you vote for in the last General Election]
  Pol90Var[Party voted for in 1990] -- Conceptual Variable Reference -->  PolConcept[Political Party Affiliation]
  Pol80Var[Party voted for in 1980] -- Conceptual Variable Reference -->  PolConcept[Political Party Affiliation] 
  Pol78Var[Party voted for in 1978] -- Conceptual Variable Reference -->  PolConcept[Political Party Affiliation] 

```
