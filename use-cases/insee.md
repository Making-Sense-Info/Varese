# Insee use case for the DDI representation of variables in repetitive contexts

## General description 
### - Provide a description of the general context around the use case

At insee, we have described around 25 studies, some of which are repetitions of the same statistical programme over time and for which we have described the variables represented. Changes over time are documented at the level of the variable represented, i.e. variables that are stable between two surveys are assumed to be carried by the same variable represented. BasedOn relationships are used as much as possible to document the lineage between the represented variables. Analysing the pair of represented variables linked by a basedOn relationship is the simplest way to start assessing whether our existing metadata is sufficient to correctly reuse the variables over time. 

## Sources and variables ()
### - Describe the variable to represent and how the data is produced
### - Describe the repetitive aspect

In the DUMP of our Colectica database we have around 800 relationships based on that have been described between the variables represented. A first line of exploration is to analyse this specific set of metadata, the largest currently available to us. Our questions will be depicted mainly with one or two examples of statistical programme(s) in a repetitive context, for instance a piori LFS that is currently our epitome for repetitive surveys.


### - Result of the Analysis of our existing Represented Variables when a basedOn relation exists

a 'foundational' output would be A typology of 800 basedOn relationships could be created to determine:
- what type of changes there are between the variables represented in practice (addition of codes, modification of univers, modification of the description, modification of the description to encompass metadata that should be elsewhere (like population or versionrationale)...).
- assess the extent to which current basedOn documentation allows more or less automatic comparisons to be made.
- This statistical approach could provide an overview of the priorities and difficulties encountered.

The tree key aspects stand out from this analysis 

### -1 Description of the universe in a formal way. 
In order to compare  the statistics over time one key aspect is to be sure that the universe of interest is the same between the two questions. The producers spontaneously use a logical description of their universe of the variable. is helpfull in this way, The use of this formal description may facilitate description of evolution of the universe is helpfull in this way,.

The following example show how universe can be model logocicaly : 

we have two variables called SHART1 from two sucessive studies. The variables are linked by a basedOn relation.  we will call respectively these variables SHART1, la nouvelle variable, and SHART1_bo  the former variable referenced by the basedOn relation.
    
The first variable we consider is SHART1, its Label is : Transport service: the individual has used a dedicated website or application (such as OUICAR, Koolicar, covoiturage-libre, etc.) in the last twelve months to obtain a transport service from a private individual. This variable as the universe { NUSEWEB = 1 }

The value domain of this question is 

    1 - Yes
    2 - No

The former variable (SHART1_bo in my file) has a different universe : {Population Asked if NUSEWEB = 1 or 2}. The value domain is the same.

    1 - Yes
    2 - No

where the representedVariable NUSEWEB is the Last personal use of the Internet with the following categories:
    
    1 - In the last three months
    2 - Between 3 months and one year
    3 - More than a year ago
    4 - Never used the internet

(-> double checked with the nusweb represented variable)

So in these first case if we don't know the difference between the universes we cannot compare properly the statitics over time.

A more complexe exemple of universe formally described is found with the RepresentedVariable RAISADM05 , that is asked if (NUSEWEB = 1 ou 2) and ADM3 = 2 and ADM4 = 2, where ADM3 has the label  "In the last twelve months, the respondent has used the Internet for private purposes to contact a government department or public service in order to complete their tax return online".
Description. In this case we have to define a more complexe universe.

### -2 Other bag of observations coming from this analysis
in the frame of our question, we can observe the following metadata provided by the producers to describe the relation between variables 

Mapping with a previous variable announcing they are consistant

Link with  a weighting variable

panel (longitudinal or one point in time analysis)

Caveats indicating the sucessive variables are not consistant

Variable built based one or several variables

Concept change, or new wording to present the concept




## what do we want to formalize and why?
- Want to describe/understand the changes in the variables over time
- Want to re-use the correct variables, so need to understand what the differences 

## Controled vocabulary to qualify the lineage between the variables

