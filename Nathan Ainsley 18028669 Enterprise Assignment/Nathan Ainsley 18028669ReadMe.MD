#ReadMe.MD

##Nathan Ainsley 18028669

###Table of Contents
1. [Basic Http Interface](#Basic HTTP Interface)
1.1 [Interface Introduction](#Interface Introduction)
1.1.1 [Add Film](#Add Film)
1.1.2 [Searching Overview](#Searching Overview)
1.1.3 [All Films](#All Films)
1.1.4 [Search Films](#Search Films)
1.1.5 [Edit Mode](#Searching Films)
1.1.6 [Delete](#Delete)
2. [RESTful Service](#RESTful Service)
3. [Cloud Application](#Cloud Application)

####Basic HTTP Interface
Code is located within NathanAinsley18028669Cloud+Http+Ajax.Zip
For testing because the Database it is looking at is the Cloud one which wont be running after submission data to prevent the occuring of unwanted charges if you wish to test the code out please change the data within the hibernate.cgf.xml file to that of the mudfoot server or one that is running.
The Basic HTTP Interface can be accessed through either directly accessing the servlets or via the provided HTML interface. Both of the scenarios are presuming that the application is running on a tomcat local server. Otherwise the url would be different with the IP replacing the localhost:port

To access the servlets directly use the following links.
*note:- the format parameter can be passed either xml/json/string with json being the default choice if none are supplied*
*note:- this application has been designed with tomcat 9.0 in mind*
*note:- the port used by tomcat in the links is 8080 however if yours is different then reflect that in the url*
- http://localhost:8080/AssignmentPartA/AllFilms?format=xml
-- Returns all the films in the database to the screen
- http://localhost:8080/AssignmentPartA/Search?filmid={id}&format=xml
-- Returns the film with the provided id back the the user
- http://localhost:8080/AssignmentPartA/Search?filmtitle={title}&format=xml
-- Returns the films that contain the string provided in their title
- http://localhost:8080/AssignmentPartA/Search?filmyear={year}&format=xml
-- Returns the films that contain the string provided in their release year
- http://localhost:8080/AssignmentPartA/Search?filmdirector={director}&format=xml
-- Returns the films that contain the string provided in their director
- http://localhost:8080/AssignmentPartA/Search?filmstars={stars}&format=xml
-- Returns the films that contain the string provided in their stars

To access the main Graphical user interface created with HTML use the following link
- http://localhost:8080/AssignmentPartA/

##### Interface Introduction
When the GUI loads you will be presented with 3 buttons, 2 dropdown boxes and a single input box. The first button you will see, the biggest one and the button located at the top of the page is the mode swap button **Swap between Add/Search+Edit+Delete Modes**. Pressing this button will hide the rest of the inputs and replace them with some text boxes for inserting data. Pressing the button a second time will revert the screen to its original state.
######Add Film
After pressing the button you will be faced with a new interface specifically for inserting data into the database. There are multiple input boxes with labels for the data they want to be populated with. When you have entered the data pressing the **Add Film** button will attempt to insert the new record into the database. However it will first check to make sure that the ID provided doesnt colide with an ID already in the database. If there was a match then the application would ask the user to try a different ID value, this is to prevent multiple films from having the same ID.
###### Searching Overview
Pressing the **Swap between Add/Search+Edit+Delete Modes** button will return the interface to its normal operation mode.
Within this Regular mode there are 2 drop down boxes. The most important one currently is the 2nd box being the format box. This box allows the user to specify which format the data they get send is in being XML/JSON/STRING.
###### All Films
Pressing the **GetAllFilms** button will return all the films in the database to the screen, and depending on the format chosen will send in that format. However, no matter what format is chosen the way the data is presented to the user in the GUI does not change it is simply the format the Javascript recieves.
###### Search Films
The other dropdown box allows the user to Tailor their search in the database by selecting the field they would like to search against. These fields are;
- Id
- Title
- Year
- Director
- Stars

Selecting the search type you would like (field you would like to search against) and then entering your search value into the Search Bar allows you to then press the **Search Films** button to return records if any excist to match the search to the screen. 
*Please note that you must make sure to match the search type to what you want to search against, it will not automatically detect what you are searching for*

###### Edit Mode

Once a film has been searched for you will notice that each record from the database is in its own li or box, this box is specific to that record and allows through Mustache.js to perform some operations on that data. 
Pressing the **Edit** button turns that li into edit mode replacing the text with textboxes and populating them with the text for that record. This allows you to make subtle changes without having to retype out the entire record. 
If you decided not to save your changes to the record pressing the **Cancel** button will revert the li back to its normal state. However if you choose to save your changes pressing the **Save** button will do such that. Updating the li with the new data and reverting it back to its original none edit mode. The record is updated on the SQL server and the interface reflects that.

###### Delete

Within the li of the records when you have searched for a film you may have noticed the little red box in the top right of the screen that contains a single **X**.
This button is the delete button for that individual record. Pressing it will instantly delete the record from the database and it will be removed from the screen. It does this by getting the ID for the record that the li belongs to and then passes that to the Delete Servlet.

#### RESTful Service

Code is located within NathanAinsley18028669Rest.Zip

The RESTful service has 6 different operations within it those are:

| **Resource Path** 				| **Request Type** 	| **Return** 						| 
|-----------------------------------------------|-----------------------|-------------------------------------------------------|
|rest.18028669.services/rest/films 		| Get 			| Returns all the films in the database to screen 	| 
|rest.18028669.services/rest/films/count 	| Get 			| Returns the number of records in the database 	|
|rest.18028669.services/rest/films/{id} 	| Get 			| Returns specific record with the id supplied 		|
|rest.18028669.services/rest/films 		| Post 			| Adds film object to the database 			|
|rest.18028669.services/rest/films 		| Put 			| Updates film record with object 			|
|rest.18028669.services/rest/films/{id} 	| Delete 		| Deletes film record from database 			|

These different methods can be called either from a java application as done during testing or via a webpage.
The RESTful application is designed to be ran on Tomcat 9.0 as that was the version used during development.

#### SOAP
Code is located within NathanAinsley18028669Soap.Zip
There was an attempt at the creation of a SOAP service however the service is not fully functional. There excists an interface 

#### Cloud Application
Code is located within NathanAinsley18028669Cloud+Http+Ajax.Zip
The Cloud application is the same as the HTTP interface except it has been uploaded to google cloud and run via the google app engine. The cloud based application can be accessed via the url: https://assignment-cloud-18028669.nw.r.appspot.com/
The application functions exactly the same as the one talked about in the [Basic Http Interface](#Basic HTTP Interface) section.
The SQL database is also cloud based but will be turned off post submission data to prevent unwanted charges.


### Conclusion

Please review the Proof of work to see the cloud application in use.
Please also review the Critical Assessment of Code for more indeph analysis of the techniques used when creating the project.
