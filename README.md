# BUSINESS_INSIGHTS - 360
My First Power BI Project.
## Project Overview : 
 AtliQ Hardware a consumer goods electronics company having operations in various countries. Their business is growing rapidly and they still rely on excel files for data analytics. Excel files are hard to consume and not effective in generating insights. Due to the lack of effective analytics the company faced a major loss in Latin America.
Thus, senior executives of this company have decided to invest in a data analytics project and have assigned a team for this work.

I had completed this project by following the Codebasics PowerBI Course. You can check the course [here](https://codebasics.io/courses/power-bi-data-analysis-with-end-to-end-project).
## Technology Implemented 
- Project Charter (Mural)
- SQL
- Excel
- Power BI Desktop
- Power Query M Language
- DAX Language
- DAX Studio for report optimization
## Key PowerBI Learnings
- What are the questions that should be asked before starting the project? (Understanding the scope of the project)
- Validating Data using Benchmark Numbers
- Using Data Catalog to browse through the list of databases available in the company
- Quick Data Exploration using basic SQL queries.
- Creating & Enhancing Visuals using Rough Sketches provided by the stakeholders
- Using Power Query for Data transformation
- Creating a Dimension(date) table using M language
- Creating calculated columns
- Best approaches to create calculated columns using Power Query or DAX for performance optimization
- Preventing Zero errors using DIVIDE function
- Concept of normalization and denormalization of tables
- Query Folding techniques
- Data Modeling (Concept of Star & Snowflake Schema, Cardinality etc)
- Verifying numbers using table/matrix visual(A simple yet effective way)
- Concept of Filter Context
- Preparing Pseudo Code for Efficiently Creating DAX Measures
- Creating Toggle Switch Using Slicer
- Switching between two visuals using bookmarks
- Creating Buttons for Page navigation
- Effectively using KPI indicators
- Using Conditional Formatting for values in visuals
- Power BI Serivce
     - Publishing Reports
     - Setting up personal gateway for auto refresh of data
     - Collaboration, workspace, and Access permissions
- Contingency plan for discrepancy in reports
## Key Business Metrics
 - Gross Price (GP)
 - Pre-invoice Deductions
 - Post-Invoice Deductions
 - Net Invoice Sale (NIS)
 - Gross Margin (GM)
 - Net Sales (NS)
 - Net Profit (NP)
COGC - Cost Of Goods Sold
YTD - Year To Date
YTG - Year To Go
Direct
Retailer
Distributors
Consumer
 ## About Company
AltiQ hardware is a company which has grown vastly in the recent years, and opened business all over the globe. It is a company which sells, computer and computer accessories through three mediums/channel
 - Retailers
 - Direct
 - Distributors

Recently the company has faced a unforeseen loss by opening store in America based on the surveys, intuition and some excel analysis and also the company’s competitors has handful of analytics team to perform analysis and make data driven decision. So, the AltiQ hardware has no other option other than building their analytics team for data driven insights and decisions in the future to survive competitively in the industry.
## Things to consider before starting to build the project
Sometimes business managers may give a data analyst a very rough requirements for the projects. Then its a responsibility of a data analyst to ask counter questions and to clarify requirements. So its better to clarify things first, rather than asking them later! Thus we will be able to set realistics expectations. Last but not the least, a data anaylyst has to be very upfront and clear - For e.g., While working on the project a data analyst will not allow too many changes in the report (Feature Creep).
 ### Questions to be asked before the project gets started - 
- What is the primary objective for building this Power BI report ?
- What are the hopes & fears (expectations) does stakeholders have for this project ?
- What is project deadline ?
- What problem are we trying to solve ?
- How the success of this project will be measured ?
- What are the risks involved in creating this project ?
- Additional resources required for buidling the report ?
- Who are all will be using this dashboard and for what purpose?
- Is there any feedback from stakeholders on the design and views of the dashboard?
### Discovering Datasets
Lets get a good understanding of data provided. Before we proceed further for analysis.

Dimension table : This table contains the static data like details of customers and products. Dimension tables contain descriptive attributes that provide context for the facts in the fact table.  
Fact table : It will have the data about the transactions. Fact tables store quantitative data like sales, cost, and profit.

  - gdb041:
    - dim_customer
      - **27** distinct markets (e.g India, Australia, Spain)
      - **75** distinct customers thorough out the market
      - **2** types of platforms
        - Brick & Mortars - Physical/offline store
        - E-commerce - Online Store (Amazon, flipkart etc.)
      - Three channels
        - Retailer
        - Direct
        - Distributors
    - dim_market
       - **27** distinct markets (e.g India, Australia, Spain)
       - **7** subzones 
       - **4** regions
          - APAC 
          - EU
          - NAN
          - LATAM
     - dim_product
       - Divisions
        - P & A
          - Peripherals
          - Accessories
        - PC
          - Notebook
          - Desktop
        - N & S
          - Networking
          - Storage
      - There are 14 different categories, Like Internal HDD, keyboard etc.
      - There are different variants available for the same product.
   - fact_forecast_monthly
     - This table is used to forecast the customer’s need in advance, which can help in
        - Higher customer satisfaction.
        - Reduced cost in warehouses for storage purpose.
     - The table is denormalized by data engineering team, as it is a data warehouse which is aimed to be used for analytical work.
    - All the date of the month will be replaced by the start date of the month.
    - It will have all the column names and in the end it will have the forecast quantity need of the customer.
   - fact_sales_monthly
     - This table is more or less is same as fact_forecase_monthly table, but the last column has the value of sold quantity instead of forecast value.
  

 - gdb056
   - freight_cost
      - This table has details of shipping and other cost for each market with fiscal year.
   - gross_price
      - Details of gross prices with product code.
   - manufacturing_cost
     - Details of manufacturing cost with product code with year.
   - Pre_invoice_dedutions
     - Details of pre invoice deductions percentage for each cutomer with year.
   - Post_invoice_deductions
     - Post invoice deductions and other deductions details.
### Importing Data to PowerBI
 - As the database is in MySQL for this project. We need to import the datasets from Mysql database to PowerBI by providing the Database access credentials using MySQL workbench.
### Data Model
 - Data modeling is important because it helps organize and structure data, which improves data quality, reduces errors, and improves performance.
 - For this project [Snowflake](https://en.wikipedia.org/wiki/Snowflake_schema) Schema has been followed. 
<img width="838" alt="Data_model" src="https://github.com/user-attachments/assets/8c5fd52d-8fa6-468a-a30c-09dc96a3f218" />

### Moving to Dashboard Designing
Mr. Nick Puri (Product Owner) has provided us with the visual mock ups. Based on which the data team will start designing the visuals and create measures as required.
Mock ups given are as follows -
 
<img width="838" alt="Finance_mockup" src="https://github.com/user-attachments/assets/b024fb1b-ff74-48db-b1b3-fe1188b0c636" />

<img width="838" alt="Sales_mockup" src="https://github.com/user-attachments/assets/1b34e214-7055-4ac9-90df-e8ebccc1a277" />

<img width="838" alt="Marketing_mockup" src="https://github.com/user-attachments/assets/854f957a-c12d-4a09-9101-541d22ad243f" />

<img width="838" alt="Supply_Chain_mockup" src="https://github.com/user-attachments/assets/61255c82-04c4-4383-8b1e-aae80dc25d7d" />

And after getting further feedback we also get another request to build an additional visual. Mockup is as follows - 

<img width="838" alt="Executive_mockup" src="https://github.com/user-attachments/assets/72ac172f-f687-4057-b5a3-57d4e22030e5" />

After long hours of hardwork. The Output - 

### Home View
In Home View all the buttons are available with brief details of the visuals. End user can access specific pages with the buttons provided.
 - Info
 - Support
 - Finance View
 - Sales View
 - Marketing View
 - Supply chain View
 - Executive View
 - Feature Request

**Note**: Feature Request is an another additional requirement given by Mr. Hariyali (Sales Director) for product analysis with specific requirements.
### Home, Information and Support View

<img width="838" alt="Home View" src="https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Resources/Home%2C%20Info%20and%20Support.gif" />

### Finance View
<img width="838" alt="Finance View" src="https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Resources/Fin%20View.gif" />

### Sales View
<img width="838" alt="Sales View" src="https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Resources/Sales%20View.gif" />

### Markeing View
<img width="838" alt="Marketing View" src="https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Resources/Marketing%20View.gif" />

### Supply Chain View
<img width="838" alt="Supply Chain View" src="https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Resources/Supply%20Chain%20View.gif" />

### Executive View
<img width="838" alt="Executive View" src="https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Resources/Executive%20View.gif" />

### Feature Request
<img width="838" alt="Feature Request" src="https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Resources/Feature%20Request.gif" />

### Conclusion 
This report can now be used to take several key decisions based on the insights found with data. This will help to answer not only to known problems. But can figure out problems which are not known and find optimal strategies to address them.
You can find the report [here](https://github.com/Suy27/BUSINESS_INSIGHTS---360/blob/main/Report/BI-360.pbix).





























 
 
