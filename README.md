# Analysis-of-Agents-in-the-Tractchun-company
Resume: Tractchun is a company in the manufacturing industry with Information Technology (IT) agents who support Tickets. Information has been requested from the Human Resources department in order to perform a more in-depth analysis based on classifications of their Agents.

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

# Detailed Explanation of the Project

1) Data obtained, in Excel format:

a) Tickets: 
From 1 January 2016 to 31 December 2020. The Ticket data are separated by years, i.e. we have a table of Ticket data corresponding to the year 2016, another table corresponding to the year 2017, another to 2018, another to 2019, and another to 2020. The tables for each year have the same format with the same columns.

Column data:
- Ticket ID: ID of each Ticket
- Date: creation date of the Ticket
- Employee ID: Employee ID, relates to the employee table, as Tickets are created by employees
- Agent ID: ID of the IT Agents, related to the Agents table, who attend to the Tickets created by the employees
- Category: Access / Login, Hardware, Software, System
- Type: Problem, Request.
- Severity: 0 - Unclassified, 1 - Minor, 2 - Normal, 3 - Major, 4 - Critical
- Priority: 0 - Unassigned, 1 - Low, 2 - Medium, 3 - High.
- Resolution Days: days taken to resolve each Ticket.
- Satisfaction: from 1 to 5 stars, represents the satisfaction of each Employee with the attention received from the Agents on the Tickets.

