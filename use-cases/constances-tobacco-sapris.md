# During Covid pandemic’s
- Constances complementary questionnaire was set-up (SAPRIS Study) 
- Only web participants for Sapris
- Among primary objectives: effect of tobacco on Covid symptoms 

# 1) tobacco exposure definition:  
- Never smoker (refe): never smoke before SAPRIS Study and declare on sapris (Do you currently smoke (=No) and Since the lockdown began, did your smoking habits changed (=No))
- Regular smoker: status before SAPRIS (=Smoker) and on SAPRIS ((Do you currently smoke (=Yes every day)) and 
  -	Since the lockdown began, did your smoking habits changed (=No)) 
  -	or Since the lockdown began, did your smoking habits changed (=Yes, Ismoke more)) 
-	Occasional Smoker: only on Sapris ((Do you currently smoke (=Yes occasionally))
-	Former-smoker:  smoker before Sapris study and declare on sapris (Do you currently smoke (=No) OR ex-smoker before Sapris study and declare on sapris (Do you currently smoke (=No) 
-	Other modalities: non-classified 
## On practice: 
- Constances variables before SAPRIS :
  - Inclusion: calculated variable (AQ_COMPORT_TcStatut_i) based on two variables 
    -	AQ_COMPORT_TcTabac : Have you ever consumed tobacco in your life?
    -	AQ_COMPORT_TcFumAct	If yes: Do you still smoke currently?
  -	Follow up : 
    -	AQ_COMPORT_TcActFume	Currently, do you smoke (excluding e-cigarettes)?
-	Constances-Sapris complementary questionnaire 
  -	Do you currently smoke (=No) (varsapTb1)
  -	Since the lockdown began, did your smoking habits changed (=No)  (varsapTb1)

# 2)	Smoking, length of time (years) since quitting for ex-smokers
-	Former-smoker on Tobacco exposure definition
-	Calculate the length of time 

## On practice 
Two additional Constances variables before used SAPRIS at inclusion
-	AQ_COMPORT_TcFumAct	If yes: Do you still smoke currently?
-	AQ_COMPORT_TcAgeFin	If no: (If you no longer smoke) At what age did you quit (last quit)?	Years

One additional Constances variables before used SAPRIS on follow-up (s)
- If former status = smoker and delaclared on follow up on the variable AQ_COMPORT_TcActFume	(Currently, do you smoke (excluding e-cigarettes)? (No)) :the year was took as reference 
- If former status = nonsmoker or ex-smoker and declared on follow up on the variable AQ_COMPORT_TcActFume	(Currently, do you smoke (excluding e-cigarettes)? (Yes)) and afterwood declared (No) :the year of first no was took as reference  
