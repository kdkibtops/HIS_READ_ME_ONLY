# QA-Rad

## Description:

Quality assurance Radiology assistant application that can help in managing Radiology departments while sticking to the quality standards so the department can get accrediation easily avoiding too much paper work.

## Goal:

Develop an application based on the GAHAR or JCI standards that can manage Radiology departments, this application should include a RIS system with the option of DICOm viewer and document editor, it shall have an HLA7 server to send and recieve HLA7 messages as well as DICOM server to retrieve and send DICOM files and open them in a viewer.
The application should contain all needed standards with the ability to follow up the compliance of the department to the standards and give alert whenever a standard/policy is violated with the option to log all data to corresponding files so the agencies can follow up the department compliance.
When the application is validated I have to seek accreditation from GAHAR or JCI accordingly.

## Where am I now:

I have my-pacs & rad-assist-app both working the original project was my-pacs but I ruined it when I ran "npm audit fix --force" so I copied all data to rad-assist-app and created new react project then I fixed all issue in my-pacs.
I have also updated the index.html file by adding type="text/babel" to all scripts and I installed babel-preset package to avoid Uncaught syntax error on the console while running the app.

I will continue to work on my-pacs and leave rad-assist-app as a backup.

Lastly I wanted to turn my project to typescript but I have some issues with the response coming from the server so I stopped at defining the types.

### The Application has the following functions:

#### FrontEnd: 

It uses react to view orders, patients, studies, users, user configuration with the possibility to upload files.

#### BackEnd:

- Based on PostgreSQL database I have the following tables:
  - main.users: it holds all data of the user including their documents and user configuration.
  - main.studies: it holds all data of the studies.
  - main.patients: it holds all data of the patients.
  - main.orders: it hold all data of the orders.

#### Next steps will include:

- Unifying the server response for all requests becasue authorization requests still return different response format, so my plan is to define types in the main folder and import types from this files for both the frontend and backend so both files will be catching the same response from both then I will update all the backend handlers to return the same response format to the frontend
- I need to define new request formats mostly from the backend so the frontend will be obligated to send these requests only
- I need to do the following in the backend:
  - Add new HR section that will handle all the staff documents and data
  - Add roles for users
  - Add a new table for allergy, events, laboratory results and clinical data for each patient
  - Add a new column in studies that holds the average dose for each study by calculating the average from orders table
- Use more models for manipulating the database so I can get the following:
  - Average radiation dose for each study
  - Get cumulative radiation dose for the patient in a specific period
- In the front end I have to do the following:
  - Add a new document editor for the frontend
  - add QR code to get the patient
  - when click on the patient retrieve all his orders
  - add QR code to get the roder
- Create new inventory application that will handle all stock and consumables including its frontend and then backend
