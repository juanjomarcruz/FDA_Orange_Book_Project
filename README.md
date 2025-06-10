# Healthcare Data Analysis Project: Patents & Exclusivities

<img src="0_Images/FDA_sign.jpg" alt="FDA" width="900">

## Description

In this Healthcare Data Analysis Project, I've analyzed a dataset from the **FDA Orange Book**, a database published by the U.S. Food and Drug Administration (FDA) which provides information on FDA-approved drug products, therapeutic equivalences between innovators & generic drugs, patents & market exclusivities.

The analysis has focused on gaining insights on **Patents and Exclusivities**: Which has been the patent submission trend over the last years? Which are the firms holding the highest number of patents? Which exclusivities are typically granted together?

Addresing these kind of questions is crucial to have a more deep understading of current drug competition in the US market and regulatory incentives granted by the FDA to foster drug development and accessibility.

## Objective

To deliver a **powerful tracking tool** for assisting business strategists, regulators & market researchers in monitoring **FDA drug approvals**, **drug competition within the US market** and **FDA-granted incentives** in the pharmaceutical industry.

## Structure

```bash
FDA_Orange_Book_Project/
├── 0_Images/ #contains the images used for the project's README and dashboard.
│   ├── dashboard_1.png
│   ├── dashboard_2.png
│   ├── dashboard_3.png
│   ├── dashboard_4.png
│   ├── drug_products.png
│   ├── FDA_logo.png
│   ├── FDA_sign.png
│   ├── help.png
│   └── patent.png
│
├── 1_Data/
│   └── Data_Raw/ #includes only the raw data, without transformations or cleanage.
│   │   ├── exclusivity_raw.txt
│   │   ├── patent_raw.txt
│   │   ├── patent_use_codes_raw.xlsx
│   │   └── products_raw.txt
│   │
│   └── Data_Transformed/ #includes data cleaning and transformations.
│   │   ├── exclusivity_tr.xlsx
│   │   ├── patent_tr.xlsx
│   │   └── products_tr.xlsx
│   │
│   └── Metadata/ #includes additional info on data to give context.
│      ├── Column_Definitions.docx #column definitions for each table (products, patents and exclusivities) together with pre-analysis notes on columns.
│      ├── Exclusivities_Explanation.docx #explanations on how exclusivities can complement patents.
│      ├── FDA_Issue_Patents_Exclusivities.pdf #FDA document on Patents & Exclusivities.
│      └── FDA_PPT_Exclusivities.pdf #FDA PowerPoint with more explanations and examples on Exclusivity types.
│
├── 2_Jupyter_Notebooks/
│   └── 2_1_Data_Processing/ #includes data cleaning & transformation of each table using python data processing libraries: numpy & pandas.
│   │   ├── pre_analysis_cleaning_transformation_ex.ipynb
│   │   ├── pre_analysis_cleaning_transformation_pat.ipynb
│   │   └── pre_analysis_cleaning_transformation_prod.ipynb
│   │
│   └── 2_2_Exploratory_Data_Analysis/ #includes exploratory data analysis of each table using python visualization libraries: matplotlib & seaborn.
│       ├── EDA_ex.ipynb
│       ├── EDA_pat.ipynbb
│       └── EDA_prod.ipynb
│
├── 3_Project_Notes/ #includes my personal notes with my initial planning, captured insights and dashboard design drafts.
│   ├── 3_1_Project_Planning.docx
│   ├── 3_2_Pre_Analysis_Clean_Transf_EDA_Notes.docx
│   └── 3_3_Dashboard_Design_Notes.docx
│
├── Dashboard_FDA.pbix #the project's deliverable.
└── README.md
```

## Dataset Columns

### Table 1: Products.txt

**1. Ingredient (string)**: The active ingredient(s) for the product. Multiple ingredients are listed in alphabetical order, separated by a semicolon.

**2. Dosage form; Route of Administration (string)**: The product dosage form and route, separated by a semicolon.

**3. Trade Name (string)**: The trade name of the product as shown on the labeling.

**4. Applicant (string)**: The firm name holding legal responsibility for the new drug application. Condensed to a maximum twenty-character unique string.

**5. Strength (string)**: The potency of the active ingredient. May repeat for multiple part products.

**6. New Drug Application Type (string)**: Type of drug application. "N" for innovator (NDA) and "A" for generic (ANDA).

**7. New Drug Application (NDA) Number (string)**: The FDA-assigned number to the application. Format is nnnnnn.

**8. Product Number (string)**: The FDA-assigned number to identify the application products. Each strength is a separate product. Format is nnn.

**9. Therapeutic Equivalence (TE) Code (string)**: Indicates the therapeutic equivalence rating of generic to innovator prescription products.