a proposal from gesis https://vocabularies.cessda.eu/vocabulary/Variables-Relations?lang=en   (we can register in a sense to participate in the construction and evolution of this proposal). The 6 following categories are the controlled vocabulary created by GESIS.
	
    01 IsBasedOn.hasDifferentWave 	Variable B is based on a previous variable A from a previous wave (W); it measures the same concept (C_Var) as variable A in the same study (S) program but a different wave (W). This relation represents the same variable (Var), with no differentiation in other waves (W).
	
    02 IsBasedOn.hasDifferentSurvey 	Variable B is based on a previous variable A, but from a different Survey (Sy); it measures the same concept (C_Var) as variable A in the same study (S) program and at the same wave (W). This relation represents the identical variable (Var), with no differentiation in other waves (W). More than one survey (Sy) is applied to participants from different groups but measuring the same concept (C_Var) in different contexts, e.g. income for couples and single households in different surveys in the same wave (W) or based on other participants' characteristics.
	
    03 IsBasedOn.hasDifferentVarName 	Variable B is based on a previous variable A from a previous wave (W); it measures the same concept (C_Var) as variable A in the same study (S) program but a different wave (W). Still, it may have a different name (R_Vn) than Variable A in the previous wave (W) of the same study (S).
	
    04 IsBasedOn.hasDifferentVarLabel 	Variable B is based on a previous variable A from a previous wave (W); it measures the same concept  (C_Var) as variable A in the same study  (S) program but a different wave (W). Still, it may have a different label (R_Vl) than Variable A in the previous wave (W) of the same study (S).
	
    05 IsBasedOn.hasDifferentQuestion 	Variable B is based on a previous variable A in the same study (S) programme but a different wave (W). Still, it may have a different name (R_Vn) or label (R_Vl) than Variable A (or not) in another wave (W), and it has a different question-wording (Q) in the new wave (W)—the question (Q) lexical expressions changes. 
	
    06 IsBasedOn.DifferentResponseSchema 	Variable B is based on a previous variable A in the same study (S) programme but a different wave (W). Still, it may have a different name (R_Vn) or label (R_Vl) than Variable A in another wave (W) or not. The question wording is the same, but the response schema (RS) differs. The variable (Var) values scale changes from the registering variable B to a related variable A. Variable A has a given number of measures changed in another wave (W), so the related variable B in the future waves (W) of the same study (S) has measure values increased or decreased ‘n’ to ‘n.’ For instance, Variable A has four values in a prior wave (W): how strongly are you interested in politics? Very strongly (1), strongly (2), not so strongly (3), not at all (4). The variable B is extended and added another value: very strong (1), strongly (2), medium (3), little (4), not at all (5). Different Response Schemas (RS) can be different response scales, such as Likert Scale type, Dichotomous or Trichotomous scales, Semantic differential scales, and other response schemas (RS). Response scale types should be part of the relation type label: e.g., IsBasedOn.DifferentResponseSchema.isTypeLikertScale.


### The categories we could propose to expand the controlled vocabulary from GESIS is 

IsBasedOn.hasDifferentUniverse	variable B is based on a previous variable A, but the universe is different.

IsBasedOn.hasDifferentConcept	variable B is based on a previous variable A, but the concept measured is different.

IsBasedOn.hasDifferentValueDomain	Variable B is based on a previous variable A but has a different value domain, either substantive value domain or sentinel value domain

IsBasedOn.hasDifferentUnitType	variable B is based on a previous variable A, but the UnitType is different
	

### Another angle for variable transformation. 
This crosses previous categories , so it could be an extension, like IsBasedOn.hasDifferentValueDomain.aggregation	

IsBasedOn.Aggregation	variable B is based on a previous variable A. the representation of the variable B is different in order to correspond to an agregation values of the variable A (gathering of categories or creation of intervalles if variable A is numeric). This case is a subcase 

IsBasedOn.Imputation	variable B is based on a previous variable A. the content of the component of the dataset corresponding to the variable B is changed by imputation process. 


### Another kind of relation ? 
Flag to directly convey caveats or information that variables are comparable ?



## additionnal question concerning the modeling 
several possibilites to handle universe defined logicaly , 
- use a UniverseGenerationCode,
- use a the definition of a sub-universe
- use intersection of mulitple references to universe
- use the link with the question and the variable. 

The basedOn relation has a cardinality 0 1 , so if we want to use several differences at the same time we have to precise how to do that. 
The based On relation is use to documente how the variables are created. It could be important to compare also variables that are not directly in a lineage relation. So the question is not to have a controlled vocabulary for the basedOn relation , but more generaly a controlled vocabulary to compare variables , that could be used in a mapping for instance. 

by example the following situation exists : IsBasedOn.hasDifferentStatisticalProgram	variable B has the same content (Concept, representation, unittype) but is created by another survey

relation between variables and weights variable



