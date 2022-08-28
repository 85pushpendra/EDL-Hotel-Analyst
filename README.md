# EDA-Hotel-Analyst
## Objective
I have provided with a hotel bookings dataset.

Out main objective is perform EDA on the given dataset and draw useful conclusions about general trends in hotel bookings and how factors governing hotel bookings interact with each other.
## Dataset
###  | Column                          |Non-Null Count   |Dtype     |Discription 
---  | ------                          |--------------   |-----     |-----------
 0   | hotel                           |119390 non-null  |object    |Name of hotel
 1   | is_canceled                     |119390 non-null  |int64     |Whether the booking is canceled or not
 2   | lead_time                       |119390 non-null  |int64     |time (in days) between booking transaction and actual arrival.
 3   | arrival_date_year               |119390 non-null  |int64     |Year of arrival
 4   | arrival_date_month              |119390 non-null  |object    |month of arrival
 5   | arrival_date_week_number        |119390 non-null  |int64     |week number of arrival date.
 6   | arrival_date_day_of_month       |119390 non-null  |int64     |Day of month of arrival date
 7   | stays_in_weekend_nights         |119390 non-null  |int64     |No. of weekend nights spent in a hotel
 8   | stays_in_week_nights            |119390 non-null  |int64     |No. of weeknights spent in a hotel
 9   | adults                          |119390 non-null  |int64     |No. of adults in single booking record.
 10  | children                        |119386 non-null  |float64   |No. of children in single booking record.
 11  | babies                          |119390 non-null  |int64     |No. of babies in single booking record.
 12  | meal                            |119390 non-null  |object    |Type of meal chosen
 13  | country                         |118902 non-null  |object    |Country of origin of customers (as mentioned by them)
 14  | market_segment                  |119390 non-null  |object    |What segment via booking was made and for what purpose.
 15  | distribution_channel            |119390 non-null  |object    |Via which medium booking was made.
 16  | is_repeated_guest               |119390 non-null  |int64     |Whether the customer has made any booking before
 17  | previous_cancellations          |119390 non-null  |int64     |No. of previous canceled bookings.
 18  | previous_bookings_not_canceled  |119390 non-null  |int64     |No. of previous non-canceled bookings.
 19  | reserved_room_type              |119390 non-null  |object    |Room type reserved by a customer.
 20  | assigned_room_type              |119390 non-null  |object    |Room type assigned to the customer.
 21  | booking_changes                 |119390 non-null  |int64     |No. of booking changes done by customers
 22  | deposit_type                    |119390 non-null  |object    |Type of deposit at the time of making a booking
 23  | agent                           |103050 non-null  |float64   |Id of agent for booking
 24  | company                         |6797 non-null    |float64   |Id of the company making a booking
 25  | days_in_waiting_list            |119390 non-null  |int64     |No. of days on waiting list.
 26  | customer_type                   |119390 non-null  |object    |Type of customer
 27  | adr                             |119390 non-null  |float64   |Average Daily rate.
 28  | required_car_parking_spaces     |119390 non-null  |int64     |No. of car parking asked in booking
 29  | total_of_special_requests       |119390 non-null  |int64     |total no. of special request.
 30  | reservation_status              |119390 non-null  |object    |Whether a customer has checked out or canceled,or not showed 
 31  | reservation_status_date         |119390 non-null  |object    |Date of making reservation status.


dtypes: float64(4), int64(16), object(12)
Total number of rows in data: 119390
Total number of columns: 32
## Data Cleaning and Feature Engineering
### (1) Removing Duplicate rows
All duplicate rows were dropped.

### (2) Handling null values
- Null values in columns `company` and `agent` were replaced by 0.
- Null values in column `country` were replaced by 'others'.
- Null values in column `children` were replaced by the mean of the column.
  

### (3) Converting columns to appropriate data types

- Changed data type of `children`, `company`, `agent` to int type.
- Changed data type of `reservation_status_date` to date type.

### (4) Removing outliers

- One outlier was found in the `adr` column. Simply dropped it.

### (5) Creating new columns
- Created new column `total_stay` by adding `stays_in_weekend_nights`+`stays_in_week_nights`.
- Created new column `total_people` by adding `adults`+`children`+`babies`.

## Exploratory Data Analysis

