# Introduction
Haulage Analysis for a fictional haulage business.

---

# Project Name: Haulage Analysis (Deriving insights From Data)
![homepage](https://user-images.githubusercontent.com/92920156/194767939-de70c762-1380-4633-9b3a-4271b7950b81.jpg) <br>
image source: [google.com](https://www.google.com/) <br>
all rights belongs to the orignal creator

---

# Problem Objective <br>

Data Analysis using Power BI<br>
Creating a Reports that gives the insights on a fictional haulage business covering the employee productivity, most moved product(most profitable product), revenue, expenses by product, drivers and depot and destination visited. 
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
- Closed trip list: This includes more than 7 columns: 
    - Trip No
    - Date
    - Time
    - Truck No
    - Driver Name
    - Destination
    - Actual Date   
- Open trip list:  This includes more than 7 columns: 
    - Trip No
    - Date
    - Time
    - Truck No
    - Destination
    - Actual Date 
- Trip Rates:  This includes more than 9 columns: 
    - Load Port
    - Destination
    - Product Category
    - Trip Rate
    - Loading Expenses
    - Trip Allowance
    - Union Fees
    - Parking Fees
    - Capacity
    - Product
- Truck Available: This includes more than 7 columns: 
    - Truck No
    - Product Type
    - Capacity
    - Truck Classification
    - Aquilla Status
    - Status(Availability)
    - Depot Location
- Truck List: This includes more than 7 columns: 
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


Then I used excel to create a new table including just a column named total truck trip id by copy the truck trip id from both closed and open trips into a single column. This was done to create a better relationship between these two columns.<br>
### Note
I didn't append both tables because they had little structural differences.<br>
Then I imported this newly created table which I named destinations into power bi (note: I later used this table as my fact table. Forgive me for the wrong choice of name)

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

## 1. Starting From the Truck Section
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

### Now to the Visuals
- ### The first visual contains a pie charts showing the total trucks by the year Purchased
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their trucks are prone to breakdown and prepare for it before hands.
Factors influencing breakdown include how much the trucks is being used, this brings us to the next visual.

- ### Bar chart showing the Total Trips per trucks
This visual shows how many trips a truck has travelled through out the business's lifetime(2 years+).
#### Importance of The visual
This will enable the stakeholders know which of their trucks are the most active and prepare for replacement before hand imcase of a breakdown.

- ### Treemap Visual showing aquilla status by trucks
This shows trucks by their registration type.
#### Importance of The visual
This will enable the stakeholders know which of their trucks are available for aquilla approved states.


- ### Line charts showing total trips, closed trips and open trips
This shows the total trips travelled by trucks which includes a drill through from year, to quarter, month and day.
#### Importance of The visual
This will enable the stakeholders know the total trips travelled by their trucks and prepare before hand for breakdown.

- ### Pie chart showing the percentage classification of trips
This shows the percentage classification of all trucks 
#### Importance of The visual
This will enable the stakeholders know the truck types they have in stock and the type of destination they can travel based on their classification and know which type of trucks will warrant more investment.<br>
With Bridging meaning long distance trucks, West local - Trucks that travels to closer states and local meaning trucks that travels within states.

- ### Matrix Showing the capacity of trucks by total trucks and available trucks
This shows the total trucks by capacity and available trucks
#### Importance of The visual
This will enable the stakeholders know the truck by capacity they have in stock and those that are available for jobs. When clients demands for them

## Findings
Majority of the company's truck were purchased in 2020.<br>
The top 5 trucks that travelled the most destination where purchased in year 2020 with majority being non aquilla, bridging trucks having majority capacity of 45,000litres and none of the trucks (trucks bought in 2020) are currently under repair.<br>
Over 160 of these trucks are available for use while 290 are currently on route at the time the data was collected.

## Recommendation
I will recommed the stakeholders to get new trucks to replace these trucks in few years to come due to the higher possiblity of breakdown due to their immense usage.
<br><br>
[![Trucks Section](https://user-images.githubusercontent.com/92920156/194880008-de38eee6-05cd-4aa1-8c71-1bee3ce9addd.jpg)](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSection16a40e10e52960e0676b)


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

### The Visuals
- ### The first visual contains a bar charts showing the Most Active Depot
#### Importance of The visual
This visual will make its easier for the decision makers to know which of depot they have more presence in advert of employement and development

- ### Line charts showing total trips, closed trips and open trips
This shows the total trips travelled by trucks which includes a drill through from year, to quarter, month and day
#### Importance of The visual
This will enable the stakeholders know the total trips travelled by their trucks and prepare before hand for breakdown.

- ### The Flow maps
The first flow map shows the how the trucks travelled from the depot to various destination with concentration on the destination visited.<br>
The second flow  map shows how the trucks travelled from the depot to various destination with concentration on the depot.
#### Importance of The visual
This will enable the stakeholders know which area or route to create repair shops or strike a deal with the mechanic along the route in advert of a truck breakdown.


## Findings
A total of 15K trips have being carried out by the company at the time of this report. Having a total of over 6k closed trips and 7k open trips. <br> 
Location 4 depot happens to be the most active depot, while abuja happens to be the most visited places.

## Recommendation
I will recommed the stakeholders to make deal with mechanics and repair shop at strategic places along the most used route by its drivers incase of breakdown for immediate support and repair
<br><br>

[![Trips Section](https://user-images.githubusercontent.com/92920156/194876312-55d2cf9c-2cee-4679-9824-9d0cc7b2b4bf.jpg)](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSection4641173b6ac39aee8c22)

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

### The Visuals
- ### The first visual contains a pie charts showing expenses by drivers
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their drivers are they spending the most on.

- ### Bar showing total trips by drivers
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their drivers have travelled the most (i.e most productive).

- ### The treemap showing total revenue generated by drivers
#### Importance of The visual
This visual will make its easier for the decision makers to know which of their drivers have they generated the most revenue from their successful trips.

- ### Line charts showing total trips, closed trips and open trips
This shows the total trips travelled by trucks which includes a drill through from year, to quarter,m onth and day
#### Importance of The visual
This will enable the stakeholders know the total trips travelled by their trucks and prepare before hand for breakdown.

## Findings
The dataset provided gave only details(name) of drivers whom have successfully completed a trip (closed trips).<br>
In the bridging section <br>
- Pilot 151 had the most successful number of trips. Travelling from Warri to Sapelle.<br>
He also accounted for the most expenses in the catergory of bridging drivers which is understandable but with a lesser revenue generated (the third driver with the most revenue generated) due to the destination he his plying.

In the West Local section <br>
- Pilot 649 had the most succeful number of trips. Travelling from Warri and few other states like Auchi.<br>
He also accounted for the most expenses and the most revenue generated in the catergory of West Local Trucks drivers which is understandable.

In the Local section <br>
- Pilot 658 had the most succeful number of trips. Travelling from Warri and few other states like Auchi.<br>
He also accounted for the most expenses and the most revenue generated in the catergory of Local Trucks drivers which is understandable.

## Recommendation
I will recommed the stakeholders to give / provide initiatives for outstanding employee to increase their productivity and a means of acknowledgement of the job well done.
<br><br>

[![Drivers Section](https://user-images.githubusercontent.com/92920156/195020848-2f7ac418-0737-4999-9474-42072e9f21d4.jpg)](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSection68ae205ed19a82d7c24b)

## 4. The Product Section
Which contains 5 main visuals, 1 cards and 2 slicers
### The cards shows
- The total product moved

### The slicers includes:
- Year Slicer to filter between years
- The Status Slicer

### The Visuals
- ### The first visual contains a pie chart showing the product moved by status (open or closed)
#### Importance of The visual
This visual will make its easier for the decision makers to know the quantity of product on the road and those delivered.

- ### Treemap Visual
This shows the total product moved by product types
#### Importance of The visual
This will enable the stakeholders know which product type they moving the most

- ### The column chart
This shows the product types by expenses
#### Importance of The visual
This will enable the stakeholders know which of the product types they spending the most on, in terms of transportation.

- ### The column chart 2
This shows the product by product moved
#### Importance of The visual
This will enable the stakeholders know which of the product have they moved the most.

- ### The matrix chart
This shows the product by capacity by product volume by total trips
#### Importance of The visual
This will enable the stakeholders know which product types is the most moved and of which of the capacities

## Findings
The most moved product is the white product.<br>
Lesser product are on the road compared to the successfully delivered ones

## Recommendation
I will recommend the decision makers to make sure that trucks of capacity 45,000L are always ready to answer clients request since the are the most used which implies that trucks of such capacity will be the most demanded by clients.

[![Product Section](https://user-images.githubusercontent.com/92920156/195021536-05eff087-d244-4d7e-95d1-e0093edb5458.jpg)](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSection02c4bbdf9905ef002511)

## 5. The Revenue Section
Which contains 5 main visuals, 1 cards and 2 slicers
### The cards shows
- The total product moved

### The slicers includes:
- Year Slicer to filter between years
- The Status Slicer

### The Visuals
- ### The Column Chart Visuals
The total revenue by product type
#### Importance of The visual
This visual will make its easier for the decision makers to which product gives them the most revenue

- ### Pie Chart Visual
This shows the total revenue generated by closed and open destination trips
#### Importance of The visual
This will enable the stakeholders know which of their trips have generated the most.

- ### The Treemap chart
This shows the total Revenue generated per years
#### Importance of The visual
This will enable the stakeholders know which of the years have generated the most revenue.

- ### The bar chart
This shows the total Revenue generated by drivers
#### Importance of The visual
This will enable the stakeholders know which drivers have generated the most revenue.

- ### The Decomposition Tree
This shows a breakdown of revenue by depot, destination, product type, trip status and driver's name.
#### Importance of The visual
This will enable the stakeholders drill through the revenue and notice the factors affecting the revenue.

## Findings
The product that generate most revenue is the white product due to the fact that it the most moved product.<br>
While revenue generated by the trip status is nearly evenly distributed with open trip 3%+ more than the revenue generated by the closed trip which is also understandable because the dataset clearly says the total open trips are more than the succesfully completed trips (closed trips). <br>
The most revenue generated came from the year 2021 due to more bussiness active in the that year. <br>
Road pilot 172 Generated the most Revenue which is understandable due to the type of destination he travels and the product he carries (Bridging driver).

## Recommendation
Other drivers should be charged to work more to reduce the overhead effect on the company's revenue incase Road pilot 172 decides to leave.

[![Revenue Section](https://user-images.githubusercontent.com/92920156/195021790-28ba9ea0-363b-4252-b912-b145215d9449.jpg)](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSectiond55df70af4a105088c79)


## 6. The Expenses Section
Which contains 5 bookmarks, 5 main visuals, 1 multi cards and 2 slicers
### The multi-cards shows
- Total Expenses
- Total Loading Expenses
- Total Trip Allowance
- Total Union Expenses

### The slicers includes:
- Year Slicer to filter between years
- The Status Slicer

### The Bookmarks
- Expenses
- Loading Expenses
- Union Expenses
- Trip Allowance
- All Expenses
#### Note three bookmarks contains the same visual but the reference columns are being replaced in respective bookmarks.
    -   Reference columns include
            - Loading Expenses
            - Union Expenses
            - Trip Allowance

---

### - The Visuals for Bookmark(2)
- ### The Decomposition Tree
This shows a breakdown of all expenses by depot, destination, product type, trip status and driver's name.
#### Importance of The visual
This will enable the stakeholders drill through the revenue and notice the factors influencing their expenses.

- ### The Column Chart Visuals
The expenses by product type
#### Importance of The visual
This visual will make its easier for the decision makers to know which product they are spending more on.

- ### Pie Chart Visual
This shows the expenses by closed and open destination trips
#### Importance of The visual
This will enable the stakeholders know which of their trips status they spent more on.

- ### The Treemap chart
This shows the expenses per years
#### Importance of The visual
This will enable the stakeholders know which of the years they have spent more in.

- ### The bar chart
This shows expenses by drivers
#### Importance of The visual
This will enable the stakeholders know which drivers have incurred the most cost.


## Findings
The product that generate most expenses incurred was on the white product due to the fact that it the most moved product.<br>
While expenses incurred by the trip status is nearly evenly distributed with open trip 3%+ more than the expenses incured by the closed trip which is also understandable due to the dataset which clearly says the total open trips are nore than the succesfully completed trips (closed trips). <br>
The most expenses incured came from the year 2021 due to more bussiness active in the that year. <br>
Road pilot Austin incurred the most expenses which is understandable because he travelled the most trips

---

### - The Visuals for Bookmark(2,3,4)
- ### The Decomposition Tree
This shows a breakdown of Loading Expenses, Union Expenses, Trip Allowance (in their respective bookmarks) by depot, destination, product type, trip status and driver's name.
#### Importance of The visual
This will enable the stakeholders drill through the revenue and notice the factors influencing their expenses.

- ### The Column Chart Visuals
The Loading Expenses, Union Expenses, Trip Allowance (in their respective bookmarks) by product type
#### Importance of The visual
This visual will make its easier for the decision makers to which product they are spending more on.

- ### Pie Chart Visual
This shows the Loading Expenses, Union Expenses, Trip Allowance (in their respective bookmarks) by closed and open destination trips
#### Importance of The visual
This will enable the stakeholders know which of their trips have they spent more on.

- ### The Treemap chart
This shows theLoading Expenses, Union Expenses, Trip Allowance (in their respective bookmarks per years
#### Importance of The visual
This will enable the stakeholders know which of the years they have spent more in.

- ### The bar chart
This shows Loading Expenses, Union Expenses, Trip Allowance (in their respective bookmarks) by drivers
#### Importance of The visual
This will enable the stakeholders know which drivers have incurred the most cost.

## Findings
The product that generate most revenue is the white product due to the fact that it the most moved product.<br>
While revenue generated by the trip status is nearly evenly distributed with open trip 3%+ more than the profit generated by the closed trip which is also understandable due to the dataset which clearly says the total open trips are nore than the succesfully completed trips (closed trips). <br>
The most profit generated came from the year 2021 due to more bussiness active in the that year. <br>

## Recommendation
I will recommend the trip allowance of the drivers with the most trips being increased because i found out that they weren't among the highest paid drivers.

### - The Visuals for Bookmark 5
- ### The Line Chart (Saw tooth visual)
This shows a year to date, quater to date and month to date visual of alll the categories of expenses
#### Importance of The visual
This will enable the stakeholders understand the how the expenses incurred are performing from a year to a date level
<br><br>
[![Expenses Section](https://user-images.githubusercontent.com/92920156/195022114-1fa1acfa-6487-459f-a132-c253cdbe3f2d.jpg)](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSectionb6ce676c7ea503ec24c8)


## 7. The Yearly Analysis Section
Which contains 5 main visuals and 3 slicers
### The slicers includes:
- Year Slicer to filter between years
- The Product Type
- The Driver's name

### The Visuals
- ### The Column and bar charts
This shows the total trip rate(revenue) vs total trip rate(revenue) in the previous year, total product moved vs total product moved in the previous year, total expenses Vs total expenses in the previous year
#### Importance of The visual
This will enable the stakeholders compare their growth and expenses between years

## Findings
The company's most active year was 2021. Which lead to a reasonable expenses incurred, net revenue generated and a profit from the bussines in that particular year.<br>
Most Product were moved with, more focus on white product

## Recommendation
I will advise the company on looking for ways to market other product aside white. <br>
Which might mean expanding to the locations where other products are in demand to prevent a total fold up incase white product goes out of demand.<br>
Also, I will recommend the company to get more of her trucks aquilla registered to benefits from the subsidy provided by the government, Without forgetting to encourage her workers. <br> 
My finally recommendation to the company is that they should offer incentives such as a reduction in trip rate for returning clients in other to retain them.
<br><br>
[![yearly analysis](https://user-images.githubusercontent.com/92920156/195022379-c6633243-175d-4600-914f-6e906e43c6b0.jpg)](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSectionfbe455b6ac5d81780793)

[Link to live Report](https://app.powerbi.com/view?r=eyJrIjoiYTQ5NzhkZWMtMmM2OS00NmM2LTk5MTgtMmY1NzA0NDBjZjI1IiwidCI6Ijg4ZTlhN2RjLTU2MzMtNGM2Ni1iNjZjLTkyZGY1Y2E3NDhmYyJ9&pageName=ReportSection)



