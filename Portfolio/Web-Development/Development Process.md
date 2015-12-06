##Web Design Assessment Task - Development Process

###Table of Contents:
######Project Overview
- [Project Requirements](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#base-project-requirements)
- [Additional Features](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#additional-features)

######Design
- [Responsive Web Design](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#responsive-web-design)
- [Collapsible Sets](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#collapsible-sets)

######jQuery Plugins
- [Datepick](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#datepick)
- [Tablesaw](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#tablesaw)

######PHP
- [Login](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#login)
- [Database Connection](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#database-connection)
- [Generate Database Table](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#generate-tables)
- [Generate Data Entry Form](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#generate-forms)
- [Validation](https://github.com/LucidityWaver/ICA40511-NotesAndKeywords/blob/master/Portfolio/Web-Development/Development%20Process.md#validation)

###Overview (Requirements and Features)

#####Base Project Requirements
The project was required to be delivered in 3 stages:

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

#####Additional Features
Grouped by project stage, the full list of features for the website are as follows.

1. Prototype
  - Responsive design layout using fluid grids
  - Collapsible sets
  - Embedded Map
  - Other custom CSS styling

2. Basic Database Operations
  - Single page for generating tables from database
  - Single page for generating forms from db tables
  - Responsive and sortable tables with Tablesaw plugin
  - Date selection with Datepick plugin
  - Some referential integrity ensured on update or delete
  - Form validation

3. Bridge Table Operations & Finalization
  - Functioning PHP login (fake authentication)
  - Select menu to filter bridging table
  - Select menu for consultant assignment to projects
  - Ensures referential integrity on update and delete

###Design
#####Responsive Web Design
[Responsive Web Design](https://en.wikipedia.org/wiki/Responsive_web_design) (RWD) refers to the method of delivering the same content in a consistent design to devices or screens of different sizes.

I achieved this using [CSS media queries](http://www.w3schools.com/cssref/css3_pr_mediaquery.asp), [the viewport meta tag](http://www.w3schools.com/css/css_rwd_viewport.asp) and a three-column fluid-grid layout. The website layout and display is altered based on the detected window, device or screen size as follows:
- Mobile device sizing up to 480px
- Tablet widths from 481px to 768px
- Desktop sizing from 769px to 1232px

Note:  For modern web browsers (IE10 or above), the use of fluid-grids and floated elements for layout is discouraged.

The HTML:
```html
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
<body>
  <!-- Banner & Navigation -->
  <div class="gridContainer clearfix"> <!-- gridContainer and clearfix classes described below -->
    <div class="fluid fluidGridOne material"> <!-- material class to add background -->
      <h2 class="contentHeader">About Us</h2> <!-- contentHeader class just used to center text headers -->
      <!-- Section content -->
    </div>
    <div class="fluid fluidGridTwo material">
      <h2 class="contentHeader">About Us</h2>
      <!-- Section content -->
    </div>
	  <div class="fluid fluidGridThree material" >
	    <h2 class="contentHeader">Our Projects</h2>
      <!-- Section content -->
		  
		</div>
  </div>
  <!-- Footer -->
</body>
```



The CSS:
```css
.fluid {
	clear: both;
	margin-left: 0;
	width: 100%;
	float: left;
	display: block;
}

/* Mobile Layout: 480px and below. */
/* no media query; these are the default styles as per the mobile-first approach */
.gridContainer {
	margin-left: auto;
	margin-right: auto;
	width: 88.0326%;
	padding-left: 1.4836%;
	padding-right: 1.4836%;
	clear: none;
	float: none;
}
```

The fluid class identifies content blocks, clearing them of floating elements and floating them left.
The gridContainer class is used as a container for the content blocks and specifies padding left and right.

```css
/* General layout grids */
.fluidGridOne {
	width: 100%;
}
.fluidGridTwo {
	width: 100%;
	clear: both;
}
.fluidGridThree {
	width: 100%;
	clear: both;
}
```

The content blocks are marked as belonging to the first, second or third column and provided a standard size (used for mobile size display).

```css
/* Tablet Layout: 481px to 768px. Inherits styles from: Mobile Layout. */

@media screen and (min-width: 481px) {

  .gridContainer {
  	width: 91.4836%;
  	padding-left: 0.7581%;
  	padding-right: 0.7581%;
  	clear: none;
  	float: none;
  	margin-left: auto;
  }
  
  /* General layout grids */
  .fluidGridOne {
  	width: 49.1712%;
  }
  .fluidGridTwo {
  	width: 49.1712%;
  	clear: none;
  	margin-left: 1.6574%;
  }
  .fluidGridThree {
  	width: 100%;
  	clear: none;
  	margin-left: 1.6574%;
  }
}
```

The media query rule is used to apply these styles only for screens above 480px. At this size, the first two sections are displayed side by side with the third section displaying at full width. The left and right padding is also adjusted for this size.

```css

/* Desktop Layout: 769px to a max of 1232px.  Inherits styles from: Mobile Layout and Tablet Layout. */
@media screen and (min-width: 769px) {
  .gridContainer {
  	width: 89.0217%;
  	max-width: 1232px;
  	padding-left: 0.4891%;
  	padding-right: 0.4891%;
  	margin: auto;
  	clear: none;
  	float: none;
  }
  /*General layout */
  .fluidGridOne {
  	width: 32.6007%;
  }
  .fluidGridTwo {
  	width: 32.6007%;
  	margin-left: 1.0989%;
  	clear: none;
  }
  .fluidGridThree {
  	width: 32.6007%;
  	clear: none;
  	margin-left: 1.0989%;
  }
}
```

This final rule applies for desktop sizing -- above 768px -- and allows all three content blocks to display side by side, each taking up about one third of the page.


In addition to thie above, a few other css styles are required to make this work and display consistently.
```css
img, object, embed, video {
	max-width: 100%;
}
html, body {
	margin: 0;
	padding: 0;
}
div, h1, h2, h3, h4, h5, h6, p, ul, ol, dl, li, dt, dd, address, blockquote {
	margin: 0;
	padding: 0;
	color: #000;
}

.clearfix:before, .clearfix:after { content: ""; display: table; }
.clearfix:after { clear: both; }
.clearfix { *zoom: 1; }
```

- Image, object, embed and video elements are set to a max width of 100% (of the width of their container)
- Standard margins and paddings are removed
- The clearfix class is used to ensure a parent element containing only floating elements does not collapse.
- A [boilerplate](https://github.com/h5bp/html5-boilerplate) (v3.0.2) to help achieve cross-browser support has also been included. 


#####Collapsible Sets

###jQuery Plugins
#####Datepick
#####Tablesaw


###PHP
#####Login
#####Database Connection
#####Generate Tables
#####Generate Forms
#####Validation
