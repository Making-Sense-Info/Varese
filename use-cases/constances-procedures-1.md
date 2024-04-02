# Constances use case on cleaning procedure for the DDI representation of variables in repetitive contexts
*Constances is a "general purpose" population-based epidemiological cohort. It is a nationally representative sample of 200,000 adults aged between 18 and 69 (at inclusion). This epidemiological cohort is designed to contribute to the development of epidemiological research and provide information for public health purposes.*

*People who have agreed to take part in Constances receive a self-administered questionnaire (let's name it "questionnaire at inclusion"). A medical questionnaire asked by the doctor (intermediary) is also completed as part of inclusion process. A follow-up questionnaire is sent annually to Constances volunteers, and comprises a common core and questions that vary from year to year (named follow-up questionnaire code named F-yyyy where yyyy corresponds to the year).*

*The data collected via this protocol is then cleaned before being made available to the scientific community.*

## General description
After collecting raw data via questionnaire, data is cleaned according to a procedure/formula. A new variable is then created following the procedure definition. For different reasons (mostly for fixing errors), a cleaning procedure can be updated. In that case, the new cleaning method is applied for each variable collected over time, over questionnaires.

## Sources and variables
Let's consider a collected variable named "var1" and the related cleaned variable named "var1_n". The original procedure "if value for _var1_ is missing then _var1\_n_ = "0"" changed to "if value for _var1_ is missing then _var1\_n_ = "999"".

## What do we want to represent?
We want to represent the changes in the cleaning procedure definition over time. Each updated procedure has to be attached to the all variables _var1_ collected over time.

## Precise example in pseudo-DDI