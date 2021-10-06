### Project Proposal of Business Project
Chien Yuan Chang
#### Question/need:
I am going to deliver a well-scoped project proposal and preliminary analysis to a struggling nursing home with low occupation rate to let them understand and accept how data science can help them increase the occupation rate.

>* What is the framing question of your analysis, or the purpose of the model/system you plan to build? 
>* Who benefits from exploring this question or building this model/system?

#### Data Description:
* Dataset: 
  * Data Source: [Nursing Homes Including Rehab Services - Provider Information](https://data.cms.gov/provider-data/dataset/4pq5-n9py) on [Centers for Medicare & Medicaid Services](https://www.cms.gov/)
  * Description: General information on currently active nursing homes, including number of certified beds, quality measure scores, staffing and other information used in the Five-Star Rating System. Data are presented as one row per nursing home.
  * Data size: 15266 rows with 88 columns

* An individual sample/unit of expected characteristics/features to work with (33 columns): 

Column Name|Sample Value
---:|---:
Federal Provider Number|15010
Provider Name|COOSA VALLEY HEALTHCARE CENTER
Provider Address|260 WEST WALNUT STREET
Provider City|SYLACAUGA
Provider State|AL
Provider Zip Code|35150
Provider County Name|Talladega
Ownership Type|For profit - Corporation
Number of Certified Beds|85
Average Number of Residents per Day|71.4
Average Number of Residents per Day Footnote|Medicare and Medicaid
Provider Type	Provider Resides in Hospital|N
Date First Approved to Provide Medicare and Medicaid Services|1/1/67
Continuing Care Retirement Community|N
Abuse Icon|N
Most Recent Health Inspection More Than 2 Years Ago|Y
Provider Changed Ownership in Last 12 Months|N
Overall Rating|4
Health Inspection Rating|3
QM Rating|4
Long-Stay QM Rating|2
Short-Stay QM Rating|5
Staffing Rating|5
RN Staffing Rating|5
Rating Cycle 1 Standard Survey Health Date|6/13/19
Total Weighted Health Survey Score|18.667
Number of Facility Reported Incidents|0
Number of Substantiated Complaints|0
Number of Citations from Infection Control Inspections|0
Number of Fines|1
Total Amount of Fines in Dollars|650
Number of Payment Denials|0
Total Number of Penalties|1

>* What dataset(s) do you plan to use, and how will you obtain the data?
>* What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?
>* If modeling, what will you predict as your target?

#### Tools:
* Microsoft Excel or Google Sheets for exploratory data analysis
* Tableau for data visualization

>* How do you intend to meet the tools requirement of the project? 
>* Are you planning in advance to need or use additional tools beyond those required?

#### MVP Goal:
* Complete the components of the proposal below
    *  Impact hypothesis
        *  Increase the occupation rate
    *  Solution paths: (pick one) other are options
        *  Build a model to interpret the factor of the occupation rate
    *  Measures of success: 
        * Adjust R-squared is above 0.6
    *  Risks and assumptions: 
        *  Marketing effort and local environment
        *  The quality ratings are related to the occupation rate
* Some charts of the preliminary analysis

>* What would a minimum viable product (MVP) look like for this project?