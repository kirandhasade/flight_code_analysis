### Project Name: Flight Prediction Analysis

### Project Objective:
- The number of people who fly has dramatically increased in recent years. Pricing alters dynamically owing to many variables, making it difficult for airlines to maintain prices. As a result, I am attemptted to solve this problem by cleaning, preparing and analysing the flight price.
- Hence, the goal of this project is to clean, prepare and analyse the flight price dataset taken from Kaggle.
- Basically dataset have price based on information such as airline, date_of_journey, flight route including number of stops and duration of flight.
- Used this dataset to analyse the flight **journey price** based on a variety of variables as mentioned above. 

Using flight price dataset we tried to find out following questions answer:
1. Top 10 Aviation Companies whose flight tickets are sold the most?
2. Which month have most number of flights?
3. Which airline is most expensive?
4. Which airline has boarded the most?
5. Which source will be having highest fare?
6. Which destination will be having highest fare?
7. Which city is popular source city where most of the flights boarded?
8. Which city is popular destination city where most of the flights landed?

### Project Involve Following Phases:
1. Data Collection
2. Data Understanding
3. Data Cleaning & Preparation 
4. Data Analysis

### Phase 1. Data Collection
- This dataset comprises information about flight booking options. Data taken from Kaggle - flights travel between India's top 6 metro cities.
- This data consists of 11 rows and 13354 columns.

### Phase 2: Data Understanding
  1. airline:
  - Name of the airline ticket was booked.
  - There are total **12 unique airline** in the dataset.
  
  2. date_of_journey:
  - Journey date of each traveller. 
  - It is a date column in MM/DD/YYYY format.
  - Dates are from **01/03/2019 to 09/06/2019**
  
  3. source:
  - Source from which the airline would depart.
  - Total **5 unique source** names in the dataset.
  - It contains Banglore, Kolkata, Delhi, Chennai, Mumbai.
  
  4. destination:
  - Destination to which airline would arrive
  - There are total **6 unique destination** names in the dataset.
  - It contains New Delhi, Banglore, Cochin, Kolkata, Delhi, Hyderabad.
  
  5. route:
  - Represents route of the airline from source to destination.
  - There is one null value in the dataset.
  
  6. dep_time:
  - Time at which flight would departure from the source.
  - It is in H:MM format
  
  7. arrival_time:
  - Time at which flight would arrive at the destination.
  - It is in H:MM format followed by date of arrival.
  
  8. duration: 
  - Duration that airline takes to fly from source to destination.
  - It is in H:MM format.
  
  
  9. total_stops:
  - Total no. of stops that airline takes between source and destination.
  - There are total **5 unique total stops** in the dataset.
  - There is one null value in the dataset.
  - It contains non-stop, 2 stops, 1 stop, 3 stops, nan, 4 stops.
  
   10. additional_info:
  - Represents any Additional info about the airline.
  - There are total **10 unique additional information** in the dataset.
  - It contains No info, In-flight meal not included,No check-in baggage included, 1 Short layover, No Info,1 Long layover, Change airports, Business class,Red-eye flight, 2 Long layover.
 
   11. Price:
   - Represents fare of the ticket to fly from Source to destination in **rupees**.

### Overall statistics about dataset:
- Number of columns/features = 11
- Number of rows = 13354
- Number of categorical type of feature = 10
- Number of numerical type of feature = 1

### Phase 3: Data Cleaning, Preperation and Handling null values:

#### Data Cleaning
- Step 1. **Dropping 2 rows** there are 2 records whose flight duration is of 5 min which is inconsisent because distance between Mumbai to Hyderabad is approximately 713 Km and it approximately takes 2 hours to reach to Hyderabad from Mumbai.
- Step 2: **Filling total_stops column null value** there is one row where total_stops column contains 1 null value.As the flight duration is approximately 23 hours and journey is from Delhi to Cochin hence here replacing total_stops null value with 1 by refering similar data points in dataset.
- <img width="791" alt="Null_value_handling" src="https://user-images.githubusercontent.com/127043120/226655860-b45bccb3-e032-491a-b9e7-42f7f06bc52b.png">
- Step 3:**Handling categorical(total_stops) column** replacing total_stops column with integer variable such as non-stop:0,1 stop:1,2 stops:2,3 stops:3,4 stops:4,nan:1
- <img width="1005" alt="map_function" src="https://user-images.githubusercontent.com/127043120/227167643-3a44b8cb-8cad-4dcb-a29e-291d49d06401.png">
- Step 4:**Delete route column** Analysis not based on route column hence, deleting route column.

#### Handling multiple Null Value
- Step 1:**Impute mean for price column:**
  - 1. Price has **2671 null records** while 
  - 2. Ticket price is depended on **airline, source, destination and number of stops**.
  - 3. Hence null price values will be imputed or replace by mean value based on airline, route along with number of stops.
  - <img width="1000" alt="Screenshot 2023-03-23 at 12 11 33" src="https://user-images.githubusercontent.com/127043120/227200126-2c4a8fff-6019-4809-a26d-e0c3ddc52a46.png">
- Step 2:**Filling null values with mean data:**
  - After calucating mean in Step 1 we are replacing all price columns null values with mean data as price is dependent on various factors like which airline, source and destination and number of stops.
- Step 3: After step - 2 **drop rows having incomplete information:**
   - After Step 2-found that there is only one record left for Jet Airways Business flying from Bangalore to New Delhi.
   - As there is no corresponding rows for the factors which is airline,source,destination in dataset to compute it's mean price amount.
   - <img width="945" alt="Screenshot 2023-03-23 at 11 49 38" src="https://user-images.githubusercontent.com/127043120/227194906-acb1e3d0-1461-421f-bea5-1c7aff6acefc.png">
   - We will delete the record as it has only one record, if it contains multiple records then we can be able to do futher analysis.
   - - <img width="1000" alt="Screenshot 2023-03-23 at 11 59 25" src="https://user-images.githubusercontent.com/127043120/227197496-3346e1ea-fadc-4a17-a2bd-0edd3223e645.png">
 - In real world we can perform following analyis for the same:
    - 1. We try to find similiar records i.e. same source ,destination and airline and will try to impute mean for the same.
    - 2. We'll ask airline for more detailed information of the flight and can do the further analysis.
    - 3. We can delete the record.

    
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
 
#### Q.6 Which destination will be having highest fare?
- Flights whose destination is New Delhi has highest fare compared to other flights whose destination is other than New Delhi.
- New Delhi as the destination location has most of the outliers while Kolkata has the least.
 <img width="999" alt="Q 6_screenshot" src="https://user-images.githubusercontent.com/127043120/226341067-b7eb1832-9d73-4073-b63c-8fc4d22444e1.png"> 
  
