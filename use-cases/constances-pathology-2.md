# Constances use case on Pathology for the DDI representation of variables in repetitive contexts
*Constances is a "general purpose" population-based epidemiological cohort. It is a nationally representative sample of 200,000 adults aged between 18 and 69 (at inclusion). This epidemiological cohort is designed to contribute to the development of epidemiological research and provide information for public health purposes.*

*People who have agreed to take part in Constances receive a self-administered questionnaire (let's name it "questionnaire at inclusion"). A medical questionnaire asked by the doctor (intermediary) is also completed as part of inclusion process. A follow-up questionnaire is sent annually to Constances volunteers, and comprises a common core and questions that vary from year to year (named follow-up questionnaire code named F-yyyy where yyyy corresponds to the year).*

*The data collected via this protocol is then cleaned before being made available to the scientific community.*

## General description
A question on pathologies since birth is asked in the medical questionnaire, with a slightly different list of pathologies. What we want is to link pathologies when they are:
- identical
- similar (i.e. "Chronic bronchitis" versus "Chronic bronchitis, COPD, emphysema, respiratory insufficiency")

Users want to retrieve data about Chronic bronchitis or similar concept.

## Sources and variables
A multiple-choice question in the medical questionnaire captures pathologies suffered by the individual since birth. Each choice is represented by a yes/no checkbox. For instance, the doctor checked "yes" for ""Chronic bronchitis".
A multiple-choice question in the follow-up questionnaire captures pathologie suffered by the individual over the last 12 months. Each choice is represented by one checkbox. For instance, the individual checked for "Chronic bronchitis, COPD, emphysema, respiratory insufficiency"


## What do we want to represent?

What we want to represent is the link between concepts formalising that "Chronic bronchitis" and "Chronic bronchitis" are similar.