Tickets table preview:
Example of 2018 Tickets:
![image](https://github.com/user-attachments/assets/aa42cb84-7750-4860-bdc2-a6bca90a5bf1)

b) Agents: 
Data corresponding to the Agents who deal with the queries of the employees. With their ID, Name, E-mail, and date of birth.
![image](https://github.com/user-attachments/assets/03daac7d-47e9-4c06-93c0-48c08aa36b49)

c) List + Employees: 
Data corresponding to the employees requesting the Tickets. There are 2 floors of employees, 1 and 2.
Column data:
Shift: represents the shifts or schedules that correspond to the employees.
ID Position: work role occupied by each employee of the company, it is correlated with the Positions table.
Plant 1:
![image](https://github.com/user-attachments/assets/e43fbb11-cb4d-400a-85de-1346dc41a4f6)

Plant 2:
![image](https://github.com/user-attachments/assets/e7f6e65b-bf91-4a47-812b-9a35522d0fa3)

d) Positions: 
Data corresponding to the job roles of the employees requesting the Tickets.
Column data:
ID Position:
Position: job role, it can be Systems Analyst, Internal Auditor, Accounting Assistant, etc.
Department: which department each position corresponds to, such as Materials, Accounting, Staff, Production Control, SYSTEMS, TRAFFIC AND CUSTOMS, etc.
Position Type: type of position, can be Administrative, Management, Middle Management or Operational.

![image](https://github.com/user-attachments/assets/0f09da8e-ea0d-4d44-8091-7cbc2e49b730)

2) Data import and data transformation:
We import the Tickets tables with the option to import it by folder, which allows us to combine all the tables (remember that we have the Tickets data for the years 2016, 2017, 2018, 2019 and 2020, but in separate tables, this is possible because the tables have the same column format), we import the Positions table, then TI Agents, and finally from the List + Empolyees file it contains two tables, the Plant 1 and Plant 2. 
Having in total 5 tables, Tickets, Positions, TI Agents, Plant 1, Plant 2.

a) Tickets Table:
![image](https://github.com/user-attachments/assets/9ca63a99-427e-40e5-8619-2782c0a533c0)

In Power Query we remove the Source.Name column, then we add a conditional column called ‘Opinions’ assigning a rating or opinion based on satisfaction, for example: if 5 = Excellent, if 4 = Very Good, if 3 = Good, 2 = Fair, 1 = Bad.

![image](https://github.com/user-attachments/assets/31d4d652-2495-4970-a558-17224928fed8)

We check that the data types are correct. And now we have the Tickets table ready, which will be our Facts table.

![image](https://github.com/user-attachments/assets/9b2e3f97-0993-42aa-b01a-6441e9c63be1)
![image](https://github.com/user-attachments/assets/4ca8388b-6661-4dc4-ae27-2eab1e30f455)

b) Plant 1 and Plant 2 tables:
From the Excel List + Employees, we import the Plant 1 and Plant 2 tables:
Plant 1:
![image](https://github.com/user-attachments/assets/c48aacec-461f-4395-b153-1573121409ec)

Plant 2:
![image](https://github.com/user-attachments/assets/2f3ca8b8-620d-4112-bdc4-4ba995ffab0c)

The process applies to both tables. We clean the top 5 rows with null values, so we are left with row 6 as the first row so we use the first row function as header, fill in the column ‘Shift’, and finally we add a column called ‘Plant’ to indicate to which plant each employee corresponds, 1 for plant 1, and 2 for plant 2, as we will later combine the Plant 1 and Plant 2 tables.

Table of Plant 1 and Plant 2 ready:
![image](https://github.com/user-attachments/assets/7e3b88b3-7970-4e3f-b80c-01fb666822e2)
![image](https://github.com/user-attachments/assets/26c6660f-3e5c-4309-a7c6-6dc273269413)
![image](https://github.com/user-attachments/assets/e1af1202-c77a-4581-8f2f-617f1414c5b9)

What we will do is, from the Plant 1 and Plant 2 tables, we will create a table called Employees, which will contain all the data of the company's employees, with the function of appending tables.

![image](https://github.com/user-attachments/assets/69b2c45f-7199-4996-9679-15225220b206)

Una vez creada, creamos una columna llamada Full Name en la que combinamos
las columnas de “Name” y “Last Name” para obtener el Full Name

![image](https://github.com/user-attachments/assets/9bf4520b-da58-4a61-984b-001a71c17eee)

Y tenemos lista nuestra tabla de Employees:

![image](https://github.com/user-attachments/assets/af88dde7-d362-4c27-b980-2cf5b2e8922d)

c) Tabla Positions:
Power BI, automáticamente nos elimina las primeras dos filas que no nos eran útiles. No hay mucho por hacer, solo poner en Mayúsculas la primera letra de cada palabra de la columna “Position Type”

![image](https://github.com/user-attachments/assets/0c2b97ec-d636-4f50-a5b2-1244046f739c)

d) Combination between the Employees table and the Positions table:
This will be our final table for the Employees which will be called Employees + Positions which will contain all the data of the employees of the company plus their job role, as it will contain the data of the employees and the positions. For this we use the function of Merge Queries as New, we use the column that they have in common that is ‘ID Position’, so that each employee of the table Employees is added the column of the corresponding position of the table Positions.

![image](https://github.com/user-attachments/assets/008dc801-90f8-4085-bd13-889a8ebc4c46)

We delete the ‘ID Position’ column and we have our final table of Employees table called ‘Employees + Positions’.
![image](https://github.com/user-attachments/assets/d3d57a5a-9be7-4f28-9ec3-27d5f54f3f41)

e) Tabla Agents:
A esta tabla debemos insertarle la columna de “Date of Birth” para determinar la fecha de nacimiento de cada Agente, esto lo hacemos combinando las columnas de Day, Month y Year, por lo tanto, una vez creada, eliminamos las columnas de Year, Month y Day. Luego, si observamos bien, algunos nombres de los Agentes contienen el apellido y otros no, algunos tienen abreviaciones, otros bien escritos, otros mal escritos, etc, asi que usaremos la columna de “E-mail” que contienen los nombres y apellidos de cada Agente, usaremos esta información para completar el nombre completo de los Agentes.
Con una función de Power Query, primero vamos a crear una columna que extraiga de la columna “E-mail” los valores que se encuentren antes del punto para obtener el Name, y luego vamos a crear otra columna que extrae los valores que se encuentren entre el punto y el arroba para extraer el Last Name
Para así poder combinar estas dos columnas y obtener el Full Name
Otra opción era extraer todo los valores que se encuentren antes del arroba, y reemplazar el punto por un espacio, y también obtendremos el Full Name

![image](https://github.com/user-attachments/assets/2dd5a1b6-cf49-4b11-af7e-2ae114c07224)

f) Creating the Calendar table:
Created from the Tickets table
This table is useful to be able to have precise segmentations in specific periods.
We create a blank Query in Power Query, and in the Source of that Query, programming in M we create a function that extracts a list with all the dates that are in the ‘Date’ column of the Tickets table.
![image](https://github.com/user-attachments/assets/7f71a3a4-965c-4125-9853-ffde87101751)

Then we create another function that extracts the minimum date from this list of dates, then another function that extracts the maximum date.

![image](https://github.com/user-attachments/assets/fa4661f7-7437-4c66-9def-ec11abb4de56)
![image](https://github.com/user-attachments/assets/74581d7f-ed1c-4d7d-9787-78a82f1b284b)

Now we create an array from the minimum date to the maximum date.

![image](https://github.com/user-attachments/assets/6bb044f9-a71e-4882-aae6-55045819ad9d)

We convert this matrix into a table...

![image](https://github.com/user-attachments/assets/acd9ea6f-a9f1-481b-bf3b-a3c016353e6e)

And, from now on, we make transformations such as changing the data type of the column so that it is in date format.

![image](https://github.com/user-attachments/assets/631834b1-d8ae-47f3-b565-e90d1811f9da)

 and then we can insert year, month, day, quarter, week of the year, name of the month, name of the day, number of the day of the week, number of the day of the year, we create a conditional column for the semesters (if it is the first semester of the year or the second semester of the year), 

 And now we have our Calendar table ready, which will be useful for precise filtering and graphing of exact periods for deeper and more detailed analysis.

 ![image](https://github.com/user-attachments/assets/ae223b07-7838-480d-a945-20e36b2e40ae)

g) Creating the ‘Resolution Days’ table
We created this table to have a more compact analysis of the resolution days, as it is visually simpler to observe the resolution days in ranges, than to observe them one by one, later we will understand why this is the case.
Before moving on to data modelling, let's create a table called ‘Resolutions Days’ which will contain two columns, one called ‘Resolution Days’ which will contain the unique values of the ‘Resolution Days’ column of the Tickets table, and then another column called ‘Range of Days’ which will contain periods of days.
For this, similar to the Calendar table creation, we first create a new blank query, with M language we import the ‘Resolution Days’ column from the Tickets table into the table, remove duplicates, convert it to a table, use the conditional columns to create the Range of Days,

![image](https://github.com/user-attachments/assets/9da25b0c-d615-4466-af21-ac43f7d2f361)
![image](https://github.com/user-attachments/assets/f323a046-9370-4fb5-bace-3cdebd168acd)

Data Modelling:
In star design, Tickets our Facts table, and the rest our Dimensions tables.

![image](https://github.com/user-attachments/assets/00313646-7c03-4f40-8eac-b9c0b6f6d4c8)

Relations:
![image](https://github.com/user-attachments/assets/79cc3c80-9354-4fd3-9cf1-1e6f68e4c363)

Report

The pages contain arrows at the top for easy and intuitive navigation between pages.
1) First Page:
![image](https://github.com/user-attachments/assets/05b8e121-af02-412a-962b-ae4db0b5d581)

On this first page, on the left hand side we have a menu to filter the graphs by Year, Month, Day Range and IT Agent Name (with a search engine to look for a specific Agent). In this way we have precise information about a specific Agent, in a specific year and month. And thus evaluate the performance of each Agent. At the bottom there is a filter cleaner, if we apply filters to the graphs and we want to clean them, just click there and the filters will be cleaned. We also have an option to look at graphs by type which we will see later.

At the top we have some key KPI's, that the measures to create these KPI's are stored in a Measures table that we program them with DAX language, that will be used for the visualisations and KPI's. Like:

Total number of Tickets: ![image](https://github.com/user-attachments/assets/c59a9e1c-3065-4d5c-823f-61bd8d2cc5c8)


Total number of Agents: ![image](https://github.com/user-attachments/assets/1a823751-74e1-4ca4-805a-32631b5d4b60)


Average Satisfaction: ![image](https://github.com/user-attachments/assets/3521cf71-81c8-4eff-b26d-5ccc0818c3d2)


Average days to resolution: ![image](https://github.com/user-attachments/assets/cf60083c-2e01-4a0b-aaea-fe331b1eef62)


Number of Tickets per Agent: ![image](https://github.com/user-attachments/assets/ba7d59f8-773f-4beb-9fe4-096c5642a1ac)


Percentage of Positive Tickets: ![image](https://github.com/user-attachments/assets/de652d8d-b299-47b7-98c3-33ef5802d3a0)
![image](https://github.com/user-attachments/assets/6af0d1cb-2a01-4b7b-bfa8-a105ba7da51d)


Average Number of Tickets per Agent: ![image](https://github.com/user-attachments/assets/be7d08af-c62e-4140-90b5-1369f69f21fe)

Charts: 
Area Chart: corresponds to the number of tickets over time.
Donut Chart: proportion of tickets by Reviews, if it is ‘Excellent’ or ‘Very Good’ it is considered ‘Positive’, we can see the dark pink bar and the blue bar that cover 80% of the Donut, i.e. 80% of the attention of the Tickets have positive reviews.
Left bar chart: number of tickets per category
Right bar chart: Number of tickets by days of resolution

If in the menu we click on the marker (small square to the right of the text) next to ‘View Charts by type’ we see the following:
![image](https://github.com/user-attachments/assets/668906ee-8e7e-4918-b5cd-9b74e1012e54)




































