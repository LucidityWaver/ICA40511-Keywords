##Mobile Applications Assessment Task - Learner Driver Logbook

###Note: Images not yet uploaded
![Learner Logbook Main](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/LogbookMain.png)

###The Project
For the mobile applications subject of Holmesglen's IT Cert IV Programming course, students were required to design and create a logbook application for learner drivers. The application must make use of jQuery Mobile and Cordova / Apache Phonegap technologies to create a Web SQL (SQLite) database.

####Project Requirements
The project required documentation and application functions as follows:

- Report format documentation including:
  - Description and purpose of the application
  - Testing documentation
  - Recommendations for future improvements
- Single user only
- Database creation, access and full CRUD operations
- Tables to record data for:
  - the learner driver
  - supervising drivers
  - vehicles used, and
  - trips taken.
- Data entry validation
- Easy navigation
- Follows coding standards
- Custom styling
- Accessible for Android devices

###The Completed Application
My completed learner driver application features:

- A simple, clear layout
- Easy, centralized navigation using a splash screen and only 3 distinct page types:
  1. **The main logbook page**, displaying user information, sum total hours achieved and navigation options.
  2. **Data entry forms**, with a consistent and easy to understand design.
  3. **A 'view records' page**, for each type of record stored. (excepting the learner driver, as there is only one).
- Specialized data entry fields better suited to mobile users
- A modular design for flexibility


#####Splash Page
![Learner Logbook Splash Page](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/LogbookSplash.png)
The splash page is used to give the application time to load, if needed, and add conditional navigation. If there is no user data recorded, the application will navigate to the user entry form instead of the main logbook page.

#####Main Page
![Learner Logbook Main](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/LogbookMain.png)

#####User Entry
![Learner/User Entry Form](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/UserEntry.png)

#####Supervisor Entry
![Supervisor Entry Form](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/SupervisorEntry.png)

#####View Supervisors
![View Supervisor List](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/ViewSupervisors.png)

#####Vehicle Entry
![Vehicle Entry Form](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/VehicleEntry.png)

#####View Vehicles
![View Vehicle List](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/ViewVehicles.png)

#####Manual Trip Entry
![Full Trip Entry Form](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/TripEntry.png)

#####Auto Trip Entry
![Auto Trip Entry Popup](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/AutoTrip.png)

#####View Trips
![View Trip List](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/ViewTrips.png)

#####View Trips
![View Trip List](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/ViewTrips.png)

#####Datebox Plugin
![Datebox Plugin](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/DateboxPlugin.png)

Date and time entry was simplified using the jQueryMobile plugin [DateBox](http://dev.jtsage.com/jQM-DateBox/). This reduced user entry requirements from one field for each year, month, day, hour or minute (or more complex validation for each) to a single field for each date or time combination. Note: The plugin has since been updated to work with jQuery UI and Bootstrap.

#####Form Validation
![Datebox Plugin](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/ValidatePlugin.png)
The validation was performed using the [jQuery Validate Plugin](http://jqueryvalidation.org/)

