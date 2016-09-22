# Salesforce-Formulas-Collection
---
##### Formula: Set Expiration Date for a record (One Year later and last Day of the Month)
```
TEXT(DATE(YEAR(DATEVALUE(CreatedDate)) +1, MONTH(DATEVALUE(CreatedDate)) + 1, 1) - 1)
```
```
Result:  IF CreatedDate = 15/12/2016 THEN Your_Custom_Field__c = 31/12/2017
```
---
##### Formula: Returns the number of business days between two dates (Week_Start_Date__c and Week_End_Date__c)
```
CASE(MOD( Week_Start_Date__c - DATE(1985,6,24),7), 
0 , CASE( MOD( Week_End_Date__c - Week_Start_Date__c ,7),1,2,2,3,3,4,4,5,5,5,6,5,1), 
1 , CASE( MOD( Week_End_Date__c - Week_Start_Date__c ,7),1,2,2,3,3,4,4,4,5,4,6,5,1), 
2 , CASE( MOD( Week_End_Date__c - Week_Start_Date__c ,7),1,2,2,3,3,3,4,3,5,4,6,5,1), 
3 , CASE( MOD( Week_End_Date__c - Week_Start_Date__c ,7),1,2,2,2,3,2,4,3,5,4,6,5,1), 
4 , CASE( MOD( Week_End_Date__c - Week_Start_Date__c ,7),1,1,2,1,3,2,4,3,5,4,6,5,1), 
5 , CASE( MOD( Week_End_Date__c - Week_Start_Date__c ,7),1,0,2,1,3,2,4,3,5,4,6,5,0), 
6 , CASE( MOD( Week_End_Date__c - Week_Start_Date__c ,7),1,1,2,2,3,3,4,4,5,5,6,5,0), 
999) 
(FLOOR(( Week_End_Date__c - Week_Start_Date__c )/7)*5)
```
```
Result:  IF Week_Start_Date__c = 18/09/2016 AND Week_End_Date__c = 26/09/2016 THEN Your_Custom_Field__c = 6
```


