# Pwc-Diversity-and-Inclusion-Data-Analysis
For the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.

# Click on the link to view the Dashboard :
https://app.powerbi.com/view?r=eyJrIjoiNmJmYTczOWYtYzA0Ny00OThjLTk5NWYtMmRkM2YyNDBjYTk1IiwidCI6IjQ5NmE3ZmFlLTM0ZmUtNDJmNS1iNjYzLTc3MjFlNmZhYzA0MCJ9

# Problem Statement :
Define proper KPIs in hiring, promotion, performance and turnover
Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.

# Data Preparation
Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.
Data Cleaning for the dataset was done in power query as follows:
Unnecessary columns were removed
Unnecessary rows were filtered
Each of the columns in the table were validated to have the correct data type

# Data Visualization
Data visualization for the dataset was done in 2 folds using Microsoft Power BI Desktop:
The HR Manger (1/2) Page: Shows the hiring KPI, promotion KPI, Turnover Rate (FY20 leavers) KPI, e.t.c
The HR Manger (2/2) Page: Shows the Performance rating KPI, Executive Gender Balance KPI, Age Group KPI, e.t.c

# Data Analysis
Measures used in visualization are:

'#' of leavers =  CALCULATE(COUNTA('HR Manager'[Employee ID]), 'HR Manager'[Leaver FY] IN { "FY20" })

'#' of men =  Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male"))

'#' of women =  Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female"))

% employees promoted (FY21) = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Promotion in FY21?]="Yes")),Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for Promotion FY21]="Yes")))

% of hires men = Divide('HR Manager'[# of men],('HR Manager'[# of men]+'HR Manager'[# of women]))

% of hires women =  Divide('HR Manager'[# of women],('HR Manager'[# of women]+'HR Manager'[# of men]))

% Promotees who were men = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male")),distinctcount('HR Manager'[Employee ID]))

% Promotees who were women = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female")),distinctcount('HR Manager'[Employee ID]))

% Turnover = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager',NOT('HR Manager'[Department @01.07.2020]=BLANK()))),2))

Avg Rating Men = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Male"))

Avg Rating Women = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Female"))

# Insights
It can be deduced that:
41% of hires were female
59% of hires were male
53.8% of promotees were women in the Junior Officer category, the highest for the year
Avg Rating women 2.42%
Avg Rating women 2.41%
The most common age group is 20-29 having 215 employees fall in this category

# Data Visuals :

![image](https://github.com/Ushashree441997/Pwc-Diversity-and-Inclusion-Data-Analysis/assets/69711495/7db25f49-970a-4013-9617-4dbc3f27a246)
![image](https://github.com/Ushashree441997/Pwc-Diversity-and-Inclusion-Data-Analysis/assets/69711495/0795185a-7597-48b0-b99e-976a78a21e6e)

