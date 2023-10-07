# Hotel Cancellation Predictor

## Table of Contents
1. [Introduction](#Introduction)
2. [File Structure](#FileStructure)
3. [Installing](#Installing)
4. [Feature Documentations](#FeatureDocumentations)

<a name="Introduction"></a>
## Introduction
In the modern hospitality industry, where customer preferences and behaviors are constantly evolving. The ability to anticipate and manage hotel booking cancellations plays a pivotal role in optimizing operations, maximizing revenue, and enhancing customer satisfaction. This predictive capability has the potential to empower hotel management with actionable insights, allowing them to proactively allocate resources, manage inventory, and tailor their strategies to minimize the impact of cancellations. 

Let's delve into the various stages of this machine learning project, from data collection and preprocessing to model selection, training, and evaluation. I will explore the intricacies of the dataset, the methodologies employed to extract meaningful patterns, and the techniques used to fine-tune my models for optimal performance. Moreover, I will discuss the implications of my findings, the practical applications of the predictive models, and the potential avenues for further research and improvement. finally mapping of the models on business metrics and incorporating dynamic thresholding to adapt to the seasonality inherent in the hospitality industry. I will 

The [original dataset](https://www.sciencedirect.com/science/article/pii/S2352340918315191) was created by the article Hotel Booking Demand Datasets, by Nuno Antonio, Ana Almeida, and Luis Nunes for Data in Brief, Volume 22, February 2019.

<a name="FileStructure"></a>
## File Structure
Each of the following project steps is completed in a separate notebook:
- [Raw Data](https://github.com/YimingZ13/Hotel_cancellation_predictor_with_dynamic_thresholding/blob/main/hotel_bookings.csv): `hotel_bookings.csv`
- [Data Cleaning](): `hotel_cleaning.ipynb`
- [Exploratory Analysis](): `hotel_eda.ipynb`
- [Data Preprocessing](): `hotel_preprocessing.ipynb`
- [Modelling](): `hotel_modelling.ipynb`

<a name="Installing"></a>
## Installing

<a name="FeatureDocumentations"></a>
## Feature Documentations
- `ADR`: Average Daily Rate (Calculated by dividing the sum of all lodging transactions by the total number of staying nights)
- `Adults`: Number of adults
- `Agent`: ID of the travel agency that made the booking (If 0.0 was given, it means that the booking was made without one)
- `ArrivalDateDayOfMonth`: Day of the month of the arrival date
- `ArrivalDateMonth`: Month of arrival date with 12 categories: “January” to “December”
- `ArrivalDateWeekNumber`: Week number of the arrival date
- `ArrivalDateYear`: Year of arrival date
- `AssignedRoomType`: Code for the type of room assigned to the booking. Sometimes the assigned room type differs from the reserved room type due to hotel operation reasons (e.g. overbooking) or by customer request. Code is presented instead of designation for anonymity reasons
- `Babies`: Number of babies
- `BookingChanges`: Number of changes/amendments made to the booking from the moment the booking was entered on the PMS until the moment of check-in or cancellation (Calculated by adding the number of unique iterations that change some of the booking attributes, namely: persons, arrival date, nights, reserved room type or meal)
- `Children`: Number of children (Sum of both payable and non-payable children)
- `Company`: ID of the company/entity that made the booking or responsible for paying the booking. ID is presented instead of designation for anonymity reasons	(If 0.0 was given, it means that the booking is private)
- `Country`: Country of origin. Categories are represented in the ISO 3155–3:2013 format
- `CustomerType`: Type of booking, assuming one of four categories:	
    - Contract - when the booking has an allotment or other type of contract associated to it; 
    - Group – when the booking is associated to a group; 
    - Transient – when the booking is not part of a group or contract, and is not associated to other transient booking; 
    - Transient-party – when the booking is transient, but is associated to at least other transient booking
- `DaysInWaitingList`: Number of days the booking was in the waiting list before it was confirmed to the customer (Calculated by subtracting the date the booking was confirmed to the customer from the date the booking entered on the PMS)
- `DepositType`: Indication on if the customer made a deposit to guarantee the booking. This variable can assume three categories: (Calculated based on the payments identified for the booking in the transaction (TR) table before the booking׳s arrival or cancellation date.) 
    - No Deposit – no deposit was made; (In case no payments were found the value is “No Deposit”.) 
    - Non Refund – a deposit was made in the value of the total stay cost; (If the payment was equal or exceeded the total cost of stay, the value is set as “Non Refund”.)
    - Refundable – a deposit was made with a value under the total cost of stay. (Otherwise the value is set as “Refundable”)
- `DistributionChannel`: Booking distribution channel. The term “TA” means “Travel Agents” and “TO” means “Tour Operators”
- `IsCanceled`: Value indicating if the booking was canceled (1) or not (0)
- `IsRepeatedGuest`: Value indicating if the booking name was from a repeated guest (1) or not (0) (Variable created by verifying if a profile was associated with the booking customer. If so, and if the customer profile creation date was prior to the creation date for the booking on the PMS database it was assumed the booking was from a repeated guest)
- `LeadTime`: Number of days that elapsed between the entering date of the booking into the PMS and the arrival date (Subtraction of the entering date from the arrival date)
- `MarketSegment`: Market segment designation. In categories, the term “TA” means “Travel Agents” and “TO” means “Tour Operators”
- `Meal`: Type of meal booked. Categories are presented in standard hospitality meal packages:
    - Undefined/SC – no meal package;
    - BB – Bed & Breakfast;
    - HB – Half board (breakfast and one other meal – usually dinner);
    - FB – Full board (breakfast, lunch and dinner)
- `PreviousBookingsNotCanceled`: Number of previous bookings not cancelled by the customer prior to the current booking	(In case there was no customer profile associated with the booking, the value is set to 0. Otherwise, the value is the number of bookings with the same customer profile created before the current booking and not canceled.)
- `PreviousCancellations`: Number of previous bookings that were cancelled by the customer prior to the current booking	(In case there was no customer profile associated with the booking, the value is set to 0. Otherwise, the value is the number of bookings with the same customer profile created before the current booking and canceled.)
- `RequiredCardParkingSpaces`: Number of car parking spaces required by the customer
- `ReservationStatus`: Reservation last status, assuming one of three categories:
    - Canceled – booking was canceled by the customer;
    - Check-Out – customer has checked in but already departed;
    - No-Show – customer did not check-in and did inform the hotel of the reason why
- `ReservationStatusDate`: Date at which the last status was set. This variable can be used in conjunction with the ReservationStatus to understand when was the booking canceled or when did the customer checked-out of the hotel
- `ReservedRoomType`: Code of room type reserved. Code is presented instead of designation for anonymity reasons
- `StaysInWeekendNights`: Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hotel	(Calculated by counting the number of weekend nights from the total number of nights)
- `StaysInWeekNights`: Number of week nights (Monday to Friday) the guest stayed or booked to stay at the hotel	(Calculated by counting the number of week nights from the total number of nights)
- `TotalOfSpecialRequests`: Number of special requests made by the customer (e.g. twin bed or high floor)
