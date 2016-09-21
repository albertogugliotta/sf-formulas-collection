# Salesforce-Formulas-Collection

###### Set Expiration Date for a record (One Year later and last Day of the Month)
```
TEXT(DATE(YEAR(DATEVALUE(CreatedDate)) +1, MONTH(DATEVALUE(CreatedDate)) + 1, 1) - 1)
```

