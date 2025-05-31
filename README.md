# Healthcare Data Analysis Project: Patents & Exclusivities

<img src="0_Images/FDA_sign.jpg" alt="FDA" width="900">

## Description

In this Healthcare Data Analysis Project, I've analyzed a dataset from the **FDA Orange Book**, a database published by the U.S. Food and Drug Administration (FDA) which provides information on FDA-approved chemical drugs, therapeutic equivalences between innovators & generic drugs, patents & market exclusivities.

The analysis has focused on gaining insights on **Patents and Exclusivities**...Which has been the patent submission trend over the last years? Which are the firms holding the highest number of patents? Which exclusivities are typically granted together?

Addresing these kind of questions is crucial to have a more deep understading of current drug competition in the US market and regulatory incentives granted by the FDA to foster drug development and accessibility.

## Objective

To deliver a **powerful tracking tool** for assisting business strategists, regulators & market researchers in monitoring **FDA drug approvals**, **drug competition within the US market** and **FDA-granted incentives** in the pharmaceutical industry.

## Structure

```bash
FDA_Orange_Book_Project/
├── 0_Images/ #contains the images used for the project's README and dashboard.
│   ├── dashboard.png
│   ├── drug_products.png
│   ├── FDA_logo.png
│   ├── FDA_sign.png
│   ├── help.png
│   └── patent.png
├── 1_Data/
│   └── Data_Raw/ #includes only the raw data, without transformations or cleanage.
│   │   ├── exclusivity_raw.txt
│   │   ├── patent_raw.txt
│   │   ├── patent_use_codes_raw.xlsx
│   │   └── products_raw.txt
│   └── Data_Transformed/ #includes data cleaning and transformations.
│   │   ├── exclusivity_tr.xlsx
│   │   ├── patent_tr.xlsx
│   │   └── products_tr.xlsx
│   └── Metadata/ #includes additional info on data to give context.
│      ├── Column_Definitions.docx #column definitions for each table (products, patents and exclusivities) together with pre-analysis notes on columns.
│      ├── Exclusivities_Explanation.docx #explanations on how exclusivities can complement patents.
│      ├── FDA_Issue_Patents_Exclusivities.pdf #FDA document on Patents & Exclusivities.
│      └── FDA_PPT_Exclusivities.pdf #FDA PowerPoint with more explanations and examples on Exclusivity types.
├── 2_Jupyter_Notebooks/
│   └── 2_1_Data_Processing/ #includes data cleaning & transformation of each table using python data processing libraries: numpy & pandas.
│   │   ├── pre_analysis_cleaning_transformation_ex.ipynb
│   │   ├── pre_analysis_cleaning_transformation_pat.ipynb
│   │   └── pre_analysis_cleaning_transformation_prod.ipynb
│   └── 2_2_Exploratory_Data_Analysis/ #includes exploratory data analysis of each table using python visualization libraries: matplotlib & seaborn.
│       ├── EDA_ex.ipynb
│       ├── EDA_pat.ipynbb
│       └── EDA_prod.ipynb
├── 3_Project_Notes/ #includes my personal notes with my initial planning, captured insights and dashboard design drafts.
│   ├── 3_1_Project_Planning.docx
│   ├── 3_2_Pre_Analysis_Clean_Transf_EDA_Notes.docx
│   └── 3_3_Dashboard_Design_Notes.docx
├── FDA_Dashboard.pbix
└── README.md
```
