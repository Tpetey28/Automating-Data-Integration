# Automating-Data-Integration

This project was created as a final project for the Advanced Data Management course I took at WGU. For the assignment, I was given access to a sample database hosted 
on a postgreSQL server. I was tasked with going through the tables in the database, and coming up with a real-world business report that could be created from the data sets. 

The business report I created has the goal of optimizing inventory management, guiding marketing decisions, and ultimately increasing sales.It will do this by giving stakeholders a look into the frequency that each film is being rented. This report will enable the business to make informed decisions when it comes to replacing non-performing inventory. It will also help our marketing teams to decide which highly popular films to include in promotional campaigns to generate more sales. 

To create the business report, I first created two empty tables to house data from the database. I then set up an extraction of data from 4 different tables (using inner-join statements) to populate the first "detailed" table. 

My next step was to create a function used to transform several fields from the detailed table into a singular field. This function will be utilized as part of a trigger function created later on. 

I then created a trigger function that is triggered any time an update is made to the detailed table. This trigger function populates the second empty table that I created, and is labeled "summary". The tranformation function created earlier is also called with this trigger function and concatenates the first_name and last_name fields into one field labeled manager_name. 

One of my last steps was to create another trigger function to remove duplicate values from the "summary" table. This function is triggered by any update to the "summary" table.

My last step to complete the automation was to create a stored procedure that would refresh both tables at once. This guarantees that the data in the "summary" and "detailed" tables remains fresh each time the business calls for the report.

The report will be set up to run at regular monthly intervals using pgAgent in pgAdmin and emailed to stakeholders for review.

Please see the Business Report Summary file for a complete business report detailing the plan for the report and what it will accomplish. The Business Report Summary also includes the SQL code written to complete the automation. Also included is the SQL CODE file which includes only the SQL code used for this project.

Thanks for reading! :)

