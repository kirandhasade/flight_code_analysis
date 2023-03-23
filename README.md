### Project Name: Flight Prediction Analysis

### Project Objective:
- The number of people who fly has dramatically increased in recent years. Pricing alters dynamically owing to many variables, making it difficult for airlines to maintain prices. As a result, we will attempt to solve this problem by cleaning, preparing and analysing the flight price.
- Hence, the goal of this project is to clean, prepare and analyse the flight price dataset taken from Kaggle.
- Basically dataset have price based on information such as airline, date_of_journey, flight route information including number of stops and duration of flight.
- So that we can use this dataset to analyse the flight journey price based on a variety of variables as mentioned above. 

Using flight price dataset we try to find out following questions answer:
1. Top 10 Aviation Companies whose flight tickets are sold the most ?
2. Which month have most number of flights?
3. Which airline is most expensive?
4. Which airline has boarded the most?
5. Which source will be having highest fare?
6. Which destination will be having highest fare?

### Project Involve Phases:
1. Data Collection
2. Data Understanding
3. Data Cleaning & Preparation 
4. Data Analysis

### Phase 1. Data Collection
- This dataset comprises of contains information about flight booking options. Data taken from Kaggle - flights travel between India's top 6 metro cities.
- This data consists of 11 rows and 13354 columns.

### Phase 2:Data Understanding
  1. airline:
  - Depicts name of the airline from which the ticket is booked.
  - There are total 12 unique airline names in the dataset.
  - It is of Object datatype.
  
  
  2. date_of_journey:
  - Represents journey date of each traveller. 
  - It is a date column in MM/DD/YYYY format.
  - It It is of Object datatype.
  
  
  3. source:
  - Represents source from which the airline would departure.
  - There are total 5 unique source names in the dataset.
  - It is of Object datatype.
  
  
  4. destination:
  - Represents destination to which airline would arrive
  - There are total 6 unique destination names in the dataset.
  - It is of Object datatype.
  
  
  5. route:
  - Represents route of the airline from source to destination.
  - It is of Object datatype. 
  - There is one null value in the dataset.
  
  
  6. dep_time:
  - Represents time at which flight would departure from the source.
  - It is in H:MM format.
  - It is of Object datatype.
  
  
  7. arrival_time:
  - Represents time at which flight would arrive at the destination.
  - It is in H:MM format followed by date.
  - It is of Object datatype.
  
  
  8. duration: 
  - Represents duration that airline Takes to fly from source to destination..
  - It is of Object datatype. 
  
  
  9. total_stops:
  - Represents total no. of stops that airline takes between source and destination.
  - There are total 5 unique total stops in the dataset.
  - There is one null value in the dataset.
  - It is of Object datatype.
  
  
   10. additional_info:
  - Represents any Additional info about the airline.
  - There are total 10 unique additional information in the dataset.
  - It is of Object datatype.
  
  
   11. Price:
  - Represents fare of the ticket to fly from Source to destination.
  - It is of float datatype.

### Overall statistics about dataset:
- Number of columns/features = 11
- Number of rows = 13354
- Number of categorical type of feature = 10
- Number of numerical type of feature = 1

### Phase 3: Data Cleaning, Preperation and Handling null values:

#### Data Cleaning
- Step 1. **Split date_of_journey column into date month and year columns** and then convert it into int datatype, as it contains DD/MM/YYYY format and object datatype.
- Step 2. **Dropped date_of_journey** column.
- Step 3: **Split arrival_time column into arrival_hour and arrival_min columns** and then convert it into int datatype, as it contains HH:MM format and object datatype.
- Step 5: **Split dep_time column into dept_hour and dept_min columns** and then convert it into int datatype, as it contains HH:MM format and object datatype. 
- Step 6: **Dropped dep_time** column.
- Step 7: **Split duration column into duration_hour column** as it contains H:MM format.
- Step 8: We found in duration_hour column there were 2 records which was having '5m' data values which was inconsistent as the route was Mumbai to Hyderabad.Hence we dropped the two rows.
- Step 9: Converted duration_hour into int.

