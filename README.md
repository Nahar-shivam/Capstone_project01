# HOTEL BOOKING ANALYSIS 

## Objective
Our primary goal is to perform EDA on the provided dataset and try to find out hidden trends and patterns in the data and derive valuable conclusions about hotel booking trends and how various factors interact to affect hotel bookings.After the complete analysis I have to provide solutions to business objectives and conclusions about the analysis.
## Dataset
The given dataset contain the booking information of city and resort hotels. The dataset consist of 119390 rows and 32 columns and the variables are of different data types like object, integer and float.
 - hotel: Name of hotel ( City or Resort)
 - is_canceled: Whether the booking is canceled or not (0 for no canceled and 1 for canceled)
 - lead_time: time (in days) between booking transaction and actual arrival.
 - arrival_date_year: Year of arrival
 - arrival_date_month: month of arrival
 - arrival_date_week_number: week number of arrival date.
 - arrival_date_day_of_month: Day of month of arrival date
 - stays_in_weekend_nights: No. of weekend nights spent in a hotel
 - stays_in_week_nights: No. of weeknights spent in a hotel
 - adults: No. of adults in single booking record.
 - children: No. of children in single booking record.
 - babies: No. of babies in single booking record. 
 - meal: Type of meal chosen 
 - country: Country of origin of customers
 - market_segment: What segment via booking was made and for what purpose.
 - distribution_channel: Via which medium booking was made.
 - is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for Yes)
 - previous_cancellations: No. of previous canceled bookings.
 - previous_bookings_not_canceled: No. of previous non-canceled bookings.
 - reserved_room_type: Room type reserved by a customer.
 - assigned_room_type: Room type assigned to the customer.
 - booking_changes: No. of booking changes done by customers
 - deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
 - agent: Id of agent for booking
 - company: Id of the company making a booking
 - days_in_waiting_list: No. of days on waiting list.
 - customer_type: Type of customer(Transient, Group, etc.)
 - adr: Average Daily rate.
 - required_car_parking_spaces: No. of car parking asked in booking
 - total_of_special_requests: total no. of special request.
 - reservation_status: Whether a customer has checked out or canceled,or not showed 
 - reservation_status_date: Date of making reservation status

## Data cleaning and manipulation
 ### Removing Duplicate values
 - Drop all the duplicates rows. At the starting I have 119390 rows and 32 columns, after removing the duplicates  rows (31994) from the dataset, 87396 rows and 32 columns are remaining in dataset.
 ### Handling Null / Missing Values
 - Children, country, and agent are discrete numerical variables, so replaced null values with mode of it.
 - Variable company had null values greater than 50%, so removed it.
 ### Handling and removing outliers
 - Interquartile Range in the skew symmetric curve used to remove outliers found in the lead_time and adr variables.
 ### Converting Columns to Appropriate Data Types
 - Datatypes of variables "children," "agent," "reservation_status_date," "total_people," and "total_children" were transformed from float64 datatypes to int64.
 - Datatype of the variable "reservation_status_date" was transformed from object datatype to datetime64.
 ### Created New Columns
 - The variable "total_stay" is created by adding the variables "stays_in_weekend_nights" and "stays_in_weeknights."
 - The variable "total_people" is created by adding the variables "adults," "children," and "babies."
 - The variable "reserved_room_assigned" is made up of the variables "reserved_room_type" and "assigned_room_type."
 - From variables "children" and "babies," a new "total_children" variable is created by adding both of them.
 - The variable "total_people" used to create "guest_category."
