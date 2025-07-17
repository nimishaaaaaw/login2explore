# login2explore
# Micro Project #

## Student Enrollment Form using JsonPowerDB ##

### Table of Contents ###
#### Description ####
#### Benefits of using JsonPowerDB ####
#### Scope of Functionalities ####
#### Examples of Use ####
#### Project Status ####
#### Release History ####
#### Sources ####
#### Illustrations ####
#### Other Information ####

### Description ###
#### This project implements a dynamic Student Enrollment Form using HTML, Bootstrap, and JavaScript, leveraging the JsonPowerDB (JPDB) as its backend database. The form allows users to perform standard database operations (Create, Read, Update) for student records, with the "Roll Number" acting as a primary key. It demonstrates how to build a responsive web application with real-time data handling and a simplified development approach using JPDB. ####

### Benefits of using JsonPowerDB ###
*JsonPowerDB offers several key advantages that make it suitable for projects like this:
*Real-time & High Performance: Provides instant data access and updates, ensuring a smooth user experience.
*Lightweight & Simple to Use: Easy to integrate and manage, reducing the learning curve for developers.
*REST API Based: Simplifies data interaction through standard HTTP requests, compatible with any frontend technology.
*Multi-mode DBMS: Supports various data models (like JSON Document DB and Key-value DB, implicitly used here), offering flexibility.
*True Serverless Support: Eliminates the need for complex server-side programming and database administration, allowing frontend developers to build full-stack               applications with ease.
*Low Development Cost & Faster Time to Market: Accelerates development cycles due to its simplified architecture and ready-to-use APIs.

>Scope of Functionalities:

The Student Enrollment Form provides the following core functionalities:
-Form Initialization: On page load or after any operation, the form resets to an empty state, with the "Roll Number" field enabled and focused, while other fields and buttons are disabled.
-Roll Number Lookup (findRoll):
When a user enters a "Roll Number" and tabs out, the system checks if the ID exists in the "STUDENT-TABLE" relation in "SCHOOL-DB".
-If ID does NOT exist: Enables "Full Name", "Class", "Birth Date", "Address", "Enrollment Date" fields, and the [Save] and [Reset] buttons. The cursor moves to "Full Name".
-If ID EXISTS: Displays the existing student's data in the form, disables the "Roll Number" field, enables other fields for modification, and enables the [Update] and [Reset] buttons. The cursor moves to "Full Name".
-Data Validation (validateData): Ensures all required fields are non-empty and numeric fields (like "Class") contain valid, non-negative numbers before saving or updating. Provides user-friendly messages for missing/invalid data.
-Save Data (saveData):
Stores new student records in the database using a PUT operation (which acts as an upsert based on the Roll Number primary key).
Resets the form to its initial state upon successful save.
-Update Data (updateData):
Modifies existing student records using the SET command (specifically an UPDATE type operation) with the stored rec_no from the initial lookup.
Resets the form to its initial state upon successful update.
-Reset Form (resetForm): Clears all form fields, re-enables the "Roll Number" field, disables other fields and all control buttons, and sets focus back to "Roll Number".
User Feedback: Utilizes a custom message box to display success or error messages to the user, avoiding disruptive alert() pop-ups.

>Examples of Use:

-This form can be used in various scenarios for managing student data:
-New Student Registration: Quickly enroll new students by entering their unique roll number and details.
-Student Profile Management: Easily retrieve and update existing student information (e.g., address, class changes, contact details).
-Data Entry Operations: Streamlined interface for administrative staff to manage student records efficiently.

>Project Status:
Complete and Functional. The form successfully implements all specified requirements for student data management using JsonPowerDB.

>Release History:
v1.0.0 (July 16, 2025)

>Initial release of the Student Enrollment Form.

-Implemented CRUD operations (Create/Update via PUT/SET, Read via GET_BY_KEY).
-Dynamic form field and button enabling/disabling based on Roll Number existence.
-Client-side data validation.
-Integration with JsonPowerDB using jpdb-commons.js and custom functions.
-User-friendly message display.

>Sources:

-JsonPowerDB Official Website: http://login2explore.com/
-JsonPowerDB Commons JS: http://login2explore.com/jpdb/resources/js/0.0.3/jpdb-commons.js
-Bootstrap 5.1.1: https://cdn.jsdelivr.net/npm/bootstrap@5.1.1/dist/css/bootstrap.min.css
-jQuery 3.5.1: https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js

>Illustrations:

FORM
<img width="1920" height="1080" alt="Screenshot (2193)" src="https://github.com/user-attachments/assets/bdda9f31-8142-4b03-9ec8-86441a27556f" />

FILLING FORM 
<img width="1920" height="1080" alt="Screenshot (2189)" src="https://github.com/user-attachments/assets/70c5dc9d-ed94-444c-aa03-8074121c69df" />

UPDATING INFO
<img width="1920" height="1080" alt="Screenshot (2190)" src="https://github.com/user-attachments/assets/cc380030-32ff-44f2-9cf5-a81d0f85d4ca" />

JPDB 
<img width="1920" height="1080" alt="Screenshot (2191)" src="https://github.com/user-attachments/assets/be37c9cd-ee27-4b59-82ae-c4dd1bb5a8e9" />



>Other Information:
-Database: The form interacts with the SCHOOL-DB database and STUDENT-TABLE relation in JsonPowerDB.
-Connection Token: Ensure your token variable in index.js is updated with a valid JsonPowerDB connection token for the specified database and relation.
-Primary Key: The Roll_No field acts as the primary key for the STUDENT-TABLE relation.
