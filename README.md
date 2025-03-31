Booktracker Application
Overview
The Booktracker Application is a Java command-line program that manages a SQLite database for tracking users' reading habits. The application stores user information and reading records, and it provides various functionalities to add, update, delete, and query data.

The database uses two tables:

User

userID (INTEGER PRIMARY KEY AUTOINCREMENT)

age (INTEGER)

gender (TEXT)

Name (TEXT) – This column is added as required.

ReadingHabit

habitID (INTEGER PRIMARY KEY AUTOINCREMENT)

book (TEXT) – The title or name of the book

pagesRead (INTEGER) – The number of pages read

submissionMoment (DATETIME) – The time when the record was created

user (INTEGER) – A foreign key referencing User(userID)

Functionalities
The program provides the following functionalities:

Add a user to the database.

Provide all the reading habit data for a certain user.

Provide the ability to change the title of a book in the database (by habitID).

Provide the ability to delete a record/row from the ReadingHabit table (by habitID).

Provide the mean age of the users.

Provide the total number of users that have read pages from a specific book.

Provide the total number of pages read by all users.

Provide the total number of users that have read more than one book.

Add a column to the User table named "Name" which contains TEXT data.

Project Structure
csharp
Copy
Assignment-2/
├── .idea/                           # IntelliJ IDEA project configuration files
├── out/                             # Compiled output files
├── src/                             # Java source files
│   ├── BooktrackerApp.java          # Main application (command-line interface)
│   └── SQLManager.java              # Database operations and schema initialization
└── README.md                        # This file
Requirements
Java JDK 11 or higher

SQLite JDBC library (added via Maven or through IntelliJ IDEA's Project Structure > Libraries)

IntelliJ IDEA (or any Java IDE) to compile and run the project

SQLite – the database file (booktracker.db) will be created automatically

Setup Instructions
Clone or Download the Repository:
Download or clone the repository to your local machine.

Open the Project in IntelliJ IDEA:

Open IntelliJ IDEA.

Click File > Open and select the project folder (Assignment-2).

Add the SQLite JDBC Dependency:
If you are not using Maven, add the SQLite JDBC JAR file to your project via File > Project Structure > Libraries.

Build the Project:
Use Build > Build Project to compile the source files.

Run the Application:
Right-click on BooktrackerApp.java and select Run 'BooktrackerApp.main()'.
The application will initialize the database (booktracker.db), create the necessary tables, and display the command-line menu.

How to Use
After running the application, you will see a menu with the following options:

Add a User

Input the user's age, gender, and name to create a new record in the User table.

Show Reading Habit Data for a User

Input a user ID to display all reading habit records associated with that user.

Change the Title of a Book (by habitID)

Input the habitID for which you want to update the book title, then enter the new title.

Delete a Reading Habit Record (by habitID)

Input the habitID of the record you wish to delete from the ReadingHabit table.

Show the Mean Age of Users

The application calculates and displays the average age of all users in the database.

Show Total Number of Users that have read pages from a Specific Book

Input a book title to display the count of distinct users who have a record for that book.

Show Total Number of Pages Read by All Users

The application sums up and displays the total pages read from all reading habit records.

Show Total Number of Users that have read more than one book

The application calculates and displays the count of users with reading records for more than one book.

Add 'Name' Column to User Table

If the "Name" column does not exist in the User table, this function will add it.

Exit

Closes the application.

Additional Notes
After the program starts, if you perform a delete operation, the database file will refresh itself. Because the assignment criteria do not require re-insertion of data, once a deletion is performed, the data cannot be recovered.

Therefore, if you need to test further operations, modify your code as necessary and re-run the program in your Java IDE.

Alternatively, you can also use DB Browser for SQLite to add or remove data via SQL commands.

The application creates the database file booktracker.db in the project root if it does not exist.

SQL queries are executed using JDBC. The CREATE TABLE IF NOT EXISTS statements ensure that tables are not recreated if they already exist.

SLF4J warnings may appear if no logging backend is configured; these do not affect the functionality of the application.

Authors
Emir Doğan - https://github.com/EmirDogan16

Alireza Mehmannavaz - https://github.com/alireza-meh