## Exploratory Data Analysis
I performed EDA and tried answering the following questions:
 01. Which type of hotel is mostly preferred by the people ?
 02. What are the most common types of room booked and by what kind of customer ?
 03. Which distribution channels have the most cancellations of bookings?
 04. What is the percentage of repeated guest?
 05. In which month most of the bookings happened?
 06. In terms of hotel types, how many parking spaces are most frequently requested by customers?
 07. Which room generates a higher ADR?
 08. What is the most common number of special requests made by customers, and what kind of customer are they?
 09. Which distribution channel contributed more to adr in order to increase the income?
 10. Which type of hotel is mainly suitable for stay in week night with repect to short or long duration by the customers ?
 11. Which month is the busiest for hotels?
 12. Which customer type generates more revenue in terms of hotel types and customer types?
 13. Is the ADR affected by the hotel not giving a reserved room?
 
 These following graphs and plots were primarily created and  used using Matplotlib and the Seaborn package.
 - Pie chart
 - Count plot
 - Bar plot
 - Box plot
 - Heatmap
 - Pairplot

 ## Solutions to business objectives
- A city hotel has more bookings than a resort.So resort hotels should offer packages and promotions to promote bookings and management team should insure that the facilities are provide according to the customers needs. The resort hotels can also apply the same facilities like city hotels to attract the people.
- Hotel managment should manage the staff according to the months, increase the staff ratio in month of august and september and reduce the staff ratio in other months according to booking ratios in different months, this helps to reduce the cost.
- Most of the bookings are made through the online platform. Hotels can cut costs by eliminating market segments such as complementary and aviation because bookings through these segments are very low.
- Because most bookings made through TA/TO distribution are followed by corporate distribution, hotels should invest in both TA/TO and corporate distribution channels. The GDS distribution channel can be eliminated by resort hotels because bookings made through it are extremely low.
- Very few customers (3.86%) visited again. So hotels can increase repeat bookings by offering the right repeat booking incentives, understanding the motivations behind repeat bookings, marketing to your guest past interests, and assessing past bookings to identify priority guests.
- Because rooms A and D are the most popular with customers, the hotel should maintain their quality. The hotel should promote rooms E, F, and G to increase demand by offering discounts.
- Because customers do not prefer to book room types B, C, H, and L, the hotel can eliminate them, lowering the cost of these rooms.
- Hotels should eliminate room type I and K because they generates very low adr which leads to low growth in revenue.
- Customers do not want to pay a pre-deposit for a reservation. Hotels should promote advance deposits because not only does an advance deposit allow you to recognize revenue faster, it also greatly decreases the risk of cancellations.
- Because 3 and 8 parking spaces were rarely requested by customers, hotels can only keep bookings for 1 and 2 parking spaces to save money.
- 15% of customers were not given reserved rooms. Make sure that guests get the rooms they have booked.
- Almost 25% of customers cancelled their bookings. Hotel should implement a cancellation policy, discount on confirmed bookings, and send booking reminders to guests to reduce booking cancellations.
- People typically book rooms for two people, so encourage family and group bookings. You can maximize revenue by promoting it with a discounted offer for group bookings.
- Overall city hotels should tries to improve their existing facilities to attract more people and implement new offers and discounts for customers. and Resort hotels should take feedback from the customers to improve the services and facilities.

## Conclusion
- Overall city hotels perfome well as compare to resort hotels. City hotels generates high revenue and show more bookings.
- Customers favored city hotels more than resort hotels by a margin of 61.07 percent.
- Resort hotels are more comfortable and preferred by the people for a long stay.
- The Online (internet) platform is used to make the majority of bookings.
- The majority of the bookings are made using TA/TO, the leading distribution channel.
- The vast majority of hotel bookings are made by new guests. Almost no consumers (3.86%) returned.
- The customer wants Room A to be reserved the most.
- Most of the bookings were done by the couples.
- Customers (80%) favored making a hotel reservation for a short visit.
- Only 10% of people require space to park their cars.
- The inability to assign a reserved room to a customer is not grounds for cancellation.
- Booking cancellations are not caused by a longer Lead time.
- A city hotel is busier than a resort.
- The busiest months for hotels are August, October and September. There isn't a lengthy wait for reservations in July.
- Not assigning a reserved room does not affect ADR.
