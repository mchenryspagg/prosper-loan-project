# (Prosper Loan Data)

## Table of contents

- [Overview](#overview)
  - [Dataset](#dataset)
  - [Summary of data wrangling](#summary-of-data-wrangling)
  - [Research Questions](#research-questions)
  - [Links](#links)
  - [Built with](#built-with)
  - [Key Insights](#key-insights)
  - [Useful resources](#useful-resources)
- [Acknowledgments](#acknowledgments)

## Dataset

- This **[data set](https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv)** contains the customer's data from a fictional loan company known as **Prosper**. This dataset comprises of 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, and many others.

- Out of these 81 variables, the analysis was focused on just 17 variables of interest to help with answering the research questions. A new dataset with the variables of interest was created with a structure of 106312 observations and 17 features. 

- The loan dataset includes :

| categorical variables | quantitative variables |
| --------------------- | ---------------------- |
| ListingCreationDate | Term |
| LoanStatus | BorrowerAPR |
| ListingCategory | BorrowerRate 
| EmploymentStatus | LenderYield |
| IsBorrowerHomeowner | EmploymentStatusDuration |
| IncomeRange | StatedMonthlyIncome |
| IncomeVerifiable | LoanOriginalAmount |
| LoanOriginationDate | MonthlyLoanPayment |
| LoanOriginationQuarter |

 Two new variables were created during data wrangling namely 
 | new categorical variables |
 | -------------------- |
 | LoanOriginationMonth |
 | LoanOriginationYear |


## Summary of Data Wrangling

- The first step involved was gathering the Prosper loan data, after which we created a subset from the main dataset consisting of 17 variables and 106312 observations which we worked with. 

Data cleaning was then carried out on the new dataset created which involved : 
- _Converting ***EmploymentStatusDuration*** to integer_; 
- _Renaming ***ListCategory (Numeric)*** variable to ***ListCategory*** and its numeric values of 1-20 replaced with its categorical listing_;
- _***ListingCreationDate*** and ***LoanOriginationDate*** was converted to a datetime datatype_; 
- _***LoanStatus***, ***ListingCategory***, ***EmploymentStatus***, ***IncomeRange***, & ***LoanOriginationQuarter*** was also converted to category datatype_;
- _***IncomeRange*** categories was reordered to be in a set order_.

## Research Questions

- After the Data cleaning, we proceeded to define the main variables of interest with our research questions:
  1. Factors that affect a loan's outcome status.
  2. Factors that affects the borrower's APR or interest rate.
  3. Identifying if there are differences between loans depending on how large the original loan amount was?

## Links

### Solution URL: 

- [Jupyter notebook](./Part_I_exploration_loan.ipynb)

- [Kaggle notebook](https://www.kaggle.com/code/henryokam/prosper-loan-exploratory-data-visualization/notebook)

## Built with

- Jupyter Notebook
- Python
- Pandas, Numpy, seaborn, matplotlib, nbconvert.

## Key Insights

The main insights as listed are those which directly or indirectly answers the research questions as earlier portrayed looking at the univariate, bivariate and multivariate visualizations done during the data exploration. 

- A loan outcome status is affected by the loan ***Term*** which is the length of the loan. The Term of the loan however is dependent on the LoanOriginalAmount as smaller loan amounts get smaller loan Term and vice versa. 

- It was observed that loans with a  Term of 12 months had a higher rate of having a loan outcome status of ***completed***. 

- It was observed that higher loan original amounts are more prone to have a loan outcome status of Defaulted, or PastDue while lower loan amounts have a higher rate of having a loan outcome status of ***completed***.

- A loan's ***Term*** and its Original Amount will have a profound effect on the borrower's annual percentage rate (APR). Lower loan amounts of less than $10,000 and of a 12 month Term will have lower borrower Annual Percentage Rate.

- The progression of loans obtained across months of the year shows that higher loan amounts are gotten by borrowers in January and December than in other periods of the year, with June been the month with the lowest loan amounts given out on average.

- Borrowers with a yearly income range of $50,000 and above have access to the higher sizes of loans.
 
- Employed borrowers accessed higher loans sizes than borrowers who are not employed or work part-time.

- It was observed that the higher the loan original amount obtained, the higher the monthly loan payments.

- 2009 had a very low proportion of loans given out to borrowers which was likely due to low or no business activity within the first quarter of that year while 2013 had a very high proportion of loans given out.

- The highest percentage of loans across all years had a listing category of ***Debt Consolidation***. This connotes that the biggest reason why people take loans is mainly to pay off their other huge debts such as student loans, home equity loans etc.
...that's quite interesting and worrisome 🤔🤔🤔


### Useful resources

- [Pandas Documentation](https://pandas.pydata.org/pandas-docs/stable/reference/frame.html) - Pandas documentation to guide any student or researcher on best practices on pandas functions and methods.
- [Stack Overflow](https://stackoverflow.com/questions/25646200/python-convert-timedelta-to-int-in-a-dataframe) - A useful platform  to search for possible answers to questions.
- [Seaborn documentation](https://seaborn.pydata.org/generated/seaborn.countplot.html)
- [Matplotlib documentation](https://matplotlib.org/stable/plot_types/index.html)

## Acknowledgments
Special thanks to ALX - T and the entire ALG/ALX group and their sponsors for the sponsorship of this program and giving me the opportunity to be a beneficiary of the Udacity data analysis nanodegree program. Being able to complete a degree of this nature is a huge achievement. Special Thanks also to all the instructors and reviewers for their feedback and reviews. Also special thanks to my session lead whose weekly sessions has helped to make my learning more easier and better. And also to my colleagues for their support and encouragement.
