##Problem Within Study – Researcher needs to view the longitudinal variables within a longitudinal population study (LPS)
##Potential DDI solution - Create relationships between the similar variables across study waves using the variable cascade

CLOSER organises Groups (i.e. CLOSER LPS) which contain several StudyUnits (i.e. LPS waves) of DataCollections of survey Instruments (i.e. questionnaire) which contain QuestionConstructs. 
The longitudinal variable relationships across LPS waves can be described using the variable cascade. Each InstanceVariable within a DataFile with the same underlying concept (e.g regular smoking, see figure below) references a ConceptualVariable. Therefore, each ConceptualVariable is a representation of the longitudinal variable which has been repeated at least once across LPS waves. RepresentedVariables do not need to be specified and so these will not be included in order to reduce the overhead. 
This solution will allow researchers to see all instances of where that concept was measured organsied by which are ordered by the TemporalCoverage.
Example – Longitudinal variable ‘Respondent has regularly smoked cigarettes’ within ALSPAC LPS
Group: ALSPAC
ConceptualVariable: Respondent has regularly smoked cigarettes

QuestionText: Which of the following have you ever smoked regularly? Cigarettes
InstanceVariable label: J1c1: Respondent has regularly smoked cigarettes
StudyUnit: ALSPAC Childhood (5 years to 12 years 11 months)

QuestionText: Which of the following have you ever smoked regularly? Cigarettes
InstanceVariable label: G2c1: Respondent has ever smoked cigarettes regularly
StudyUnit: ALSPAC Childhood (5 years to 12 years 11 months)

##Problem – Across Study: Researcher needs to find similar variables across longitudinal population study (LPS) for potential harmonisation. 
##Potential DDI solution - Create relationships between the similar variables across study waves using the variable cascade plus additional grouping.
Each LPS ConceptualVariable within a Group (LPS) which has a similar underlying concept (e.g ever smoked, see figure below) can be grouped together into a conceptual variable group.
Example – Ever smoked conceptual variable group with longitudinal variables from ALSPAC and NSHD LPS
Groups: ALSPAC and NSHD
Conceptual variable group: Ever smoked

QuestionText: Have you ever smoked as much as one cigarette per day for as long as a year?
InstanceVariable label: Have you ever smoked as much as 1 cigarette/day?
StudyUnit: 1982 (Age 36)

QuestionText: Have you ever smoked cigarettes regularly, by which I mean at least one cigarette a day for 12 months or more?
InstanceVariable label: Have you ever smoked cigarettes regularly: at least one cigarette a day for 12 months or more? 
StudyUnit: 1999 (Age 53)

