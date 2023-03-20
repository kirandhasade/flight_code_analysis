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

### Analysis Involve Phases:
1. Data collection
2. Data Understanding
3. Data Cleaning and Preparation 
4. Data Analyse

### Phase 1. Data Collection
- This dataset comprises of contains information about flight booking options data taken from Kaggle for flight travel between India's top 6 metro cities.
- This data consists of 11 rows and 13354 columns.

### Phase 2:Data Understanding
### Observation:
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

### Observations:
- Number of variables = 11
- Number of rows = 13354
- Number of categorical type of feature = 10
- Number of numerical type of feature = 1

### Phase 4. Data Analysis

#### Q. 1.Top 10 Aviation Companies whose flight tickets are sold the most?
<img width="997" alt="Q 1_screenshot" src="https://user-images.githubusercontent.com/127043120/226339938-66a1440a-001e-4c83-a3a0-aa251d2dcb93.png">
- Of the total flight tickets sold Jet Airways has the highest share followed by Indigo.   

#### Q.2. Which month have most number of flights?
<img width="641" alt="Q 2_screenshot" src="https://user-images.githubusercontent.com/127043120/226340261-e2a55e8b-b723-49c3-9683-cca08c0c2ca2.png">
- May has most number of flights followed by June and March.

#### Q.3. Which airline is most expensive?
<img width="1010" alt="Q 3_screenshot" src="https://user-images.githubusercontent.com/127043120/226340487-0dabd559-852a-4b12-b161-2c023e8f3d47.png">
 - Jet Airways Business has higher flight fares as compared to other Airlines, followed by Jet Airways and Multiple carriers.
 - Jet Airways has the most outliers in terms of price.

#### Q.4 Which airline has boarded the most?
<img width="1003" alt="Q 4_screenshot" src="https://user-images.githubusercontent.com/127043120/226340733-9b5a0dbc-6d42-4bc6-aec1-4382ab5121c6.png">- Jet Airways has most of the flights boarded followed by IndiGo and AirIndia.

#### Q.5 Which source will be having highest fare?
<img width="1012" alt="Q 5_screenshot" src="https://user-images.githubusercontent.com/127043120/226340851-fe270916-f2ed-4778-a4ce-d2c69595b43b.png">
 - Flights originating from banglore has high flight fares as compared to other sources from where flights are originating.

 - Banglore as the source location has the most outliers while Chennai has the least.

### Q.6 Which destination will be having highest fare?
<img width="999" alt="Q 6_screenshot" src="https://user-images.githubusercontent.com/127043120/226341067-b7eb1832-9d73-4073-b63c-8fc4d22444e1.png">
- Flights whose destination is New Delhi has highest fare compared to other flights whose destination is other than New Delhi.
  - New Delhi as the destination location has most of the outliers while Kolkata has the least.
