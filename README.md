# Analysis-of-Agents-in-the-Tractchun-company
Resume: Tractchun is a company in the manufacturing industry with Information Technology (IT) agents who support Tickets. Information has been requested from the Human Resources department in order to perform a more in-depth analysis based on classifications of their Agents.

To download the Power BI file: https://github.com/Lucas-F-Analysis/Analysis-of-Agents-in-the-Tractchun-company/raw/refs/heads/main/Tractchun%20Dashboards.pbix


![Vista previa del reporte](https://github.com/Lucas-F-Analysis/Analysis-of-Agents-in-the-Tractchun-company/raw/refs/heads/main/Tractchun%20GIF.mp4)

# Summary

## 📊 Overview
In this project, I carry out an exhaustive data analysis for the company Tractchun. Using the Power BI tool, using Power Query as the main data transformation tool. The situation involves the need to transform data from different support requests, called ‘Tickets’. These Tickets are associated to the Employees of the company that generated them, and to the IT Agents in charge of attending them.

## 🔍 Context
Case: Tractchun is a company in the manufacturing industry that has Information Technology (IT) agents who provide ticketing support for all aspects of their office technology (systems, hardware, software, etc.).

The manager of the IT team needs to monitor and review areas of improvement in their service and has extracted data from their ticketing system, and has also requested information from the Human Resources department in order to perform a deeper analysis based on their agent classifications.

## 🎯 Target
We must transform the data into actionable information for Power BI, then visualise it and extract important business performance information for strategic decision making, such as analysis of Agent performance over time, Feedback, KPI's, Days to Resolution, etc. 

## 🛠️ Tools Used
- **Power BI**: Dashboard design and data visualization.
- **DAX**: Data modeling and calculated measures.
- **Power Query**: Data cleaning and preparation.

## 📂 Files
- **`Tractchun Analysis.pbix`**: The Power BI file containing the dashboard.
- **`Support ticket table:`** created from the annexation of the different ticket tables from 2016 to 2020. These Tickets are requested by the company's employees. It includes feedback information on each service (classified from ‘Excellent’ to ‘Bad’), Category, Type, Severity, dates, priority, days of resolution.
- **`Detailed information about the Employees:`** including personal data of each one of them, such as names, surname, shift, email, plant to which they belong.
- **`Information on IT Agents:`** including first names, surnames, email, and date of birth.
- **`Job titles of each Employee in the company:`** detailing the job title, department and type of job.
- **`code/`**: DAX and M Query formulas.

## 🛠️ Data Preparation
1) Data Transformation and Data Cleaning Process:
I used different data transformation techniques in Power Query to ensure the integrity and quality of the information:

- Conditional columns and extraction of specific dates to facilitate temporal analysis.
- Combining and appending tables to structure data in a coherent way.
- Data cleansing including de-duplication, normalisation of alphanumeric values and case sensitivity, etc.
- Creation of additional tables:
    - "Calendar": created from the Tickets table, for precise time segmentation. 
    - "Days of Resolution": created from the Tickets table, to analyse the resolution time of the Tickets.
    - "Feedback table": independent table containing the ratings or feedback of each Ticket service.
    - "Employees + Posts": which is a combination of the Employees and Posts tables for consolidated information.

In addition, I used DAX language to create key metrics (KPIs) such as average satisfaction, tickets handled per agent, percentage of positive tickets (either ‘Excellent’ or ‘Very Good’) and average days to resolution.

2) Data Modelling
After the transformation, I performed relational modelling of the tables, setting up key relationships to ensure the model was ready for analysis in Power BI. This included setting up relationships between Employees, IT Agents, Resolution Days, Calendar and Tickets. This resulted in a snowflake model.

3) Data Visualisation
To interpret the data, I created a variety of charts, including:

Cards for key KPIs: total tickets, percentage of positive tickets (‘Excellent’ or ‘Very Good’ reviews), average satisfaction and average days to resolution.
Line graphs to see the monthly evolution of tickets.
Bar charts to classify tickets by support category (system, access/login, software, hardware).
Column charts to analyse the days of ticket resolution.
Donut graph to show the proportion of feedback on each agent's service.

In addition, I added filters by year, month and support agent, allowing a detailed analysis of the performance of each agent in a specific period.

4) Results and Conclusions
With the transformed and visualised data, significant insights can be extracted on Agent performance, identifying areas with higher support demand, response times and satisfaction levels. These insights allow informed recommendations to be made to optimise support management in the company.

## 📸 Screenshots
First page (first section):
![image](https://github.com/user-attachments/assets/d896ff2d-e4ce-4dfb-82ca-926f99d13596)

First page (second section):
![image](https://github.com/user-attachments/assets/7f7c6c14-955a-4222-a02b-e52499bbbce0)

Second Page (Rankings):
![image](https://github.com/user-attachments/assets/95d163db-6b28-4eb8-8cdc-9a38d7533c91)

Third Page (Categories): 
![image](https://github.com/user-attachments/assets/b7596822-9b88-49a2-80a2-07fab673807a)