**10. Approval Date (date)**: The date the product was approved, in the format "Mmm dd, yyyy".

**11. Reference Listed Drug (RLD) (string)**: Indicates whether the product is an RLD, approved under section 505(c) of the FD&C Act.

**12. Reference Standard (RS) (string)**: Indicates whether the product is a reference standard used in bioequivalence studies.

**13. Type (string)**: Indicates the category of approved drugs. Format: RX (prescription), OTC (over-the-counter), DISCN (discontinued).

**14. Applicant Full Name (string)**: Full name of the firm holding legal responsibility for the application.

### Table 2: Patent.txt

**1. New Drug Application Type (string)**: Type of drug application. "N" for innovator (NDA) and "A" for generic (ANDA).

**2. New Drug Application (NDA) Number (string)**: The FDA-assigned number to the application. Format is nnnnnn.

**3. Product Number (string)**: The FDA-assigned number to identify the application products. Format is nnn.

**4. Patent Number (string)**: Patent numbers submitted by the applicant. Format is numeric.

**5. Patent Expire Date (date)**: The date the patent expires. Format is "MMM DD, YYYY".

**6. Drug Substance Flag (string)**: Indicates whether the patent claims the drug substance. Format is "Y" or null.

**7. Drug Product Flag (string)**: Indicates whether the patent claims the drug product. Format is "Y" or null.

**8. Patent Use Code (string)**: Code to designate a use patent for the approved indication or use of the drug product.

**9. Patent Delist Request Flag (string)**: Indicates whether the sponsor has requested the patent to be delisted. Format is "Y" or null.

**10. Patent Submission Date (date)**: Date the FDA received patent information. Format is "Mmm d, yyyy".

### Table 3: Exclusivity.txt

**1. New Drug Application Type (string)**: Type of drug application. "N" for innovator (NDA) and "A" for generic (ANDA).

**2. New Drug Application (NDA) Number (string)**: The FDA-assigned number to the application. Format is nnnnnn.

**3. Product Number (string)**: The FDA-assigned number to identify the application products. Format is nnn.

**4. Exclusivity Code (string)**: Code indicating the type of exclusivity granted by the FDA.

**5. Exclusivity Date (date)**: The date the exclusivity expires. Format is "MMM DD, YYYY".

## Which steps did I follow?

### 1. Pre-Analysis

In order to come up with insightful questions to answer when analysing the dataset it was crucial to understand all data fields. For that reason, I first revised the metadata provided by the FDA where I made some notes and pointed out interesting questions to answer.

### 2. Data Cleaning and Transformation

The next step was to dive into the dataset. To explore the dataset I opted to use pandas, a python library very useful for data manipulation. Some of the cleaning and transformations I applied:

- Column names standarization.
- Data types correction.
- Duplicates removal.
- Filling null values.
- Creation of conditional columns to label data.
- Columns splitting.
- Mapping column values (Patent Use Codes, Exclusivity Codes) with associated definitions using dictionaries.
- Turning column values into more comprehensive ones with string manipulation functions.

### 3. Exploratory Data Analysis (EDA):

Once I had cleaned and transformed the dataset, I performed univariate and multivariate analysis on numerical, categorical and date columns. For this aim, I chose the most popular data visualization libraries in python: matplotlib and seaborn. While I was performing this task, I gathered the extracted insights in the Word file 3_2_Pre_Analysis_Clean_Transf_EDA_Notes.docx.

### 4. Interactive Dashboard:

Finally, I successfully developed an interactive dashboard that presents key performance indicators and clear, insightful visualizations, offering an at-a-glance view of critical data. As the final deliverable of the project, the dashboard enables business strategists, regulators, and market researchers to quickly identify trends in FDA drug product applications, generic drug competition in the US market, and FDA exclusivity grants. This powerful monitoring tool equips pharmaceutical stakeholders to take the temperature of the US market, understand its dynamics, and orient or refine their strategies.

## Main Insights

**1.** The number of FDA-approved drug products (46,050) is nearly double the number of FDA drug applications (26,122), indicating that grouping multiple drug products under a single application is a common practice. Frequently, applicants include **different strengths of the same drug in one application**. In other cases, a product may consist of **multiple components**—for example, a vial containing powder and a separate diluent used for reconstitution.

**2.** Today, generic drug products represent approximately 80% of the total US market. To reach this level, unlike New Drug Applications (NDAs), the number of **Abbreviated New Drug Application (ANDA) submissions has increased sharply since 2000**. In that year, generic applications already doubled the number of innovator applications. Twenty-four years later, **generic applications are eight times more common**, while NDA submissions have remained relatively stable at around 100 per year. **A key driver of this rapid growth in the generic drug market has been the FDA’s strong regulatory strategy**, supported by targeted policies aimed at encouraging generic drug manufacturing and improving market accessibility. Some of these policies include the **Generic Drug User Fee Amendments (2012)** or **The Drug Competition Action Plan (2017)**.

