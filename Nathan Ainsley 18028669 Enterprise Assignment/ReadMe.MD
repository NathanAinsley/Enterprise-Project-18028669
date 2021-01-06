#ReadMe.MD

##Nathan Ainsley 18028669

###Table of Contents
1. [Basic Http Interface](#Basic HTTP Interface)

####Basic HTTP Interface

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
[swapbutton]
[swapbutton]: https://github.com/NathanAinsley/Enterprise-Project-18028669/blob/main/Nathan%20Ainsley%2018028669%20Enterprise%20Assignment/MD%20Images/SwapButton.PNG?raw=true