#### Data Preperation
- Step 1: **Split duration column into duration_min column** as it contains H:MM format.
- Step 2: Wherever there is a NaN value replace it with zero (eg. if duration has only 2h data value in it's data in duration_hour column it will be 2 and in duration_min it will be 0) hence we are replacing duration_min column by zero.
- Step 3: Convert duration_min into int datatype. 
- Step 4: **Dropped duration** column.
- Step 5: We analysed route column and we found there is one null value in route column which we have replaced with one stop by refering similar data    points in dataset.
- <img width="791" alt="Null_value_handling" src="https://user-images.githubusercontent.com/127043120/226655860-b45bccb3-e032-491a-b9e7-42f7f06bc52b.png">
- Step 6: **Dropped route** column.
- Step 7: To analyse total_stops column we are using map function in which non_stop is mapped with zero, 1 stop is mapped with 1, 2 stops is mapped with 2, 3 stops is mapped with 3, 4 stops is mapped with 4 and nan vaue with 1.
- <img width="1005" alt="map_function" src="https://user-images.githubusercontent.com/127043120/227167643-3a44b8cb-8cad-4dcb-a29e-291d49d06401.png">
- Step 8 We are using Label Encoder for the airline,source,destination and additional_info columns to convert categorical feature into numerical feature.
- Step 8: Following is the example of airline column label encoding
- <img width="958" alt="Screenshot 2023-03-23 at 10 33 11" src="https://user-images.githubusercontent.com/127043120/227177061-512f17de-c34c-45d7-80af-a5f0e0efca59.png">

#### Handling multiple Null Value
- Observations: 
- 1. Price has **2671 null records** while route and total_stops have 1 null values respectively.
- 2. Ticket price is depended on **airline, source, destination and number of stops**.
- 3. Hence null price values will be imputed or replace by mean value based on Airline, route along with number of stops.
- 4. **One null value** still exist in price once mean is imputed. 
- <img width="945" alt="Screenshot 2023-03-23 at 11 49 38" src="https://user-images.githubusercontent.com/127043120/227194906-acb1e3d0-1461-421f-bea5-1c7aff6acefc.png">
 - Hence we can perform following analyis for the same:
       - 1.We will try to find similiar records i.e. same source ,destination and airline and will try to impute mean for the same.
       - 2.We will ask airline for more detailed information of the flight  and can do the further analysis.
       - 3.We can delete the record.
  - We will delete the record as it has only one record, if it contains multiple records then we can be able to do futher analysis.
    
### Phase 4. Data Analysis

#### Q. 1.Top 10 Aviation Companies whose flight tickets are sold the most?
  - Of the total flight tickets sold Jet Airways has the highest share followed by Indigo.
 <img width="997" alt="Q 1_screenshot" src="https://user-images.githubusercontent.com/127043120/226339938-66a1440a-001e-4c83-a3a0-aa251d2dcb93.png">  
 <img width="625" alt="Q 1_a_screenshot" src="https://user-images.githubusercontent.com/127043120/227168521-7f07605d-648e-47e0-86ff-e946e7139e9a.png">


#### Q.2. Which month have most number of flights?
- May has most number of flights followed by June and March.
<img width="641" alt="Q 2_screenshot" src="https://user-images.githubusercontent.com/127043120/226340261-e2a55e8b-b723-49c3-9683-cca08c0c2ca2.png">


#### Q.3. Which airline is most expensive?
 <img width="1010" alt="Q 3_screenshot" src="https://user-images.githubusercontent.com/127043120/226340487-0dabd559-852a-4b12-b161-2c023e8f3d47.png">
- Jet Airways Business has higher flight fares as compared to other Airlines, followed by Jet Airways and Multiple carriers.
- Jet Airways has the most outliers in terms of price.


#### Q.4 Which airline has boarded the most?
 - Jet Airways has most of the flights boarded followed by IndiGo and AirIndia.
 <img width="1003" alt="Q 4_screenshot" src="https://user-images.githubusercontent.com/127043120/226340733-9b5a0dbc-6d42-4bc6-aec1-4382ab5121c6.png">
 
#### Q.5 Which source will be having highest fare?
- Flights originating from banglore has high flight fares as compared to other sources from where flights are originating.
- Banglore as the source location has the most outliers while Chennai has the least.
 <img width="1012" alt="Q 5_screenshot" src="https://user-images.githubusercontent.com/127043120/226340851-fe270916-f2ed-4778-a4ce-d2c69595b43b.png">
 
### Q.6 Which destination will be having highest fare?
- Flights whose destination is New Delhi has highest fare compared to other flights whose destination is other than New Delhi.
- New Delhi as the destination location has most of the outliers while Kolkata has the least.
 <img width="999" alt="Q 6_screenshot" src="https://user-images.githubusercontent.com/127043120/226341067-b7eb1832-9d73-4073-b63c-8fc4d22444e1.png"> 
  
