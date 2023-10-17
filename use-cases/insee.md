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

-1 Description of the universe in a formal way. The producers spontaneously use a logical description of their universe of the variable. The use of UniverseGenerationCode
is helpfull in this way, and the use of this formal description may facilitate description of evolution of the universe.

-2 Mapping information between variables (good one create on ontology to qualify the basedOn relation sustainability)
    • Mapping with a previous variable announcing they are consistant
    • Link with  a weighting variable;
        ◦ panel (longitudinal or one point in time analysis);
    • Caveats indicating the sucessive variables are not consistant;
    • Variable built based one or several variables ;
    Concept change, or new wording to present the concept

-3 correspondance table between the code and the filed to document the changes  

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
  
- we could open the discussion by analysing the gap between what exists and what should be used (in terms of representation, universe) to improve the documentation and actionability of metadata in a repetitive context.

- depiction of our strategy and the question we want to raise with LFS
  
- proposals or questions on the DDI L model could be formulated if necessary and possible. 


## what do we want to formalize and why?
- Want to describe/understand the changes in the variables over time
- Want to re-use the correct variables, so need to understand what the differences 

## Precise example in pseudo-DDI
- Using BasedOn to link represented variables which are comprised of: Label, format, code list, unit type
- Examples - BasedOn used if 1) same variable but different unit type (technical), or 2) categories in code list changed over time 3)?
- BasedOn realtionships need to have a description, if common types, then create categories/cv so these are machine actionable.
 


