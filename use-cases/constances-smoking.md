# Constances use case for the DDI representation of variables in repetitive contexts
*Constances is a "general purpose" population-based epidemiological cohort. It is a nationally representative sample of 200,000 adults aged between 18 and 69 (at inclusion). This epidemiological cohort is designed to contribute to the development of epidemiological research and provide information for public health purposes.*

*People who have agreed to take part in Constances receive a self-administered questionnaire (let's name it "questionnaire at inclusion"). A medical questionnaire asked by the doctor (intermediary) is also completed as part of inclusion process. A follow-up questionnaire is sent annually to Constances volunteers, and comprises a common core and questions that vary from year to year (named follow-up questionnaire code named F-yyyy where yyyy corresponds to the year).*

*The data collected via this protocol is then cleaned before being made available to the scientific community.*


## General description

In order to meet the requirements of researchers and various institutions using Constances data, a clear and precise description of the different available variables (at enrollment and follow-up) must be accessible. For this first use cases, we propose to focus on smoking-related data.
Researchers want to retrieve data about smoking-related data (?).

## Sources and variables

The complete list of variables for smoking status is available [here](./smoking-variables.md).


## What do we want to represent?

To better organize this data and facilitate decision-making, it is recommended to these variables in a standard DDI format. The detail of the variables available in the specific Excel table 
All described parts listed in the tables and also 
- Highlight comparable questions between inclusion and follow up
- Highlight participation (respondent) at each follow up
- Highlight the number on follow up wave for participants (median follow-up…) 

## Precise example in pseudo-DDI

Instrument: Inclusion
- Question: If yes: Do you still smoke currently? 
  - Instance variable: AQ_COMPORT_TcFumAct
- If yes: Indicate how many cigarettes per day on average?
  - Instance variable: AQ_COMPORT_TcCigtJNb

Instrument: Follow-up Instrument
- Question: Currently, do you smoke (excluding e-cigarettes)? --> AQ_COMPORT_TcActFume
- Question: If yes, how many do you smoke per day on average (cigarettes)?
  - Instance variable: AQ_COMPORT_TcCigtJNb
