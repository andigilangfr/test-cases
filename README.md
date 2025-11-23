# test-cases

**Flow 0 - Sign In**

Sign-01
Steps:
  1. User fill correct username login
  2. App calling API tenant information with path /user/who
  3. User fill correct password login
  4. App calling API user profile with path /user/me
  5. App calling API master data with path /tenant/master then all master data with progress bar (locations, sublocations, areas, employees, forms, ect)

Expected:
All API call Return 200 OK, and all master data restored to local devices/web browser. Prompt restart appear just once.

Sign-02
Steps:
  1. Login with successfully (TC Sign-01)
  2. Logut without any clearing cache on mobile/web
  3. Login again with successfuly

Expected:
No heavy call master data, and progress bar undisplayed, also finish instantly

Sign-03
Steps:
  1. Login with invalid username
  2. App calling API tentant information path /user/who

Expected:
Got error message username invalid, due on validation on API tenant the user not registered yet.


**Flow 1 - Inspection Form**

Form-01
Steps:
  1. In WeMineOffice form with maximum 50 fields. 10 Input type, 10 Date Picker, 10 Select, 10 Radio with 4 options, and 10 Image Picker
  2. Log in into WeMine and open Equipment Inspection submission form using the created Form Code

Expected:
All layout correct without any overlap issue, and all 50 fields input displayed.

Form-02
Steps:
  1. Access form TC Form-01 on WeMine
  2. Fill all with valid data (Input data fields with input char, Date picker with selecting date, etc.)
  3. Submit data form

Expected:
Submission Succesful, and all data submitted. All data stored to database submission, and all data validated correct

Form-03
Steps:
  1. Create test form like TC Form-01 on WeMineOffice
  2. Open WeMine and fill all with valid data
  3. Disable the network
  4. Click Submit
  5. Verify submission still on pending and stored to local
  6. Re-enable network

Expected:
Pending submission automatically synced with service, and remove the data pending that stored to local

Form-04
Steps:
  1. Open WeMine, and access the previous submitted form TC Form-01
  2. Verify all data

Expected:
All data submission same as while the data submitted on TC Form-01


**Flow 2 - Safety Hazard Report**

Hazard-01
Steps:
  1. Reporter logs in and submit valid hazard report
  2. Fill all evidences (Location, Sublocation, Area, Area Description, Evidence and PIC pre-selected)

Expected:
Service will generated the hazard notification, PIC got notified, and follow up task

Hazard-02
Steps:
  1. PIC opens the follow up task form
  2. Upload the image evidence, and put date on resolution date
  4. Click on + for Co Observer 2 times
  5. Select 2 different employees
  6. Submit follow up task

Expected:
Submission pass even with 2 different employees on payload as Co Observer

Hazard-03
Steps:
  1. PIC successfuly submit the follow up task TC Hazard-02
  2. Task marked as Complete

Expected:
Direct supervisor got notified and the status of this report as complete
