# Insee use case for the DDI representation of variables in repetitive contexts

## General description 
### - Provide a description of the general context around the use case

At insee, we have described around 25 studies, some of which are repetitions of the same statistical programme over time and for which we have described the variables represented. Changes over time are documented at the level of the variable represented, i.e. variables that are stable between two surveys are assumed to be carried by the same variable represented. BasedOn relationships are used as much as possible to document the lineage between the represented variables. Analysing the pair of represented variables linked by a basedOn relationship is the simplest way to start assessing whether our existing metadata is sufficient to correctly reuse the variables over time. 

## Sources and variables ()
### - Describe the variable to represent and how the data is produced
### - Describe the repetitive aspect

In the DUMP of our Colectica database we have around 800 relationships based on that have been described between the variables represented. A first line of exploration is to analyse this specific set of metadata, the largest currently available to us. Our questions will be depicted mainly with one or two examples of statistical programme(s) in a repetitive context, for instance a piori LFS that is currently our epitome for repetitive surveys.

## What do we want to represent?
### - Detail on what specific aspects of variable representation are important in the context (e.g. lineage, evolutions of concept or representation, etc.)

a 'foundational' output would be A typology of 800 basedOn relationships could be created to determine:
- what type of changes there are between the variables represented in practice (addition of codes, modification of univers, modification of the description, modification of the description to encompass metadata that should be elsewhere (like population or versionrationale)...).
- assess the extent to which current basedOn documentation allows more or less automatic comparisons to be made.
- This statistical approach could provide an overview of the priorities and difficulties encountered.

The tree key aspects stand out from this analysis 

### -1 Description of the universe in a formal way. 
In order to compare  the statistics over time one key aspect is to be sure that the universe of interest is the same between the two questions. The producers spontaneously use a logical description of their universe of the variable. is helpfull in this way, The use of this formal description may facilitate description of evolution of the universe is helpfull in this way,.

The following example show how universe can be model logocicaly and 
    Name representedVariable SHART1
Label : Transport service: the individual has used a dedicated website or application (such as OUICAR, Koolicar, covoiturage-libre, etc.) in the last twelve months to obtain a transport service from a private individual.
Description
Asked if NUSEWEB = 1
Population
universe-16.png Statistical population of individuals
Representation Type
Code list
Selection Style
Choose a
Codes
codes-16.png SHART1

    1 	
    categories-16.png Yes
    2 	
    categories-16.png No

Name of the representedVariable SHART1
Label : Transport service: the individual has used a dedicated website or application (such as OUICAR, Koolicar, covoiturage-libre, etc.) in the last twelve months to obtain a transport service from a private individual.
Description

Population Asked if NUSEWEB = 1 or 2
 
universe-16.png Statistical population of individuals
Representation Type
Code list
Selection Style
Choose a
Codes
codes-16.png SHART1

    1 	
    categories-16.png Yes
    2 	
    categories-16.png No

where the representedVariable NUSEWEB is the Last personal use of the Internet with the following categories:
    
    1 	
    categories-16.png In the last three months
    2 	
    categories-16.png Between 3 months and one year
    3 	
    categories-16.png More than a year ago
    4 	
    categories-16.png Never used the internet


A more complexe of universe formally described is found with the RepresentedVariable RAISADM05 , that is asked if (NUSEWEB = 1 ou 2) and ADM3 = 2 and ADM4 = 2, where ADM3 is 

Name of the representedVariable ADM3
Label 
In the last twelve months, the respondent has used the Internet for private purposes to contact a government department or public service in order to complete their tax return online.
Description

Asked if NUSEWEB = 1 or 2
Population
universe-16.png Statistical population of individuals
Representation Type
Code list
Selection Style
Choose a
Codes
codes-16.png ADM3

    1 	
    categories-16.png Yes
    2 	
    categories-16.png No


ADM4 
Name
ADM4
Wording
During the last twelve months, apart from professional use, the respondent has not used the website or application of an administration or public service to access his/her personal data or information.
Description

Asked if NUSEWEB = 1 or 2
Population
universe-16.png Statistical population of individuals
Representation Type
Code list
Selection Style
Choose a
Codes
codes-16.png ADM4

    1 	
    categories-16.png Yes
    2 	
    categories-16.png No

several possibilites to handle universe define logicaly , 
- use a UniverseGenerationCode,
- use a the definition of a sub-universe
- use intersection of mulitple references to universe
- use the link with the question and the vairable. 

modelling of each case to be proposed 
  
- we could open the discussion by analysing the gap between what exists and what should be used (in terms of representation, universe) to improve the documentation and actionability of metadata in a repetitive context.

- depiction of our strategy and the question we want to raise with LFS
  
- proposals or questions on the DDI L model could be formulated if necessary and possible. 




### -2 Mapping information between variables (good one create on ontology to qualify the basedOn relation sustainability)
    • Mapping with a previous variable announcing they are consistant
    • Link with  a weighting variable;
        ◦ panel (longitudinal or one point in time analysis);
    • Caveats indicating the sucessive variables are not consistant;
    • Variable built based one or several variables ;
    Concept change, or new wording to present the concept

a proposal from gesis https://vocabularies.cessda.eu/vocabulary/Variables-Relations?lang=en   (we can register in a sense to participate in the construction and evolution of this proposal)
a proposal form NACDA 

-3 correspondance table between the code and the filed to document the changes  


## what do we want to formalize and why?
- Want to describe/understand the changes in the variables over time
- Want to re-use the correct variables, so need to understand what the differences 

## Precise example in pseudo-DDI
- Using BasedOn to link represented variables which are comprised of: Label, format, code list, unit type
- Examples - BasedOn used if 1) same variable but different unit type (technical), or 2) categories in code list changed over time 3)?
- BasedOn realtionships need to have a description, if common types, then create categories/cv so these are machine actionable.
 


