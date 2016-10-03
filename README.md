# Scheduling Service

## Aim
This service aims at managing the booking of various resources of the college such as:
* Auditorium
* Guest House
* Conference Room etc.

##Details

* The users will be classified according to the access levels they have for booking the resources. They can be club secretaries, faculty members, Training and Placement Office or the students.
* The priority among these users will be defined (either in our service or the identity service).

##Features
* The users will have a list of resources to choose from.
* The users can select the resource (for example, lecture halls) and then specify the capacity and the time duration for which it is required, and the corresponding results will be displayed.
* The users can book the resources, as well as cancel or modify their bookings from this service.
* The notification of the bookings will be sent to the required people by calling the communication service. The people will be the POC for that resource, as well as the mandatory people for the event for which the resource has been booked.
* The user who has booked the resource will be sent a confirmation mail containing information about the point of contact for that specific booking (regarding keys etc.).
* If a user cancels a booking, that resource becomes immediately available for others.
* (optional) We can even have a waitlist for the people booking a resource, who will be notified in case of any cancellations.

##Database design

Following will be the tables with the corresponding fields:

### Resources Table
* Resource_Id
* Resource_Name
* POC_Id (Point of contact)

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
* Capacity (The resource can accommodate how many people)

###Category Table
* Category
* Number_of_bookings (just in case we have to keep a restriction on the number of booking that can be made by each user).

The time range in which a specific category of users can book a particular resource will be maintained by the identity service (still to be discussed).