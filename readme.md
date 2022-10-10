# Introduction
Haulage Analysis for a fictional haulage bussiness.

---

# Project Name: Hualage Analysis (Deriving insights From Data)
![homepage](https://user-images.githubusercontent.com/92920156/194767939-de70c762-1380-4633-9b3a-4271b7950b81.jpg) <br>
image source: [google.com](https://www.google.com/) <br>
all rights belongs to the orignal creator

---

# Problem Objective <br>

Data Analysis using Power BI<br>
Creating a Reports that gives the insights on a fictional haulage bussiness covering the employee productivity, most moved product(most profitable product), revenue, expenses and profit generated by product,drivers and depot and destination visited. 
Including a year over year analysis.

---

# Tools used in actualizing the project

Power Bi<br>
Excel<br>
Notepad<br>

---

# Data Sourcing
The dataset was provided by my mentor <br>
[Sulaiman Lukman](https://www.linkedin.com/in/sulaimanlukmanadeleke/) <br>
## The dataset includes 5 excel sheets;
- Closed trip list: This icludes more than 7 columns: 
    - Trip No
    - Date
    - Time
    - Truck No
    - Driver Name
    - Destination
    - Actual Arriver Date   
- Open trip list:  This icludes more than 7 columns: 
    - Trip No
    - Date
    - Time
    - Truck No
    - Destination
    - Actual Arriver Date 
- Trip Rates:  This icludes more than 9 columns: 
    - Load Port
    - Destinatiom
    - Product Category
    - Trip Rate
    - Loading Expenses
    - Trip Allowance
    - Union Fees
    - Parking Fees
    - Capacity
    - Product
- Truck Available: This icludes more than 7 columns: 
    - Truck No
    - Product Type
    - Capacity
    - Truck Classification
    - Aquilla Status
    - Status(Availability)
    - Depot Location
- Truck List: This icludes more than 7 columns: 
    - Truck No
    - Product Type
    - Capacity
    - Truck Classification
    - Aquilla Status
    - Status(Availability)
    - Depot Location
    - Registration Year
    - Use column
 
---

# Data Transformation & Modeling

## Data Cleaning & Transformation
### - Step 1
After importing the datasets using the import method in power bi:<br>
Then, the first task i did was to clean the data by renaming misspelt values in columns, changing data-types and splitting the date-time columns (in tables that had them) to increase performance.<br>
<br/>
![applied steps 1](https://user-images.githubusercontent.com/92920156/194879509-c8e9f056-3e97-4c1e-84a7-df049a4f4cef.jpg)


Then I used excel to create a new table including just a column named total truck trip by copy the truck trip id from both closed and open trips into a single column. This was done to create a better relationship between this two columns.<br>
### Note
I didn't append both tables because they had little structural differences.
Then i imported this newly created table which i named destinations into power bi (note: I later used this table as my fact table. Forgive me for the wrong choice of name)

### - Step 2
I created a primary key in all the initial five tables to enable creating relationship with the destination table easier.<br>
Then I merged the already imported Destination tables (fact table) with other tables to create a table with more than 10 columns aside the secondary keys. <br>
Which Includes:
- Truck Trip Id
- Total Truck No
- Trip Status (conataining value indicating if the trip is closed or opem)
- Product type
- Truck Capacity
- Truck Classification 
- Depot Location
- Trip Rate
- Loading Expenses
- Trip Allowances
- Union Fees
- Destination (three columns- Destination name, Latitude and Longitude)
- Secondary Keys
<br><br>
![Destination3](https://user-images.githubusercontent.com/92920156/194777110-b97037cb-006b-4fc9-a9e8-cbaf64182686.jpg)



### - Step 3
I created a date table using blank query and M code.<br>
I also disabled power bi's defualt date table by setting my created table as my date table

## Data Modeling
I enabled many to one relationship and cross filter direction from the destination table (fact table) to other tables using their respective keys.
<br>
<br>
![model](https://user-images.githubusercontent.com/92920156/194776944-7cab5945-3346-414e-9f5a-8e61d43288d4.jpg)

---

# Findings and Recommendations 

1. ## Starting From the Truck Section
Which contains 5 main visuals, 6 cards and 3 slicers
### The cards shows:
- The total trucks
- Trucks In Use
- Trucks Under Repair
- The three classification of trucks

### The slicers shows:
- Year Slicer to filter between years
- Status Slicer to filter between available and unavailable trucks
- Classification Slicers to filter between the classification of the truck 

## Now to the Visuals
- ### The first visual contains a pie charts showing the total trucks by the year Purchased
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their trucks are prone to breakdown and prepare for it before hands.
Factors influencing breakdown include how much the trucks is being used this brings us to the next visuals

- ### Bar chart showing the Total Trips per trucks
This visual shows how many trips a truck has travelled through out the bussiness's lifetime(2 years+).
#### Importance of The visual
This will enable the stakeholders know which of their trucks are the most active and prepare for replacement before hand due to breakdown.

- ### Treemap Visual showing aquilla status by trucks
This shows trucks by their registration type
#### Importance of The visual
This will enable the stakeholders know which of their trucks are available for aquilla approved states


- ### Line charts showing total trips, closed trips and open trips
This shows the total trips travelled by trucks which includes a drill through from year, quarter,month and day
#### Importance of The visual
This will enable the stakeholders know the total trips travelled by their trucks and prepare before hand for breakdown.

- ### Barcharts showing the percentage classification of trips
This shows the percentage classification of all trucks 
#### Importance of The visual
This will enable the stakeholders know the truck types they have in stock and the type of destination they can travel based on their classification and know which type of trucks will warrant more investment.<br>
With Bridging meaning long distance trucks, West local- Trucks that travels to closer states and local meaning trucks that travels within states.

- ### Matrix Showing the capacity of trucks by total trucks and available trucks
This shows the total trucks by capacity and available trucks
#### Importance of The visual
This will enable the stakeholders know the truck by capacity they have in stock and those that are available for jobs. When clients demands for them

## Findings
Majority of the companies truck were purchased in 2020.<br>
The top 5 trucks that travelled the most destination where purchased in year 2020 with majority being non aquilla, bridging trucks having majority capacity of 45,000litres and none of the trucks (trucks bought in 2020)currently under repair.<br>
Over 160 of these trucks are available for use while 290 are currently on route at the time the data was collected.

## Recommendation
I will recommed the stakeholders to get new trucks to replace these trucks in few years to come due to the higher possiblity of breakdown due to their immense usage.
<br><br>

<a target=”_blank”  href="https://app.powerbi.com/view?r=eyJrIjoiZDhkMDE3NWUtOTMwZi00NzdkLTk0MGItNzdhZjgzMTI4NDJhIiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9"><img src="https://user-images.githubusercontent.com/92920156/194880008-de38eee6-05cd-4aa1-8c71-1bee3ce9addd.jpg"></img>
</a>


## 2. The Trip Section
Which contains 4 main visuals, 3 cards and 3 slicers
### The cards shows:
- Total Trips
- Total Open Trips
- Total Closed Trips

### The slicers shows:
- Year Slicer to filter between years
- The Truck No slicer
- The Driver's name slicer (note: all names are fictional and any similarities with real person should be taken as coincidence)

## The Visuals
- ### The first visual contains a bar charts showing the Most Active Depot
#### Importance of The visual
This visual will make its easier for the decision makers to know which of depot they have more presence in advert of employement and development

- ### Line charts showing total trips, closed trips and open trips
This shows the total trips travelled by trucks which includes a drill through from year, quarter,month and day
#### Importance of The visual
This will enable the stakeholders know the total trips travelled by their trucks and prepare before hand for breakdown.

- ### The Flow maps
The first flow map shows the how the trucks travelled from the depot to various desitnation with concentration on the destination visited.<br>
The second flow  map shows the how the trucks travelled from the depot to various desitnation with concentration on the depot.
#### Importance of The visual
This will enable the stakeholders know which area or route to create repair shops or cut a deal with the mechanic along the route in advert of a truck breakdown.


## Findings
A total of 15K trips have being carried out by the company at the time of this report. Having a total of over 6k closed trips and 7k open trips. <br> 
Warri depot happens to be the most active depot, while abuja happens to be the most visited places.

## Recommendation
I will recommed the stakeholders to make deal with mechanics and repair shop at strategic places along the most used route by its drivers incase of breakdown for immediate support and repair
<br><br>
<a target=”_blank”  href="https://app.powerbi.com/view?r=eyJrIjoiZDhkMDE3NWUtOTMwZi00NzdkLTk0MGItNzdhZjgzMTI4NDJhIiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9"><img src="https://user-images.githubusercontent.com/92920156/194876312-55d2cf9c-2cee-4679-9824-9d0cc7b2b4bf.jpg"></img>
</a>


## 3. The Drivers Section
Which contains 4 main visuals, 8 cards and 3 slicers
### The cards shows:
- Total No of Drivers
- Total Closed Trips
- Total Revenue
- Expenses
- Profit
- Total Number of bridging drivers
- West local drivers
- Local Drivers

### The slicers shows:
- Year Slicer to filter between years
- The Classification Slicer(to filter truck classification to better undertsand the trip carried out by drivers)
- The Driver's name slicer (note: all names are fictional and any similarities with real person should be taken as coincidence)

## The Visuals
- ### The first visual contains a pie charts showing expenses by drivers
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their drivers are they spending the most on.

- ### Bar showing total trips by drivers
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their drivers have travelled the most (i.e most productive).

- ### The treemap showing total revenue generated by drivers
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their drivers have they generated the most revenue from due to his successful trips.

- ### Line charts showing total trips, closed trips and open trips
This shows the total trips travelled by trucks which includes a drill through from year, quarter,month and day
#### Importance of The visual
This will enable the stakeholders know the total trips travelled by their trucks and prepare before hand for breakdown.

## Findings
The dataset provided gave only details(name) of drivers whom have successfully completed a trip.<br>
In the bridging section <br>
- Mr Austin had the most succeful number of trips. Travelling from Warri to Sapelle.<br>
He also accounted for the most expenses in the catergory of bridging drivers which is understandable but with a lesser revenue generated (the third driver with the most revenue generated) due to the destination he his plying.

In the West Local section <br>
- Mr Ubaka had the most succeful number of trips. Travelling from Warri and few other states like Auchi.<br>
He also accounted for the most expenses and the most revenue generated in the catergory of West Local Trucks drivers which is understandable.

In the Local section <br>
- Mr Ubaka had the most succeful number of trips. Travelling from Warri and few other states like Auchi.<br>
He also accounted for the most expenses and the most revenue generated in the catergory of Local Trucks drivers which is understandable.
## Recommendation
I will recommed the stakeholders to make give provide initiatives for outstanding employee to increase their productivity and a means of acknowledgement of the job well done.
<br><br>
<a target=”_blank”  href="https://app.powerbi.com/view?r=eyJrIjoiZDhkMDE3NWUtOTMwZi00NzdkLTk0MGItNzdhZjgzMTI4NDJhIiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9"><img src="https://user-images.githubusercontent.com/92920156/194876546-d22a6907-198b-4f9c-921f-3e1c4bbfde03.jpg"></img>
</a>

## The Product Section
Which contains 4 main visuals, 8 cards and 3 slicers
### The cards shows:
- Total No of Drivers
- Total Closed Trips
- Total Revenue
- Expenses
- Profit
- Total Number of bridging drivers
- West local drivers
- Local Drivers

### The slicers shows:
- Year Slicer to filter between years
- The Classification Slicer
- The Driver's name slicer (note: all names are fictional and any similarities with real person should be taken as coincidence)

## The Visuals
- ### The first visual contains a bar charts showing the Most Active Depot
#### Importance of The visual
This visual will make its easier for the decision makers to know which of depot they have more presence in advert of employement and development

- ### Line charts showing total trips, closed trips and open trips
This shows the total trips travelled by trucks which includes a drill through from year, quarter,month and day
#### Importance of The visual
This will enable the stakeholders know the total trips travelled by their trucks and prepare before hand for breakdown.

- ### The Flow maps
The first flow map shows the how the trucks travelled from the depot to various desitnation with concentration on the destination visited.<br>
The second flow  map shows the how the trucks travelled from the depot to various desitnation with concentration on the depot.
#### Importance of The visual
This will enable the stakeholders know which area or route to create repair shops or cut a deal with the mechanic along the route in advert of a truck breakdown.


## Findings
A total of 15K trips have being carried out by the company at the time of this report. Having a total of over 6k closed trips and 7k open trips. <br> 
Warri depot happens to be the most active depot, while abuja happens to be the most visited places.

## Recommendation
I will recommed the stakeholders to make deal with mechanics and repair shop at strategic places along the most used route by its drivers incase of breakdown for immediate support and repair




