# QA-Rad
Description: Quality assurance Radiology assist app

I have my-pacs & rad-assist-app both working the original project was my-pacs but I ruined it when I ran "npm audit fix --force" so I copied all data to rad-assist-app and created new react project then I fixed all issue in my-pacs
I have also updated the index.html file by adding type="text/babel" to all scripts and I installed babel-preset package to avoid Uncaught syntax error on the console while running the app

I will continue to work on my-pacs and leave rad-assist-app as a backup

Lastly I wanted to turn my project to typescript but I have some issues with the response coming from the server so I stopped at defining the types

# Next steps will include:
- unifying the server response for all requests becasue authorization requests still return different response format, so my plan is to define types in the main folder and import types from this files for both the frontend and backend so both files will be catching the same response from both then I will update all the backend handlers to return the same response format to the frontend
- I need to define new request formats mostly from the backend so the frontend will be obligated to send these requests only
- Add a new document editor for the frontend
- Add new HR section that will handle all the staff documents and data
- Use more models for manipulating the database so I can get the following:
    - Average radiation dose for each study
    - add roles for users
- In the front end I have to do the following:
    - add QR code to get the patient
    - when click on the patient retrieve all his orders
    - add QR code to get the roder
- Create new inventory application that will handle all stock and consumables
