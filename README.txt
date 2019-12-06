TutorBook
By: Lawrance Oh, Keegan Maundrell, Maria Davis

General Info:

This web application is designed to connect students and tutors through a user-friendly interface. 
Users will be able to sign up and once logged in for the first time will be prompted to declare 
whether they are a tutor, a student, or both. They're also prompted to upload a profile photo and 
provide more information (like which subjects they teach). Once signed in, a user can search for 
a tutor and use tutor search filtering (lowest price to highest price, or highest rating to lowest 
rating). Users can click on individual search results to see a specific tutor's profile page. On the 
profile page, they'll be able to see a tutor's information and also click on a button to see that 
tutor's reviews. All of this can be done without a user being logged in, however if a user is logged 
in they will also be able to see the 'Contact' and 'Book a Tutor' buttons. If a user is logged in 
and has previously had a session with that tutor, they will also be able to see the 'Review Tutor' 
button. Once on the review tutor page, the user can submit a review which will be saved to the 
database collection titled "reviews".

Interaction with Database:

We used Firebase Authentication and Firestore to store data. We currenly have three collections:
(1) users, (2) reviews, and (3) sessions. The users collection contains documents that each hold
the personal information of a user (the id is their email address). The reviews collection is made 
up of documents that include a review, a corresponding rating (out of 5 stars), the email of the user 
who left the review/rating, and the email of the tutor who is being rated. The sessions collection 
contains documents of all tutor sessions that have been booked. These documents contain all the 
necessary information about a session (who, where, when, what subject).

Overview of File Structure:

The html files are structured according to page. There's the home page, signup page, search page, 
profile page, review page, and view reviews page. Each page has a corresponding CSS external stylesheet.

Homepage (homepage.html):

The homepage is the main page, or the first page a user will see when arriving at the web application.
This page is the starting point from which user's can choose to signup/login or start searching for a tutor
without logging in. When a user selects a subject and clicks submit, that subject is saved in localStorage
and immediately accessed on the following page, the search page, where search results appear.

Sign Up (signup.html):

The sign up page enables users to sign in. It is hosted by Firebase Authentication.

Search Page (searchpage.html):

The search page allows a user to search for a tutor in a particular subject. Once more tutors sign up there 
will be more subjects offered. The drop down list will be extended or a user will eventually just type in 
the name of a subject. Our feature uses Firestore querying to access all user documents that contain the 
searched subject in the subject list of a tutor. The search page also features search filtering. Our search 
filter feature sorts through and displays tutors based on lowest-highest rate per hour or highest-lowest 
rating. From the search page, a user can click on a tutor to visit their profile page (to learn more about 
this tutor).

Profile Page (profilepage.html):

The profile page accesses the tutor information saved in localStorage on the previous page (search page) and 
accesses that tutor's information (from the Firestore database). On this page, users will see a tutor's photo, 
name, location, a short bio, subjects that they tutor, their rate/hour, and their average rating. Users will 
be able to click on another button to view that tutor's reviews. If a user is logged in, they will also be 
able to see two extra buttons (Message and Book Session). If a user is logged in and has already had a session 
with this specific tutor, they will see a 4th button (Leave a Review).

View Reviews Page (viewreviewspage.html)

On the 'View Reviews' page, users can see a tutor's reviews. They'll be able to see the rating and written 
review each past student gave the tutor. From here a user can navigate back to the tutor's profile page or 
click on their profile photo at the top right to navigate back to the home page.

Leave a Review Page (reviewpage.html):

On the 'Leave a Review' page, which can only be accessed by a user who has previously had a session with 
this tutor, the user can leave a written review and a rating (1-5 stars). The information they submit will 
be saved in the "reviews" database collection. Upon clicking submit the user will also be navigated back 
to that tutor's profile page.