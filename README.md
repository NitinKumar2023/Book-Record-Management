# Book-Record-Management

# Main File - index.js , it can have n number of routes (users and books) and every route can have n number of controllers

# Server >> Storing certain book data
#        >> User registration
#        >> Subscriber

# This is a book management API server for library system

# FINE SYSTEM
01-01-2023 ---> 01-04-2023
03-04-2023 ---> 2 DAYS LATE * 50(LATE FEE)

# Subscription Types
3 months - (Basic)
6 months - (Standard)
12 months - (Premium)

If Subscription is STANDARD && started from 01/01/2023
    >> valid till 01/07/2023

If we are subscribed and we miss the renewal date then  >> FINE 50/day
If we are not subscribed / miss the renewal date then >> FINE 100 + 50/day


# ROUTES AND ENDPOINTS 

# /users
POST - Create a new user (post info to server)
GET - all user information (get info from server)

# /users/(id)
GET - info for a particular user by their id
PUT - update certain info of the user by their id
DELETE - Delete user by their id (check if he/she has any book issued or any fine left )

# /users/subscription-details/(id)
GET - get user subscription details 
    >> Date of Subscription
    >> Valid Till
    >> Is there any fine

# /books 
GET - get all the books
POST - Create or Add a new book 

# /books/(id)
GET - get book by ID
PUT - update books by ID
DELETE - Delete book by their id 

# /books/issued 
GET - all books which have been issued

# /books/issued/fine
GET - all books which have been issued with fine

# How To Start The Project
npm init 
npm i express
npm i nodemon --save-dev
npm run dev


# Specifics 
index.js contains all basic routes 
routes/users.js contains all routes related to USERS
routes/books.js contains all routes related to BOOKS

# HOW TO CALCULATE DAYS 
new Date();  ----->if there's no prior date , do this to get today's date with exact time to miliseconds
Sun Jun 04 2023 02:55:31 GMT+0530 (India Standard Time) -----> today's date

const newDate = new Date("06/08/1998");  ------> if you have a date log it in like this 
undefined

newDate
Mon Jun 08 1998 00:00:00 GMT+0530 (India Standard Time)

Math.floor(newdate / (1000*60*60*24));  ----> to get DAYS from that date divide by 1000 ms * 60 sec * 60 mins * 24 hours
10443 days


# MVC Architecture ----> Model  View  Controller Architecture
>>  Model >> Bundle of View And Controller (frontend + backend)   Depicts structure of MongoDB collection 
>>  View >>  Defines how it looks (frontend (Handled by React.js In this project)) 
>>  Controllers >> Brain or Logical Part of a Route (Backend)  
    >>books.controllers.js
    >>users.controllers.js


# Schema - tells us how values are stored in our files / database
id : number 
name : string 
age : number 
gender : char || varchar(1)

# Model - doesn't specify the type but tells the values
id : 1 
name : nitin 
age : 26 
gender : 'M'


# Referential Integrity 
            Users file                          Books file
            issuedBook(foreign key)     =       id(Primary Key)

# ids will be auto generated 

# DTO (Data Transfer Object)
When we need to transfer information from one object to another without using dot operator(.) we use DTO , it needs certain packages
to be installed : 

eg : var obj main = {
                        name 
                        age 
                        id 
                        gender
                    }

            ||        
            ||
            DTO
            ||
            ||        
    
    var obj copy =  {
                        name 
                        age 
                        id 
                        gender
                    }