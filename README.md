# bikesharing
## Overview of the statistical analysis:

[NYC_Citibike_Challenge ipynb File](NYC_Citibike_Challenge.ipynb)

[link to dashboard](https://public.tableau.com/app/profile/kushal.pannu/viz/Bikesharing_16704710757740/BikeSharingDashboard?publish=yes)

[link to Story](https://public.tableau.com/app/profile/kushal.pannu/viz/Bikesharing_Story_16704714153730/BikesharingStory?publish=yes)

In this analysis we will be using Tableau to visualize bike-sharing data.

Resources required: 

     - 201908-citibike-tripdata csv File- We will use Pandas to change the datatype of the "tripduration" column from an integer to a datetime datatype to get the time          in hours and minutes. Then we export the DataFrame as a CSV file to use for the visualizations in Deliverable 2
     
     - Tableau Public- In Tableau Public, we will create Visualizations for the Trip Analysis.
     
### The purpose of the analysis:

Using Tableau, create visualizations that show:

      How long bikes are checked out for all riders and genders.
      How many trips are taken by the hour for each day of the week, for all riders and genders.
      A breakdown of what days of the week a user might be more likely to check out a bike, by type of user and gender.

## Results: There are at least seven visualizations for the NYC Citibike analysis (7 pt)
There is a description of the results for each visualization (7 pt)

### Deliverable 1: Change Trip Duration to a Datetime Format
[NYC_Citibike_Challenge ipynb File](NYC_Citibike_Challenge.ipynb)

        import pandas as pd
        # 1. Create a DataFrame for the 201908-citibike-tripdata data. 
        citibike_data = pd.read_csv("201908-citibike-tripdata.csv")
        citibike_data.head()
        # 2. Check the datatypes of your columns. 
        citibike_data.info()


     
       tripduration                 int64
       starttime                   object
       stoptime                    object
       start station id           float64
       start station name          object
       start station latitude     float64
       start station longitude    float64
       end station id             float64
       end station name            object
       end station latitude       float64
       end station longitude      float64
       bikeid                       int64
       usertype                    object
       birth year                   int64
       gender                       int64
       dtype: object
       
       # 3. Convert the 'tripduration' column to datetime datatype.
       citibike_data['tripdur']= citibike_data['tripduration']
       citibike_data['tripduration'] = pd.to_datetime(citibike_data['tripduration'], unit='m')
       citibike_data.head()
       
       # 4. Check the datatypes of your columns. 
       citibike_data.info()

       RangeIndex: 2344224 entries, 0 to 2344223
       Data columns (total 15 columns):
       #   Column                   Dtype         
       ---  ------                   -----         
       0   tripduration             datetime64[ns]
       1   starttime                object        
       2   stoptime                 object        
       3   start station id         float64       
       4   start station name       object        
       5   start station latitude   float64       
       6   start station longitude  float64       
       7   end station id           float64       
       8   end station name         object        
       9   end station latitude     float64       
       10  end station longitude    float64       
       11  bikeid                   int64         
       12  usertype                 object        
       13  birth year               int64         
       14  gender                   int64         
       dtypes: datetime64[ns](1), float64(6), int64(3), object(5)
       memory usage: 268.3+ MB

       # 5. Export the Dataframe as a new CSV file without the index.
       citibike_data.to_csv('citibike.csv', index= False)
       
### Create Visualizations for the Trip Analysis

#### 1. How long bikes are checked out for all riders and genders.

![Test Image](/Resources/Checkout_Times_for_Users.png)

    - In this Visualization, we will check the checked out time of the bikes for all         the riders.
    - The image represents that majority of the bike rides lasted for 5 minutes.

![Test Image](/Resources/Checkout_Times_by_Gender.png)

       - In this Vicualization, we will check the checked out time of the bike for all         the genders.
       - The image depicts that the tripduration of female( 6 minutes) is more than            the male(5 minutes)
       
#### 2. How many trips are taken by the hour for each day of the week, for all riders and genders.

![Test Image](/Resources/Trips_by_Weekday_per_Hour.png)

        - In this Visualization, we will graph the number of trips by each day of the           week for all the riders.
        
        - The Image depicts that , there are more number of bike trips during the               weekend than during the weekdays and there are more number of trips from 1pm           to 6 pm as comparate to the rest of the hours of the day.
     

![Test Image](/Resources/Trips_by_Gender.png)

         - In this Visualization, we will graph the number of trips by weekday for all           the genders.

#### 3. A breakdown of what days of the week a user might be more likely to check out a bike, by type of user and gender.

![Test Image](/Resources/User_Trips_by_Gender_by_Weekday.png)

      - In this Visualization, we will graph the number of bikes checked out by the           each gender and filtering by each usertype(customer or subscriber)
      
      - This image illustrates that the male subscribers are more likely to check out         a bike during weekdays 



## Summary:
There is a high-level summary of the results and two additional visualizations are suggested for future analysis (5 pt)
