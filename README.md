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
