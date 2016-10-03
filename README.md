# Scheduling Service

## Aim
This service aims at managing the booking of various resources of the college such as:
* Auditorium
* Guest House
* Conference Rooms
* Lecture Halls

## Details

* The users will be classified according to the access levels they have for booking the resources. They can be club secretaries, faculty members, departments or students.
* The priority among these users will be defined in our service.

## Features
* Users will have a list of resources to choose from.
* Users can select the appropriate resource (for example, lecture halls) and then specify the date and time duration for which it is required. Corresponding results will be displayed. They also need to specify the reason for making this booking.
* Users can book resources, as well as cancel or modify their bookings using this service.
* Notification of the bookings will be sent to the required people by calling the communication service. These people will be the POC for that resource, as well as the mandatory people for the event for which the resource has been booked.
* User who has booked the resource, upon approval by the authorities, will be sent a confirmation mail containing information about the point of contact for that specific booking (regarding keys etc.).
* If a user cancels a booking, that resource becomes immediately available for others.
* (optional) We can even have a waitlist for the people booking a resource, who will be notified in case of any cancellation.

## Database design

Following will be the tables with the corresponding fields:

###Resources Table
* Resource_Id
* Resource_Name
* Capacity (Number of people that can be accomodated)
* POC_Id (Point of contact)
* WiFi
* Projector
* AC

###POC Table
* POC_Id
* Name
* Email_Id
* Contact_Number

###Bookings Table
* Resource_Id
* User_Id
* Date
* Start_Time
* End_Time
* TimeStamp
This table can undergo changes in its schema depending on the requirements, for example, if an approval is needed to book a resource. 

###Category Table
* Category
* Number_of_bookings (just in case we have to keep a restriction on the number of booking that can be made by a user).
Other access privileges can be defined in this table.
