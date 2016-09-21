# Salesforce-Formulas-Collection

###### Set Expiration Date for a record (One Year later and last Day of the Month)
```
Formula: TEXT(DATE(YEAR(DATEVALUE(CreatedDate)) +1, MONTH(DATEVALUE(CreatedDate)) + 1, 1) - 1)
```
```
Result:  IF CreatedDate = 15/12/2016 THEN Your_Custom_Field__c = 31/12/2017
```


