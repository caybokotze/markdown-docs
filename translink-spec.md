[![N|Solid](https://translink.merge.africa/assets/Translink-Logo-450.png)](https://merge.africa)

# Translink Specificications Document

*Translink is a CRM focused on solving the problems faced by logistics companies in the modern day. The specifications outlined in the following document exist to solve those problems for small to medium sized logistics firms.*
## ERD
[![N|Solid](https://raw.githubusercontent.com/mergeafrica/public-resources/master/translink/erd/translink_crm.png)](https://translink.merge.africa)
### Definition of User roles throughout the application:
- Administrator
- Driver
- Site Manager
- Support Staff
- Accounting
- Executive Members
- 

### Core features description:
The core features of the translink CRM are to achieve the following:
- Record a listing of shipments that companies make.
- Record shipment metrics.
- Keep track of shipments.
- Keep track of drivers.
- Create efficient trip plans, and route plans for shipments to save cost.

*In essence the system comes down to having the ability to create shipments, which contain shipment information (weight, volume, item description, title) and creating trips, which allow the users of the system to plan out a delivery schedule for trips. Shipments can be created initially, either manually or automatically, then those shipment items are added to a trip.  A trip is a representation of a truck hauling items to the different locations where they need to be. Every stop could represent one or more shipment items. A trip should normally have at least one driver and one vehicle associated with it. A trip also contains a route plan, which is optimized to save the company cost by having a nice effective way to track when shipments should be delivered and how long it should take, how much miliage should be incurred, etc... Call support agents can then follow up on shipments that have not been delivered when they have meant to be delivered. Drivers should tick off shipments on trips when they are delivered to provide feedback on progress and to make it easier for the company and customers to track deliveries.*

# Login / Logout
### All users
 >  A user with any ranking needs to be able to create a user profile.
 
 > A user whom has created a user profile needs to be able to log into the system.
 
 > The system needs to contain at least one user with the role of "Administrator". At any point in time the database should be seeded with at least one 'priviledged' user.
 
 > A user, after loggin in, should be able to log out.
 
 > User authentication cookies should only be cached for 30 days, after which the user should be forced to log in again, on that device.
 
 > User Password data should be 'hashed' with a unique salt value which can be stored in the same user table.
 ### Administrators
 > Should be able to view all the area's of the system without any restrictions. Full read / write access throughout the entire system.
 
### Executive Members
> Should be allowed to view a summary of the company operations, but not the day to day activities. For example, an executive member, should be able to generate a report summary for the companies sales, but not be able to view all the client and employee information. (Unless granted access by an administrator)

### Site Managers
> Should be allowed to generate and view sales reports, order summaries, trip plans, invoices, customers etc.

> A site manager should not be allowed to delete any information without administrative permission.

### Support Staff
> Should be allowed to view support ticket items and respond to support queries.

> Should be able to view the shipments that are currently out.

### Workflow Diagram
[![N|Solid](https://raw.githubusercontent.com/mergeafrica/public-resources/master/translink/flow-diagrams/Register.png)](https://translink.merge.africa)

# Add Shipment
_Management of shipments are one of the core translink features. Managing shipments should be easy for the users of the system to add new products to a shipment and allocate a vehicle to the shipment that needs to be made._

> A shipment number should be automatically generated and displayed for user reference.

> A user should be able to select a product to be shipped on the shipment form.

> A user should be able to assign a vehicle (by license plate number) to a shipment.

> A user should be able to select a driver that should be allocated to a specific shipment.

> A user should be able to add an estimated distance to the shipment. (This data can also be prepulated using the google maps api.)

> A user should be able to select a departure date.

> As a user I expect the delivery date to be autofilled, and can be corrected if necessary.

### Workflow
[![N|Solid](https://raw.githubusercontent.com/caybokotze/markdown-docs/main/shipment.png)](https://translink.merge.africa)

# Add Trip
_The trip builder is the feature that will allow logistics companies / curriers to be able to plan out the trips that they would like to make and all of the stops that will need to be made to make the delivery._

> A user should be able to create a trip. The trip number should be autogenerated and displayed for user reference.

> A user should be able to set the departure date for the trip.

> A user should be able to allocate a driver to the trip.

> A user should be able to allocate a vehicle to the trip.

> The total distance of the trip should be calculated from all the shipments that are onboard.

> A stop should be created for every shipment.

> A route for a planned trip should be created where shipment deliveries are as close to each other as possible. This can be done manually as well, however eventually it can be automated as well (Google distance calculator / trip delivery estimate)

> When the trip has been created, the route planner for that trip should appear.

> Estimates for a trip, such as estimated fuel consumption, distance, etc can automatically be calculated based on metrics from within the shipments in the trip.

### Workflow diagram
[![N|Solid](https://raw.githubusercontent.com/caybokotze/markdown-docs/main/trip-planner.png)](https://translink.merge.africa)

