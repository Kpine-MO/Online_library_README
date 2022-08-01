# ONLINE LIBRARY SOURCE CODE EXPLAINED

## Table Of Content

-[App.js](#app.js)
-[Nav.js](#nav.js)
-[Home.js](#home.js)
-[Library.js](#library.js)
-[Card.js](#card.js)
-[BookDetails.js](#bookdetails.js)
-[Donations.js](#donation.js)
-[CommentCard.js](#commentcard.js)
-[DonationForm.js](#donationform.js)


# App.js

![images](./images/Screenshot%20from%202022-08-01%2014-14-00.png)

-App.js component is the components that dictates how my app we look like on the brouser, it is were all the other componets are held right before I render everything in the index.js

-In this component is where i have imported my BrowserRouter library, the function of the BrowserRouter is to enable me to navigate between the different componets i have on my navigation bar and also keep track of my browser URL.

-In the between the return on line 12 we have the Router(parent component, which keeps the UI in sync with the URL) tag sandwiching all the other componets(Routes,route)

-Route renders UI when it's path matches the current URL we are in.

-The Nav component on line 15 is specificly located outside the Routes tag to ensure we have our nav bar presents in all UI.

## Nav.js

![images](./images/Screenshot%20from%202022-08-01%2014-54-00.png)

-In this component is where we make navigation arround our application possible, first we import the Link hook from the react-router-dom.

-We then use the <link> tag as a like to our different route, so what happens is in our opening <Link> tag we add (to="/path") and if the (to="/") matches the exact path on the route then we are transfered to the component that that route is asigned to


### Library.js && Card.js

![images](./images/Screenshot%20from%202022-08-01%2015-19-11.png)
![images](./images/Screenshot%20from%202022-08-01%2015-19-17.png)

-In this component is where we render all our array of books that we have present in our database, so we create a state assign it an empty array.

-The next step is fetching the data from our database then we pass that data to our empty book array using the setState 

-We then map through the book array and pick out each property of each book and pass it down to the child component Card.js

-Card.js is resposible for presenting each book in our database, so it picks the props passed down by the parent component Library.js and uses the data to create each book which is then displayed in the Library UI.

-In this component we also have a search area which i made possible by first creating a state searchQuery, asigning it a value of empty string, the next step was I filtered through my displayed books by use of conditional statement.

-So the logic was if the searchQueary===""(nothing typed in the search area) return all the books in our database but if there is something typed in the search are and the typed characters include the title of a book or books we have in our database then return that book or books


#### Donation.js & CommentCard.js

-In this component is where we render all our array of comments that we have present in our database, so we create a state assign it an empty array.

-The next step is fetching the data from our database then we pass that data to our empty comment array using the setState 

-We then map through the comment array and pick out each property of each comment and pass it down to the child component CommentCard.js

-CommentCard.js is resposible for presenting each comment in our database, so it picks the props passed down by the parent component Donation.js and uses the data to create each comment which is then displayed in the CommentCard UI.

-In this component we also have a search area which i made possible by first creating a state searchQuery, asigning it a value of empty string, the next step was I filtered through my displayed comments by use of conditional statement.

-So the logic was if the searchQueary===""(nothing typed in the search area) return all the comments in our database but if there is something typed in the search are and the typed characters include the name of a the person commenting then return that comment made by ther perticular person.

##### Home.js

-This is a simple component containing two buttons named Library and Comment which are linked to our Library component which displays all the books and comment component which displays all the comments respectively.


###### DonationForm.js

![images](./images/Screenshot%20from%202022-08-01%2016-24-57.png)

-This component is resposible for the posting of new comments into our database