Performed EDA and tried answering the following questions?
Question1: Creat a correlation matrix?
Question2: Assess the data and plot a graph for number of booking by agents?
Qusestion3: Which room type is in most demand and which room type generatest highest adr?
Question4: Which countries most of the customers are visiting these hotels?
Question5: Calculate the percentage of bookings in each hotel?
Question6: What is preferred stay in each hotel?
Question7: Which hotel has higher bookings cancellation rate?
Question8: Which channel is mostly used for early booking of hotels?
Question9: Which significant distribution channel has highest cancellation percentage?
Question 10: what causes the cancelation of bookings of rooms by customers \ \ One question can arise that may be longer waiting period or longer lead time causes the cancellation of bookings, let us check that?

Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:
   -  Bar Plot.
   -  Histogram.
   - Scatter Plot.
   - Pie Chart.
   - Line Plot.
   - Heatmap.
   - Box Plot
     
     ###  Univariate Analysis:

Performed univariate analysis and made following conclusions:
```
 1.) Agent no. 9 has made most no. of bookings.
 2.) Most demanded room type is A, but better adr generating rooms H, G and C. Hotels should increase the no. of room types A and H to maximise revenue.
 3.) Most popular meal type is BB(Bed and Breakfast).
 4.) Around 60% bookings are for City hotel and 40% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel.
 5.) Guests use different channels for making bookings out of which most preferred way is TA/TO.
 6.) July- August are the most busier and profitable months for both of hotels. 
 7.) Most of the guests came from european countries, with highest number of guests from Portugal.
 8.) Most common stay length is less than 4 days and generally people prefer City hotel for short stay, but for long stays, Resort Hotel is preferred.
 
```
### Bivariate Analysis :

We tried to answer following questions
```
 1.) Overall adr of City hotel is slightly higher than Resort hotel and no. of bookings of City hotel is also higher than Resort hotel. Hence, City hotel is makes more revenue.
 2.) City hotel has slightly higher median lead time. Also median lead time is significantly higher for both hotels, this means customers generally plan their hotel   visits way early.
 3.) Almost 30 % of City Hotel bookings got canceled.
 4.) Both hotels have very small percentage that customer will repeat, but Resort hotel has slightly higher repeat % than City Hotel.
 5.) TA/TO is mostly used for planning Hotel visits well ahead of time. 
 6.) While booking via TA/TO one may have to wait a little longer to confirm booking of rooms.
 7.) GDS channel brings higher revenue generating deals for City hotel, in contrast to that most bookings come via TA/TO. City Hotel can work to increase outreach on GDS channels to get more higher revenue generating deals.
 8.) TA/TO has highest booking cancellation %. Therefore, a booking via TA/TO is 30% likely to get cancelled.
 9.) Longer lead time has no affect on cancellation of bookings.
 10.) Not getting same room as demanded is not the case of cancellation of rooms. A significant percentage of bookings are not cancelled even after getting different room as demanded.
 11.) Not getting same room do affects the adr, people who didn't got same room have paid a little lower adr. 
 12.) Arrivals in hotels increases at weekends and also the avg adr tends to go up as month ends. 
 13.)Moslty bookings are done by couples(bookings have two adults.)
```

## Conclusion

```
(1) Around 60% bookings are for City hotel and 40% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel. Also the overall adr of City hotel is slightly higher than Resort hotel.
(2) Mostly guests stay for less than 5 days in hotel and for longer stays Resort hotel is preferred.
(3) Both hotels have significantly higher booking cancellation rates and very few guests less than 3 % return for another booking in City hotel. 5% guests return for stay in Resort hotel.
(4) Most of the guests came from european countries, with most of guests coming from Portugal.
(5) Guests use different channels for making bookings out of which most preferred way is TA/TO.
(6) For hotels higher adr deals come via GDS channel, so hotels should increase their popularity on this channel.
(7) Almost 30% of bookings via TA/TO are cancelled.
(8) Not getting same room as reserved, longer lead time and waiting time do not affect cancellation of bookings. Although different room allotment do lowers the adr.
(9) July- August are the most busier and profitable months for both of hotels. 
(10) Within a month, adr gradually increases as month ends, with small sudden rise on weekends.
(11) Couples are the most common guests for hotels, hence hotels can plan services according to couples needs to increase revenue.
(12) More number of people in guests results in more number of special requests.
(13) Bookings made via complementary market segment and adults have on average high no. of special request.
(14) For customers, generally the longer stays (more than 15 days) can result in better deals in terms of low adr.

And many more conclusions.
```
## Challenges
```
(1) There was a lot of duplicate data.
(2) Data was present in wrong datatype format.
(3) Choosing appropriate visualization techniques to use was difficult.
(4) A lot of null values were there in the dataset.
