##Web Design Assessment Task

###The Project
For the web development component of Holmesglen's IT Cert IV Programming course, students were required to design and create a website for the fictional company Hamilton IT Consulting. The website should follow the web design principles detailed in the course and facilitate interaction with a MySQL database using PHP.

###The Completed Website

The website includes three content pages, a semi functional PHP login and pages using PHP for database interaction.

To create the core of the website, I implemented a three-column fluid-grid layout using CSS. This system moves content in from the edge of the screen to create a better aesthetic and is accessible across different screen sizes. The design needed to be altered for the contact-us page to suit an embedded map across two columns.

The design can be seen in the images below.

#####Home Page
![Hamilton IT Consulting Home Page](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonHome.png)

#####Our Service Page
![Hamilton IT Consulting Our Service Page](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonOurService.png)

#####Contact Us Page
![Hamilton IT Consulting Contact Us Page](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonContactUs.png)

####Home Page - Tablet Sized Layout

![Hamilton IT Consulting Home Page - Tablet Sizing](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonHomeTablet.png)

To save space the mobile layout image hasn't been embedded, but it can be viewed separately at the following link:
[Mobile Layout](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonHomeTablet.png)


####Database Tables
The tables on the website are created dynamically using column names and datatypes retrieved from the database table.

Additionally, the table information was made sortable and responsive client-side using a jQuery plugin - [Tablesaw v2.0.2](https://github.com/filamentgroup/tablesaw)

#####Consultant Table
![Hamilton IT Consulting - Consultant Table](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonConsultantTable.png)

#####Project Table
![Hamilton IT Consulting - Project Table](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonProjectTable.png)


#####Project-Consultant Table
The task required use of a select menu to filter the final table; a bridging table recording the consultants assigned to each project.
![Hamilton IT Consulting - Project Consultant Table](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonProjectConsultantTable.png)


####Data Entry Forms
The forms used for data entry are also created dynamically from the database table. Fields lengths are given an upper limit and maximum character limits are locked to the length allowable by the schema.

#####Consultant Table
![Hamilton IT Consulting - Consultant Form](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonEnterConsultant.png)

#####Project Table
Entry of dates is made easy using the jQuery plugin - [Datepick v5.01](http://keith-wood.name/datepick.HTML).
![Hamilton IT Consulting - Project Form Table](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonEnterProject.png)


#####Project-Consultant Table
This form locks the Project Number field, as the desired project must already have been selected. A select menu is provided for the consultant to be assigned to the project, showing only those which are not already assigned to the project (and the current consultant, if editing a record).
![Hamilton IT Consulting - Assign Project Consultant Form Table](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/images/HamiltonEnterProjectConsultant.png)


###The Development Process


####Project Requirements
The project was to be delivered in 3 stages:

1. A prototype including:
  - A color scheme
  - Three pages (home, content/services and contact-us)
  - A custom banner and logo
  - Separate CSS files and styles
2. A set of PHP pages for database interaction, including:
  - CRUD operations (view, add, edit and delete) for project and staff tables.
  - Form validation (using PHP only; no javascript)
  - Pseudo-code for one validation function
3. Completed website including:
  - CRUD operations on the bridging table for project-staff (staff assigned to a project)
  - A select menu to choose which project's staff should be displayed
  - Pseudo-code describing assigning a consultant to a project
  - A flowchart describing updating a staff assignment

####Part 1: Responsive Web Design