**3.** The **Top Applicants** in terms of number of FDA-approved drugs are the following: the **innovator Rx drugs market** in the US is lead by Baxter Healthcare Corp. (227), Pfizer Inc. (141) and Hospira Inc. (131).In fact, the latter was adquired by Pfizer so, in real terms, **Pfizer Inc. holds the first place**. As regards the innovator OTC drugs US market**, it is lead by Haleon US Holdings LLC. On the other hand, **the first position in the generic drug US market for both Rx and OTC is Aurobindo Pharma LTD, an indian company settled in Hyderabad.

**4.** In both the generic and innovator markets, **tablets and injectables rank first and second, respectively, among dosage forms**. This is likely due to their well-established, standardized, and scalable manufacturing processes. Tablets remain the most common form for new drug development, primarily because they face fewer regulatory and technological hurdles during production. However, one key question arises: **Will the dominance of tablets come to an end? As companies gain the necessary expertise and technology—and in light of recently updated regulatory requirements—will they shift more decisively toward injectables?**

5. Levothyroxine sodium, commonly used for the lifelong treatment of hypothyroidism—a condition affecting approximately 5% of the global population—is currently the most widely used active pharmaceutical ingredient (API) among innovator prescription drugs. This reflects how **pharmaceutical markets have traditionally been structured around chronic diseases. However, with the growing emergence of innovative gene therapies, this trend may be approaching its end. Sooner rather than later, conventional "quick-fix" treatments for chronic endocrine disorders may no longer represent a sustainable or attractive business opportunity**.

**6.** The generic Rx market is governed either by pregabalin or amphetamine-based drugs, both of which directly target the central nervous system (CNS). While pregabalin is commonly used to treat seizures, neuropathic pain, and generalized anxiety disorder, various combinations of amphetamines are widely prescribed to manage Attention Deficit Hyperactivity Disorder (ADHD). The **dominance of mature molecules like pregabalin and amphetamines reveal the high prevalence of CNS-related disorders and suggests that the market may be saturated in standard formulations, however, business oportunities may be found in innovative formulas**.

**7.** As of June 9, 2025, **the top applicant by number of active patents is Axsome Therapeutics Inc., with 119 active patents. Nearly all of them are associated with NDA 215430 for Auvelity**, an oral extended-release tablet combining dextromethorphan and bupropion for the treatment of Major Depressive Disorder (MDD). This extensive patent portfolio reflects the company’s strong strategic effort to protect Auvelity from potential competitors in the U.S. market. **As the first rapid-action oral drug approved specifically for MDD, Axsome anticipated significant commercial success and secured an estimated 13-year patent protection period to maximize market exclusivity**. It is clear that promising drugs need to be protected to guarantee return of the investment.

**8.** **The top Market Exclusivity by number of active eclusivities is the Orphan Drug exclusivity**, a 7-year market protection which is granted when a drug is developed to treat a rare disease or condition affecting fewer than 200,000 people annually in the U.S. This is a great new and **reflects the great success of FDA regulatory policies in terms of innovator's market protection and care for rare diseases**: in the past, rare diseases were not therapeutically covered because of the high risk of clinical and economic failure due to small target populations. Nowadays, thanks to market exclusivity grants, the risk of economic failure gets reduced and pharmaceutical companies have more incentives to develop orphan drugs.

**9.** **Orphan Drug and Pediatric Market Exclusivities are the ones that appear together the most, with 978 appearances**. This could be due to the fact that many rare diseases manifest during childhood, making pediatric populations a primary target for orphan drug development. Additionally, **companies pursuing orphan indications often conduct pediatric studies to qualify for the 6-month pediatric exclusivity extension**, further strengthening their market position. This strategy is both common and effective, **representing a regulatory success for the FDA where both stakeholders — patients and pharmaceutical companies — benefit**.

## Author

- Juanjo Martínez Cruz [LinkedIn](https://www.linkedin.com/in/juan-jose-mt-cruz)

## Contributions

Do not hesitate to contact me if you want to contribute to this project. I will be glad to open any discussion on my [LinkedIn](https://www.linkedin.com/in/juan-jose-mt-cruz) profile.

## The Project's Deliverable

<img src="0_Images/dashboard_1.png" alt="Dashboard" width="900"/>

<img src="0_Images/dashboard_2.png" alt="Dashboard" width="900"/>

<img src="0_Images/dashboard_3.png" alt="Dashboard" width="900"/>

<img src="0_Images/dashboard_4.png" alt="Dashboard" width="900"/>
