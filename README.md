# EDL-Hotel-Analyst
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
