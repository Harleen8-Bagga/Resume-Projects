
# Credit Risk Analysis 

Credit analysis is a type of financial analysis that an investor or bond portfolio manager performs on companies, governments, municipalities, or any other debt-issuing entities to measure the issuer's ability to meet its debt obligations. Credit analysis seeks to identify the appropriate level of default risk associated with investing in that particular entity's debt instruments.

To judge a customer’s ability to pay its debt, banks, bond investors, and analysts conduct credit analysis on the company. Using financial ratios, cash flow analysis, trend analysis, and financial projections, an analyst can evaluate a firm’s ability to pay its obligations. A review of credit scores and any collateral is also used to calculate the creditworthiness of a customer.

The outcome of the credit analysis will determine what risk rating to assign the debt issuer or borrower. The risk rating, in turn, determines whether to extend credit or loan money to the borrowing entity and, if so, the amount to lend.


## Project objectives

The primary aim is to understand which are the factors that are effecting more the probability of having an high credit risk of a given customer, and build models capable to predict (given some features) the credit risk level.

## Dataset

```
- SeriousDlqin2yrs                      :	Person experienced 90 days past due delinquency or worse
- RevolvingUtilizationOfUnsecuredLines  :	Total balance on credit cards and personal lines of credit except real estate and no installment debt like car loans divided by the sum of credit limits 
- age                                   :	Age of borrower in years
- NumberOfTime30-59DaysPastDueNotWorse	:   Number of times borrower has been 30-59 days past due but no worse in the last 2 years
- DebtRatio	                            :   Monthly debt payments, alimony,living costs divided by monthy gross income
- MonthlyIncome	                        :   Monthly income
- NumberOfOpenCreditLinesAndLoans	    :   Number of Open loans (installment like car loan or mortgage) and Lines of credit (e.g. credit cards)
- NumberOfTimes90DaysLate	            :   Number of times borrower has been 90 days or more past due
- NumberRealEstateLoansOrLines	        :   Number of mortgage and real estate loans including home equity lines of credit
- NumberOfTime60-89DaysPastDueNotWorse	:   Number of times borrower has been 60-89 days past due but no worse in the last 2 years
- NumberOfDependents	                :  Number of dependents in family excluding themselves (spouse, children etc.)



```

## Performance Analysis

```
1. LogisticRegression :
- Train AUC Score       :  0.6972364
- Validation AUC Score  :  0.6972798

2. Logistic regression + removing outliers :
- Train AUC Score      :  0.8058389
- Validation AUC Score :  0.8017131

3. Logistic regression + removing outliers + treating multi-collinearity
- Train AUC Score      :   0.7920906
- Validation AUC Score :   0.7893644





```