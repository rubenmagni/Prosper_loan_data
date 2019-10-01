# INVESTIGATION OF PROSPER LOAN DATA

### by Ruben Magni

## Prosper Loan dataset overview

> Prosper is a personal loan pioneer in what is called peer-to-peer landing. Through the years it has originated billions of dollars in personal loans by matching borrowers to investors using its online platform. The Prosper Loan dataset contains all the information related to several types of loans issued across several years. These include information about the type of loan, amount, duration, interest etc., as well as information about the borrower such as income, credit range, employment status. Since the data were acquired across a relatively long period of time, some parameters changed or were introduced overtime. For example two different credit systems were used by Prosper, the first called 'Credit Grade' (before 2009) and 'Prosper Rating' (after 2009).

## Goal of the study

> In the following data exploration I will focus on understanding what are the borrower characteristic that facilitate the issue of a loan and what are the main indicators and how they associate to the risk of default.

> From an investor perspective the main features of the dataset are those which help predict the risk/reward ratio of a certain investment. Some of this characteristics pertain to the loan, others to the borrower.

> Main features of the loan:
1. Loan Status
2. Estimated Return

> Main feature of the borrower are:
1. Credit Grade (Score before 2009)
2. Prosper Rating (Score after 2009)
3. Income Range

> Several feature provide more insights to understand if a loan is more likely to be a good investment or not. Among those I chose the following for further analysis.
1. Term (Months of the loan)
2. Credit Range
3. Listing Category (reason for the loan)
4. Employment Status
5. Is borrower a homeowner
6. Monthly Payment
7. Monthly Income
8. Amount of the Loan

## Results from Univariate Exploration

In the Univariate analysis I explored variables which pertains to both the Loan itself and the Borrower in order to understand what are the characteristics that would produce a profitable investment for a lender.
Before the analysis I looked at inconsistences in the data. Some data were duplicated and Prosper Score had some inaccurate values. These rows were not included in the analysis.

1. The loans given by Prosper vary from 1000-35000 USD and the length from 12 to 60 months. Most of the approved loans are below 15000 USD and for a period of 36 months. The majority of monthly payments fall below 1K/month.

2. While the lender Yield varies a lot, the mean yield is around 18%. As expected the borrower APR which includes additional fee to the interest rate is higher than the lender yield but followes the same distribution.

3. Estimated Return is normally distributed and lower than the lender yield with a mean aorund 10%. This is probably because based on other features high yield loans might be associated with a higher risk/failure.

4. The majority of applicants have a annual income between 25K-75K and are working. This is also confirmed looking at the monthly income. As expected most of the borrowers have a job and only a very small percentage (0.8%) report no employment.

5. As far as credit the majority of the applicant fall between 660 - 740 which means a good to very good credit score according to the Credit Bureau. Prosper Score and Prosper Rating are the also and indicator of the risk which takes in consideration a few factors.

6. While several are the reason to ask for a loan, more than 60% of applicants are looking for debt consolidation. This is not surprising since credit card debt is very prevalent in the US.


## BIVARIATE ANALYSIS
In this part of the analysis I will investigate the relationship between two variables. My main focus is to understand how different variables contributes to risk/reward of the loan.

1. As a first main feature I wanted to investigate is the **loan status** and how that is affected by other features such as:

    a) **Prosper Score**. No linear correlation seems to emerge across the entire range of Prosper Socre, but it is evident that a Prosper Score of '1' (the worst) has the highest proportion of 'charged off' or 'defaulted' loans while a Prosper Score of '10' (the best) has the lowest proportion of 'charged off' or 'defaulted' loans. Prosper Score of '1' has also the lowest proportion of 'current' loans.

    b) **Credit Range**. The proportion of charged off loans decreases with an increase in credit score. Mid credit score seem to be associated with a low percentage of charged off loans and a high percentage of completed or current loans.

    c) **Borrower APR**. Normally a higher interest rate is charged to a riskier loan, as a result the number of past due, 'defaulted' and 'charged off' loans are higher with an increase of APR. In simple words a higher reward comes with an higher risk to the lender.

    d) **Lender Yield**. Lender Yield and Borrowe APR are highly correlated. A higher lender yield correlates with a larger number of 'defaulted' and 'charged off' loans.

    e) **Is Borrower a Homeowner** was also investigated in relation to loan status. It does not seem that owning a home can be used as an indication of the loan status.


3. As a second main feature of interest for a perspective lender is the **estimated return**:

    a) It is clear that a higher **Income** and a higher **Credit Score** are associated with a lower return. The reason is that these borrower can qualify for lower APR since their loan has a lower risk of defaulting.


    1. From Borrower perspective, it would be interesting to know how the **Debt to Income Ratio** affect the amount that can be borrowed and the monthly payment.

        a) **Monthly payments** do not seem to correlated with Debt to Income Ratio overall. Although large monthly payments are only observed with low Debt to Income Ratio. This is probably due to the fact that only people with low Debt to Income ratio can secure higher loans which translates in higher monthly payments.

        b) **Loan Original Amount** although no clear correlation is shown, it is clear that only people with lower Debt to Income ratio can obtain larger loans in support of what just stated above. As a side note a clear positive correlation is observed between Loan Original Amount and **Monthly Income**.


## MULTIVARIATE ANALYSIS

In this section I want to investigate how the combination of two variables affect a third variable. Because income and credit score are crucial in securing a loan, it would be interesting to see how the combination of these two variable affects the return of investment for a lender.

1. **Estimated Return**

a) It is evident that the combination of **higher income and credit score** is associated with a lower estimated return. This is because since the Borrower is more qualified the risk of defaulting is lower and so lower is the reward for the lender.

b) It is also evident that a combination between **higher income and higher prosper score** similarly to above correlates with a loan given a lower return on investment to the lender.

c) I then wanted to investigate if from a lender perspective lending to **homeowners** is associated to different estimated return compared to renters. It seems that with the same prosper score, homeowners are associated to a lower estimated return.

2. **Loan Status**

a) Loan status was studied in relation to the combination of **Borrower APR** and **Loan Term**. Defaulted and charged off loans are always associated with a higher APR no matter the term of the loan. Overall the APR ranges are similar in the different loan terms. Maybe a small difference that would require further investigation can be seen in the 60 months where the median APR for current, completed and charged off loans is lower compared to the other terms.

3. Since looking at the estimated return, a difference between **homeowners** and renters was observed, I decided to investigate if other features beyond the estimated return were distributed differently among homeowners and renters.

a) **Loan amount and credit score**. The higher the credit score, the higher is the loan amount that can be obtained. Across the different credit score homeowners seem to obtain higher loans compared to renters.

b) **Loan amount and income**. The higher the income, the higher the loan amount that can be obtained. Across different income ranges homeowners seem to obtain higher loans compared to renters.

c) **Debt to income ratio and income**. Debt to income ratio decreases when the income increases. Across different income ranges homeowners seem to display a higher debt to income ratio compared to renters.


## Conclusions

The main focus of the study was to analyze features that could help a lender to invest in a loan. This required an analysis of Loan structure (term, orginal, amount, APR etc.), and Borrower qualities (Income Range, Credit Range, Debt to Income Range, etc.). Looking at these variables individually or in combination may provide the lender additional tool to make an informed decision to better invest his capital.
